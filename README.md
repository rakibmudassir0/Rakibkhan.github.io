x      line-height: 1.6;
    }
    header {
      text-align: center;
      padding: 1rem;
      background: var(--card);
      position: sticky;
      top: 0;
      z-index: 10;
    }
    header h1 {
      margin: 0.5rem 0 0;
      font-size: 1.8rem;
    }
    header p {
      margin: 0.3rem 0 1rem;
      font-size: 1rem;
      color: gray;
    }
    nav {
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }
    nav a {
      text-decoration: none;
      color: var(--text);
      font-weight: bold;
      padding: 0.4rem 0.8rem;
      border-radius: 6px;
      transition: background 0.3s, color 0.3s;
    }
    nav a:hover {
      background: var(--accent);
      color: #fff;
    }
    nav a.active {
      background: var(--active);
      color: #fff;
    }
    main {
      display: grid;
      gap: 1.5rem;
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
    }
    section {
      background: var(--card);
      border-radius: 10px;
      padding: 1.5rem;
      min-height: 60vh; /* ডেমো দেখানোর জন্য লম্বা */
    }
    h2 {
      margin-top: 0;
      font-size: 1.4rem;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
    }
    .card {
      background: var(--bg);
      border-radius: 8px;
      padding: 1rem;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }
    input, textarea, button {
      padding: 0.6rem;
      border: 1px solid #aaa;
      border-radius: 6px;
      font-size: 1rem;
    }
    button {
      background: var(--accent);
      color: #fff;
      border: none;
      cursor: pointer;
      transition: background 0.3s;
    }
    button:hover {
      background: #005f99;
    }
    footer {
      text-align: center;
      padding: 1rem;
      font-size: 0.9rem;
      color: gray;
    }
  </style>
</head>
<body>

  <header>
    <h1>আপনার নাম এখানে</h1>
    <p>একটি সুন্দর ট্যাগলাইন লিখুন</p>
    <nav>
      <a href="#about">পরিচিতি</a>
      <a href="#skills">দক্ষতা</a>
      <a href="#projects">প্রজেক্ট</a>
      <a href="#contact">যোগাযোগ</a>
    </nav>
  </header>

  <main>
    <section id="about">
      <h2>পরিচিতি</h2>
      <p>এখানে আপনার সম্পর্কে কিছু তথ্য লিখুন — যেমন আপনি কী করেন, আপনার আগ্রহ কী ইত্যাদি।</p>
    </section>

    <section id="skills">
      <h2>দক্ষতা</h2>
      <div class="grid">
        <div class="card">দক্ষতা ১</div>
        <div class="card">দক্ষতা ২</div>
        <div class="card">দক্ষতা ৩</div>
        <div class="card">দক্ষতা ৪</div>
      </div>
    </section>

    <section id="projects">
      <h2>প্রজেক্ট</h2>
      <div class="grid">
        <div class="card">
          <strong>প্রজেক্ট ১</strong><br>
          সংক্ষিপ্ত বিবরণ
        </div>
        <div class="card">
          <strong>প্রজেক্ট ২</strong><br>
          সংক্ষিপ্ত বিবরণ
        </div>
        <div class="card">
          <strong>প্রজেক্ট ৩</strong><br>
          সংক্ষিপ্ত বিবরণ
        </div>
      </div>
    </section>

    <section id="contact">
      <h2>যোগাযোগ</h2>
      <form>
        <input type="text" placeholder="নাম" required>
        <input type="email" placeholder="ইমেইল" required>
        <textarea rows="4" placeholder="বার্তা লিখুন..." required></textarea>
        <button type="submit">পাঠান</button>
      </form>
    </section>
  </main>

  <footer>
    <p>© ২০২৫ আপনার নাম</p>
  </footer>

  <script>
    // scroll-based active link
    const sections = document.querySelectorAll("section");
    const navLinks = document.querySelectorAll("nav a");

    window.addEventListener("scroll", () => {
      let current = "";
      sections.forEach(section => {
        const sectionTop = section.offsetTop - 100;
        if (scrollY >= sectionTop) {
          current = section.getAttribute("id");
        }
      });

      navLinks.forEach(link => {
        link.classList.remove("active");
        if (link.getAttribute("href") === "#" + current) {
          link.classList.add("active");
        }
      });
    });
  </script>
</body>
</html>
