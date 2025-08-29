<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>VivaLeve - Saúde e Bem-estar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 font-sans">

  <!-- Header fixo -->
  <header class="bg-emerald-600 text-white shadow-lg fixed w-full top-0 z-50">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-4">
      <!-- Logotipo -->
      <a href="index.html" class="flex items-center">
        <svg id="logo-vivaleve" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 300 80" width="160" height="50">
          <path d="M40 70 C20 40, 20 10, 50 10 C80 10, 80 40, 60 70 Z" 
                fill="#059669" stroke="#047857" stroke-width="2"/>
          <text x="100" y="50" font-family="Poppins, Arial, sans-serif" font-weight="bold" font-size="32" fill="#ffffff">
            Viva<tspan fill="#bbf7d0">Leve</tspan>
          </text>
        </svg>
      </a>

      <!-- Menu -->
      <nav>
        <ul class="flex gap-6 font-semibold">
          <li><a href="index.html" class="hover:text-gray-200">Início</a></li>
          <li><a href="dieta.html" class="hover:text-gray-200">Monte sua Dieta</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Espaço para não sobrepor -->
  <div class="h-24"></div>

  <!-- Hero Section -->
  <section class="relative bg-cover bg-center h-[80vh]" style="background-image: url('https://images.unsplash.com/photo-1510626176961-4b57d4fbad03?auto=format&fit=crop&w=1400&q=80');">
    <div class="absolute inset-0 bg-emerald-900 bg-opacity-60 flex items-center justify-center text-center px-6">
      <div>
        <h1 class="text-4xl md:text-6xl font-bold text-white">Viva saudável, VivaLeve</h1>
        <p class="mt-4 text-xl text-emerald-100">Monte sua dieta personalizada em minutos</p>
        <a href="dieta.html" class="mt-6 inline-block bg-white text-emerald-600 px-8 py-3 rounded-lg font-bold shadow-lg hover:bg-gray-100">
          Começar Agora
        </a>
      </div>
    </div>
  </section>

  <!-- Seção de Destaques -->
  <section class="py-20 bg-white">
    <div class="max-w-6xl mx-auto px-6 text-center">
      <h2 class="text-3xl font-bold text-gray-800 mb-12">Alimentação Saudável ao Seu Alcance</h2>

      <div class="grid md:grid-cols-3 gap-10">
        <div class="bg-gray-50 p-6 rounded-lg shadow hover:shadow-lg transition">
          <img src="https://images.unsplash.com/photo-1506806732259-39c2d0268443?auto=format&fit=crop&w=600&q=80" alt="Salada saudável" class="rounded-lg mb-4">
          <h3 class="text-xl font-semibold text-emerald-700">Saladas Frescas</h3>
          <p class="text-gray-600 mt-2">Receitas leves e nutritivas para o seu dia a dia.</p>
        </div>

        <div class="bg-gray-50 p-6 rounded-lg shadow hover:shadow-lg transition">
          <img src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=600&q=80" alt="Frutas coloridas" class="rounded-lg mb-4">
          <h3 class="text-xl font-semibold text-emerald-700">Frutas Coloridas</h3>
          <p class="text-gray-600 mt-2">Cheias de vitaminas e energia natural para o seu corpo.</p>
        </div>

        <div class="bg-gray-50 p-6 rounded-lg shadow hover:shadow-lg transition">
          <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=600&q=80" alt="Prato fitness" class="rounded-lg mb-4">
          <h3 class="text-xl font-semibold text-emerald-700">Pratos Fitness</h3>
          <p class="text-gray-600 mt-2">Cardápios pensados para ganhar massa e manter energia.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Call to Action -->
  <section class="py-20 bg-emerald-600 text-white text-center">
    <h2 class="text-3xl font-bold">Pronto para transformar sua alimentação?</h2>
    <p class="mt-4 text-lg">Monte agora mesmo sua dieta personalizada com a VivaLeve.</p>
    <a href="dieta.html" class="mt-6 inline-block bg-white text-emerald-600 px-8 py-3 rounded-lg font-bold shadow-lg hover:bg-gray-100">
      Monte sua Dieta
    </a>
  </section>

  <!-- Footer -->
  <footer class="bg-emerald-700 text-white py-6 text-center">
    <p>© 2025 VivaLeve. Todos os direitos reservados.</p>
  </footer>

</body>
</html>
