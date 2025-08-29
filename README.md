<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>VivaLeve - Sua Dieta Inteligente</title>

  <!-- Tailwind -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- jsPDF + svg2pdf -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js" integrity="sha512-NAe2rQ1bB2j1k2mXwXkVxkQ1Xz7kXrGgZ9oP9m4a8D6dZbHc1zQ1FQn5F3l8y2w1wQ3v3d1m6i6P3d3m9Cw7PA==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  <script src="https://cdn.jsdelivr.net/npm/svg2pdf.js@2.0.0/dist/svg2pdf.min.js"></script>

  <style>
    /* Hero com imagem chamativa */
    .hero-bg {
      background-image: url('https://images.unsplash.com/photo-1512621776951-a57141f2eefd?q=80&w=1600&auto=format&fit=crop');
      background-size: cover;
      background-position: center;
    }
    /* Contorno de foco mais visível nos inputs */
    input:focus, select:focus { outline: none; }
  </style>
</head>
<body class="font-sans bg-gray-50 text-gray-800">

  <!-- Header vibrante -->
  <header class="bg-gradient-to-r from-emerald-600 via-teal-500 to-cyan-500 text-white shadow-lg">
    <div class="max-w-7xl mx-auto px-6 py-5 flex items-center justify-between">
      <!-- Logo SVG -->
      <a href="#" class="flex items-center gap-3">
        <svg id="logo-vivaleve" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 300 80" width="200" height="60" aria-label="Logo VivaLeve">
          <path d="M40 70 C20 40, 20 10, 50 10 C80 10, 80 40, 60 70 Z" fill="#10b981" stroke="#065f46" stroke-width="2"/>
          <text x="100" y="50" font-family="Poppins, Arial, sans-serif" font-weight="bold" font-size="36" fill="#ffffff">
            Viva<tspan fill="#bbf7d0">Leve</tspan>
          </text>
        </svg>
      </a>

      <nav class="hidden md:block">
        <ul class="flex gap-6 font-semibold">
          <li><a href="#formulario" class="hover:opacity-90">Dieta</a></li>
          <li><a href="#galeria" class="hover:opacity-90">Galeria Saudável</a></li>
          <li><a href="#contato" class="hover:opacity-90">Contato</a></li>
        </ul>
      </nav>

      <a href="#formulario" class="md:inline-flex hidden bg-white text-emerald-700 font-bold px-5 py-2 rounded-lg shadow hover:shadow-md transition">
        Monte sua dieta
      </a>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero-bg">
    <div class="bg-black/40">
      <div class="max-w-5xl mx-auto px-6 py-24 text-center text-white">
        <h1 class="text-4xl md:text-6xl font-extrabold drop-shadow">Planos alimentares que combinam com você</h1>
        <p class="mt-6 text-lg md:text-xl opacity-95">Na <strong>VivaLeve</strong> você calcula sua dieta, escolhe objetivos e exporta um PDF bonito com sua marca.</p>
        <div class="mt-8 flex gap-4 justify-center">
          <a href="#formulario" class="bg-emerald-500 hover:bg-emerald-400 text-white font-bold px-7 py-3 rounded-lg shadow-lg transition">Começar agora</a>
          <a href="#galeria" class="bg-white/90 hover:bg-white text-emerald-700 font-bold px-7 py-3 rounded-lg shadow-lg transition">Ver comidas saudáveis</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Formulário -->
  <section id="formulario" class="py-16">
    <div class="max-w-5xl mx-auto px-6 grid md:grid-cols-2 gap-10 items-start">
      <div class="bg-white rounded-2xl shadow-xl p-8 border border-emerald-100">
        <h2 class="text-2xl font-extrabold text-emerald-700">Calcule sua dieta</h2>
        <p class="text-gray-600 mt-1">Preencha os dados e gere um PDF estiloso com a marca VivaLeve.</p>

        <form id="dietaForm" class="mt-6 grid gap-4">
          <label class="block">
            <span class="text-sm font-semibold">Seu nome</span>
            <input type="text" id="nome" required class="mt-1 w-full px-4 py-3 rounded-lg border border-gray-200 focus:ring-4 focus:ring-emerald-200 focus:border-emerald-500" placeholder="Ex: Ana Souza" />
          </label>

          <div class="grid grid-cols-2 gap-4">
            <label class="block">
              <span class="text-sm font-semibold">Idade</span>
              <input type="number" id="idade" min="1" required class="mt-1 w-full px-4 py-3 rounded-lg border border-gray-200 focus:ring-4 focus:ring-emerald-200 focus:border-emerald-500" placeholder="Ex: 28" />
            </label>
            <label class="block">
              <span class="text-sm font-semibold">Objetivo</span>
              <select id="objetivo" required class="mt-1 w-full px-4 py-3 rounded-lg border border-gray-200 focus:ring-4 focus:ring-emerald-200 focus:border-emerald-500">
                <option value="emagrecer">Emagrecer</option>
                <option value="ganhar">Ganhar Massa</option>
                <option value="manter">Manter Peso</option>
              </select>
            </label>
          </div>

          <!-- Upload de fotos para inserir no PDF -->
          <div class="mt-2">
            <span class="text-sm font-semibold">Suas fotos (opcional)</span>
            <input id="fotos" type="file" accept="image/*" multiple class="mt-2 block w-full cursor-pointer text-sm" />
            <p class="text-xs text-gray-500 mt-1">Você pode enviar 1 a 6 fotos (serão incluídas no PDF).</p>
            <div id="preview" class="mt-3 grid grid-cols-3 gap-2"></div>
          </div>

          <button type="submit" class="mt-2 bg-gradient-to-r from-emerald-600 via-teal-500 to-cyan-500 text-white font-extrabold py-3 rounded-lg shadow-lg hover:shadow-xl transition">
            Gerar dieta
          </button>
        </form>

        <div id="resultado" class="hidden mt-6">
          <div class="bg-emerald-50 border border-emerald-200 rounded-xl p-5">
            <h3 class="text-lg font-bold text-emerald-700">Sua dieta personalizada</h3>
            <p id="detalhesDieta" class="text-gray-700 mt-1"></p>
            <button id="downloadPDF" class="mt-4 bg-emerald-600 hover:bg-emerald-700 text-white font-bold px-5 py-2 rounded-lg shadow">Baixar PDF</button>
          </div>
        </div>
      </div>

      <!-- Destaques marketing -->
      <aside class="space-y-6">
        <div class="bg-white rounded-2xl shadow-xl p-6 border border-cyan-100">
          <h4 class="text-xl font-extrabold text-cyan-600">Por que VivaLeve?</h4>
          <ul class="mt-3 text-gray-700 list-disc list-inside space-y-1">
            <li>Visual premium com sua marca.</li>
            <li>PDF bonito com faixa e cores chamativas.</li>
            <li>Inclua suas fotos direto no documento.</li>
          </ul>
        </div>

        <!-- Galeria saudável em mini -->
        <div class="bg-white rounded-2xl shadow-xl p-6 border border-pink-100">
          <h4 class="text-xl font-extrabold text-pink-600">Dica de prato do dia</h4>
          <img src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?q=80&w=1200&auto=format&fit=crop" alt="Salada saudável colorida" class="mt-3 rounded-xl shadow w-full object-cover h-52">
          <p class="text-gray-600 mt-3 text-sm">Cores no prato = variedade de micronutrientes 🌈.</p>
        </div>
      </aside>
    </div>
  </section>

  <!-- Galeria Saudável (fotos chamativas) -->
  <section id="galeria" class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-6">
      <h2 class="text-3xl md:text-4xl font-extrabold text-emerald-700 text-center">Galeria de Alimentação Saudável</h2>
      <p class="text-gray-600 text-center mt-2">Inspirações para suas refeições do dia a dia.</p>

      <div class="mt-8 grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Frutas e iogurte" src="https://images.unsplash.com/photo-1484980972926-edee96e0960d?q=80&w=1200&auto=format&fit=crop" />
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Bowl com grãos e legumes" src="https://images.unsplash.com/photo-1543353071-10c8ba85a904?q=80&w=1200&auto=format&fit=crop" />
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Peixe com legumes" src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?q=80&w=1200&auto=format&fit=crop" />
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Smoothie verde" src="https://images.unsplash.com/photo-1505253758473-96b7015fcd40?q=80&w=1200&auto=format&fit=crop" />
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Prato mediterrâneo" src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?q=80&w=1200&auto=format&fit=crop" />
        <img class="rounded-2xl shadow-md w-full h-56 object-cover" alt="Salada com abacate" src="https://images.unsplash.com/photo-1490645935967-10de6ba17061?q=80&w=1200&auto=format&fit=crop" />
      </div>
    </div>
  </section>

  <!-- Contato -->
  <section id="contato" class="py-14 bg-gradient-to-r from-cyan-50 via-emerald-50 to-teal-50">
    <div class="max-w-6xl mx-auto px-6 text-center">
      <h2 class="text-3xl font-extrabold text-emerald-700">Precisa de ajuda?</h2>
      <p class="mt-2 text-gray-600">Fale com a VivaLeve para personalizações, planos avançados e suporte.</p>
      <a href="mailto:contato@vivaleve.com" class="inline-block mt-5 bg-emerald-600 hover:bg-emerald-700 text-white font-bold px-6 py-3 rounded-lg shadow">contato@vivaleve.com</a>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-emerald-700 text-white py-6 text-center">
    <p>© 2025 VivaLeve. Todos os direitos reservados.</p>
  </footer>

  <script>
    // ======= LÓGICA =======
    const form = document.getElementById('dietaForm');
    const resultado = document.getElementById('resultado');
    const detalhesDieta = document.getElementById('detalhesDieta');
    const downloadBtn = document.getElementById('downloadPDF');
    const fotosInput = document.getElementById('fotos');
    const preview = document.getElementById('preview');

    // Guardar imagens (base64) para PDF
    let imagensBase64 = [];

    fotosInput.addEventListener('change', async (e) => {
      preview.innerHTML = '';
      imagensBase64 = [];

      const files = Array.from(e.target.files).slice(0, 6); // limite 6 fotos
      for (const file of files) {
        if (!file.type.startsWith('image/')) continue;
        const base64 = await fileToBase64(file);
        imagensBase64.push(base64);

        // preview
        const img = document.createElement('img');
        img.src = base64;
        img.alt = 'Foto enviada';
        img.className = 'w-full h-24 object-cover rounded-lg border';
        preview.appendChild(img);
      }
    });

    function fileToBase64(file) {
      return new Promise((resolve, reject) => {
        const reader = new FileReader();
        reader.onload = () => resolve(reader.result);
        reader.onerror = reject;
        reader.readAsDataURL(file);
      });
    }

    form.addEventListener('submit', (e) => {
      e.preventDefault();
      const nome = document.getElementById('nome').value.trim();
      const idade = parseInt(document.getElementById('idade').value, 10);
      const objetivo = document.getElementById('objetivo').value;

      // texto simples de recomendação (ponto de partida)
      let dieta;
      if (objetivo === 'emagrecer') {
        dieta = 'Déficit calórico leve, priorizando proteínas magras (frango, peixe, ovos), fibras (legumes, folhas) e carboidratos complexos (arroz integral, batata-doce).';
      } else if (objetivo === 'ganhar') {
        dieta = 'Superávit calórico moderado, alta densidade proteica (frango, ovos, iogurte), bons carboidratos (arroz, aveia) e gorduras saudáveis (abacate, azeite).';
      } else {
        dieta = 'Manutenção com balanço entre proteínas, carboidratos e gorduras; foco em comida de verdade e boa hidratação.';
      }

      detalhesDieta.textContent = `Olá ${nome}, ${dieta}`;
      resultado.classList.remove('hidden');

      // clique do PDF
      downloadBtn.onclick = () => gerarPDF({ nome, idade, objetivo, dieta, imagensBase64 });
    });

    function gerarPDF({ nome, idade, objetivo, dieta, imagensBase64 }) {
      const { jsPDF } = window.jspdf;
      const doc = new jsPDF('p', 'mm', 'a4');

      // Faixa verde topo
      doc.setFillColor(5, 150, 105);
      doc.rect(0, 0, 210, 42, 'F');

      // Logo (SVG do header) no PDF
      const svgElement = document.getElementById('logo-vivaleve');
      svg2pdf(svgElement, doc, {
        x: 65, y: 6, width: 80, height: 28
      });

      // Título
      doc.setFontSize(20);
      doc.setTextColor(34, 197, 94); // verde vibrante
      doc.text('Plano Alimentar Personalizado', 105, 60, { align: 'center' });

      // Caixa dados do usuário
      doc.setDrawColor(16, 185, 129);
      doc.setLineWidth(0.6);
      doc.roundedRect(15, 68, 180, 30, 5, 5, 'S');
      doc.setTextColor(31, 41, 55);
      doc.setFontSize(13);
      doc.text(`Nome: ${nome}`, 20, 80);
      doc.text(`Idade: ${isNaN(idade) ? '-' : idade}`, 20, 90);
      doc.text(`Objetivo: ${objetivo}`, 110, 90);

      // Caixa recomendação (verde clara)
      doc.setFillColor(217, 255, 235);
      doc.roundedRect(15, 105, 180, 52, 5, 5, 'F');
      doc.setTextColor(5, 150, 105);
      doc.setFontSize(15);
      doc.text('Recomendações:', 20, 115);
      doc.setTextColor(55, 65, 81);
      doc.setFontSize(12);
      doc.text(dieta, 20, 125, { maxWidth: 170 });

      // Inserir fotos enviadas (se houver)
      let y = 162; // início da área de fotos
      if (imagensBase64.length > 0) {
        doc.setTextColor(5, 150, 105);
        doc.setFontSize(15);
        doc.text('Suas fotos:', 20, y);
        y += 6;

        const marginX = 15;
        const gap = 5;
        const cols = 3;
        const imgW = (210 - marginX*2 - gap*(cols-1)) / cols; // largura por coluna
        const imgH = 35; // altura fixa

        let col = 0;
        for (let i = 0; i < imagensBase64.length; i++) {
          const x = marginX + col * (imgW + gap);
          doc.addImage(imagensBase64[i], 'JPEG', x, y, imgW, imgH, undefined, 'FAST');

          col++;
          if (col >= cols) {
            col = 0;
            y += imgH + gap;
          }
          // quebra de página se necessário
          if (y + imgH + 20 > 297) { // 297mm altura A4
            doc.addPage();
            y = 20;
          }
        }
      }

      // Rodapé
      doc.setFontSize(10);
      doc.setTextColor(120, 120, 120);
      doc.text('© 2025 VivaLeve - Saúde e Bem-estar', 105, 290, { align: 'center' });

      doc.save('dieta_vivaleve.pdf');
    }
  </script>
</body>
</html>
