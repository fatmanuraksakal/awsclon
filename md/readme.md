
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
</head>
<body class="bg-white text-black relative">

  <!-- BLUR BACKDROP -->
  <div id="blur-backdrop" class="fixed inset-0 bg-white/30 backdrop-blur-sm z-40 hidden"></div>

  <!-- NAVBAR -->
  <nav class="flex items-center justify-between px-8 py-3 border-b border-gray-300 text-sm font-light relative z-50 bg-white">
    <!-- Logo -->
    <div>
      <a href="#"><i class="fab fa-apple text-xl"></i></a>
    </div>

    <!-- Menü -->
    <ul class="flex space-x-6">
      <li><button id="store-button" class="hover:text-gray-500">Store</button></li>
      <li><a href="#" class="hover:text-gray-500">Mac</a></li>
      <li><a href="#" class="hover:text-gray-500">iPad</a></li>
      <li><a href="#" class="hover:text-gray-500">iPhone</a></li>
      <li><a href="#" class="hover:text-gray-500">Watch</a></li>
      <li><a href="#" class="hover:text-gray-500">AirPods</a></li>
      <li><a href="#" class="hover:text-gray-500">TV ve Ev</a></li>
      <li><a href="#" class="hover:text-gray-500">Eğlence</a></li>
      <li><a href="#" class="hover:text-gray-500">Aksesuarlar</a></li>
      <li><a href="#" class="hover:text-gray-500">Destek</a></li>
    </ul>

    <!-- İkonlar -->
    <div class="flex items-center space-x-4">
      <a href="#"><i class="fas fa-search"></i></a>
      <a href="#"><i class="fas fa-bag-shopping"></i></a>
    </div>
  </nav>

  <!-- DROPDOWN -->
  <div id="dropdown" class="absolute top-[64px] left-0 w-full bg-white p-8 z-50 shadow-lg hidden">
    <div class="grid grid-cols-4 gap-6">
      <a href="#" class="hover:underline">MacBook Air</a>
      <a href="#" class="hover:underline">MacBook Pro</a>
      <a href="#" class="hover:underline">iMac</a>
      <a href="#" class="hover:underline">Mac Mini</a>
    </div>
  </div>

  <!-- Sayfa içeriği -->
  <div class="p-10">
    <h1 class="text-3xl font-semibold">Hoş geldin Apple sever 💻</h1>
    <p class="mt-4 text-gray-600">Burada arka plan blur efektli dropdown menümüz var.</p>
  </div>

  <!-- JS: Aç/kapa -->
  <script>
    const dropdown = document.getElementById('dropdown');
    const backdrop = document.getElementById('blur-backdrop');
    const button = document.getElementById('store-button');

    let isOpen = false;

    button.addEventListener('click', () => {
      isOpen = !isOpen;
      dropdown.classList.toggle('hidden', !isOpen);
      backdrop.classList.toggle('hidden', !isOpen);
    });

    // Dışarı tıklayınca kapansın
    document.addEventListener('click', (e) => {
      if (!dropdown.contains(e.target) && !button.contains(e.target)) {
        dropdown.classList.add('hidden');
        backdrop.classList.add('hidden');
        isOpen = false;
      }
    });
  </script>

  





