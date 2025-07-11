

  <!-- Navbar Start -->
  <nav
    id="navbar"
    class="fixed top-0 left-0 w-full flex items-center justify-between px-6 py-3 border-b border-gray-300 text-sm text-white bg-white/10 backdrop-blur-md z-50 transition-colors duration-300"
  >
    <!-- Logo -->
    <div class="text-2xl cursor-pointer">
      <i class="fa-brands fa-apple"></i>
    </div>

    <!-- Desktop Menü -->
    <div class="hidden md:block">
      <ul class="flex space-x-6 text-white">
        <li><a href="#" class="hover:text-gray-400 transition">Store</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">Mac</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">iPad</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">iPhone</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">Watch</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">AirPods</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">TV ve Ev</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">Eğlence</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">Aksesuarlar</a></li>
        <li><a href="#" class="hover:text-gray-400 transition">Destek</a></li>
      </ul>
    </div>

    <!-- Sağ ikonlar ve hamburger mobilde -->
    <div class="flex items-center space-x-4">
      <a href="#" class="hidden md:inline-block text-white hover:text-gray-400 transition">
        <i class="fas fa-search"></i>
      </a>
      <a href="#" class="hidden md:inline-block text-white hover:text-gray-400 transition">
        <i class="fas fa-bag-shopping"></i>
      </a>

      <!-- Hamburger -->
      <button
        id="menu-btn"
        class="md:hidden text-white focus:outline-none"
        aria-label="Menu"
      >
        <svg
          class="w-7 h-7"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          viewBox="0 0 24 24"
        >
          <path d="M4 6h16M4 12h16M4 18h16"></path>
        </svg>
      </button>
    </div>
  </nav>
  <!-- Navbar End -->

  <!-- Mobil Menü -->
  <div
    id="mobile-menu"
    class="fixed inset-0 bg-black bg-opacity-50 backdrop-blur-sm hidden z-40"
  >
    <div class="bg-white bg-opacity-90 backdrop-blur-md w-64 h-full p-6 shadow-lg">
      <button
        id="close-btn"
        class="mb-8 text-gray-700 hover:text-gray-900 font-semibold focus:outline-none"
      >
        Kapat ✕
      </button>
      <nav class="flex flex-col space-y-4 text-gray-800 font-medium">
        <a href="#" class="hover:text-gray-600">Store</a>
        <a href="#" class="hover:text-gray-600">Mac</a>
        <a href="#" class="hover:text-gray-600">iPad</a>
        <a href="#" class="hover:text-gray-600">iPhone</a>
        <a href="#" class="hover:text-gray-600">Watch</a>
        <a href="#" class="hover:text-gray-600">AirPods</a>
        <a href="#" class="hover:text-gray-600">TV ve Ev</a>
        <a href="#" class="hover:text-gray-600">Eğlence</a>
        <a href="#" class="hover:text-gray-600">Aksesuarlar</a>
        <a href="#" class="hover:text-gray-600">Destek</a>
      </nav>
    </div>
    <div
      id="overlay"
      class="flex-1"
      aria-label="Close mobile menu by clicking outside"
    ></div>
  </div>

  <!-- Sayfa içeriği örnek -->
  <main class="pt-20 max-w-7xl mx-auto p-4">
    <h1 class="text-4xl font-bold mb-6">Apple Tarzı Saydam Navbar + Mobil Menü</h1>
    <p>Sayfa kaydırıldığında navbar arka planı opaklaşıyor, mobilde hamburger ile menü açılıyor.</p>
  </main>

  <script>
    const menuBtn = document.getElementById("menu-btn");
    const mobileMenu = document.getElementById("mobile-menu");
    const closeBtn = document.getElementById("close-btn");
    const overlay = document.getElementById("overlay");
    const navbar = document.getElementById("navbar");

    // Menü açma kapama
    menuBtn.addEventListener("click", () => {
      mobileMenu.classList.remove("hidden");
      document.body.style.overflow = "hidden"; // scroll kilitle
    });
    closeBtn.addEventListener("click", () => {
      mobileMenu.classList.add("hidden");
      document.body.style.overflow = "auto"; // scroll aç
    });
    overlay.addEventListener("click", () => {
      mobileMenu.classList.add("hidden");
      document.body.style.overflow = "auto";
    });

    // Scroll ile navbar arka plan değişimi
    window.addEventListener("scroll", () => {
      if (window.scrollY > 30) {
        navbar.classList.remove("bg-white/10", "backdrop-blur-md", "text-white");
        navbar.classList.add("bg-white", "text-gray-800", "border-gray-200");
      } else {
        navbar.classList.add("bg-white/10", "backdrop-blur-md", "text-white");
        navbar.classList.remove("bg-white", "text-gray-800", "border-gray-200");
      }
    });
  </script>
</body>
</html>
