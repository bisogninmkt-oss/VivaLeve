<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>VivaLeve - Sua Dieta Inteligente</title>
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
          <li><a href="#sobre" class="hover:text-gray-200">Sobre</a></li>
          <li><a href="#contato" class="hover:text-gray-200">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Espaço para não sobrepor o conteúdo -->
  <div class="h-24"></div>

  <!-- Hero -->
  <section class="relative text-center py-32 bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1546069901-ba9599a7e63c');">
    <div class="absolute inset-0 bg-black bg-opacity-40"></div>
    <div class="relative z-10 text-white">
      <h1 class="text-5xl font-extrabold">Transforme sua Vida com a <span class="text-emerald-300">VivaLeve</span></h1>
      <p class="mt-6 text-lg max-w-2xl mx-auto">
        Planos alimentares saudáveis, personalizados e fáceis de seguir.  
        Descubra como uma dieta pode ser leve e prazerosa.
      </p>
      <a href="dieta.html" class="mt-8 inline-block bg-emerald-500 text-white px-10 py-4 rounded-lg text-xl font-bold shadow-lg hover:bg-emerald-700">
        Monte sua dieta agora
      </a>
    </div>
  </section>

  <!-- Galeria -->
  <section class="py-20 bg-white">
    <h2 class="text-4xl font-bold text-center text-emerald-700 mb-12">Alimentação Saudável</h2>
    <div class="max-w-6xl mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 px-6">
      <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836" alt="Salada colorida" class="rounded-lg shadow-lg">
      <img src="https://images.unsplash.com/photo-1512058564366-c9e3e0464b8f" alt="Smoothie saudável" class="rounded-lg shadow-lg">
      <img src="https://images.unsplash.com/photo-1543352634-4b9e5c9d3e8f" alt="Frutas frescas" class="rounded-lg shadow-lg">
    </div>
  </section>

  <!-- Sobre -->
  <section id="sobre" class="py-20 bg-gray-50">
    <div class="max-w-4xl mx-auto text-center px-6">
      <h2 class="text-3xl font-bold text-emerald-700 mb-6">Sobre a VivaLeve</h2>
      <p class="text-gray-700 text-lg leading-relaxed">
        A VivaLeve nasceu com o propósito de ajudar pessoas a atingirem seus objetivos com alimentação saudável.  
        Nossos planos são baseados em ciência, mas adaptados para sua rotina, tornando cada refeição prazerosa.
      </p>
    </div>
  </section>

  <!-- Contato -->
  <section id="contato" class="py-20 bg-emerald-50">
    <div class="max-w-3xl mx-auto text-center px-6">
      <h2 class="text-3xl font-bold text-emerald-700 mb-6">Fale Conosco</h2>
      <p class="text-gray-700 mb-6">Tem dúvidas? Quer saber mais? Entre em contato conosco!</p>
      <a href="mailto:contato@vivaleve.com" class="bg-emerald-600 text-white px-8 py-3 rounded-lg font-bold hover:bg-emerald-700">
        contato@vivaleve.com
      </a>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-emerald-700 text-white py-6 text-center">
    <p>© 2025 VivaLeve. Todos os direitos reservados.</p>
  </footer>

</body>
</html>
