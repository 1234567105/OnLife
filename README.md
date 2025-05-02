# OnLife
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OnLife – statt online – weil das echte Leben kein WLAN braucht</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gradient-to-b from-blue-100 to-white text-blue-900 font-sans">
  <header class="flex flex-col sm:flex-row items-start sm:items-center p-6 bg-white shadow-md rounded-b-2xl">
    <div class="w-24 h-24 bg-blue-200 rounded-full flex items-center justify-center shadow-md">
      <span class="text-4xl">👾</span>
    </div>
    <div class="mt-4 sm:mt-0 sm:ml-6">
      <h1 class="text-3xl font-extrabold text-blue-800">OnLife – statt online</h1>
      <p class="text-lg text-blue-600">…weil das echte Leben kein WLAN braucht.</p>
    </div>
  </header>

  <section class="p-4 mt-6 max-w-3xl mx-auto">
    <div class="bg-white p-6 rounded-xl shadow-lg border-l-4 border-blue-400">
      <p class="text-lg italic text-blue-700">“Technology should improve your life, not become your life.”</p>
    </div>
  </section>

  <section class="px-4 mt-8 max-w-3xl mx-auto">
    <h2 class="text-2xl font-semibold mb-3">Frag den Avatar 🤖</h2>
    <div class="bg-white p-6 rounded-xl shadow space-y-3">
      <div id="chat-box" class="bg-blue-50 p-3 rounded-lg h-48 overflow-y-auto text-sm"></div>
      <div class="flex gap-2">
        <input id="chat-input" type="text" placeholder="Frag mich etwas..." class="flex-1 p-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-300">
        <button onclick="sendMessage()" class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition">Senden</button>
      </div>
    </div>
  </section>

  <section class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6 p-6 mt-12 max-w-6xl mx-auto">
    <button onclick="showSection('wohlbefinden')" class="bg-white p-6 rounded-2xl shadow hover:shadow-xl border hover:bg-blue-50 transition">Wohlbefinden</button>
    <button onclick="showSection('self')" class="bg-white p-6 rounded-2xl shadow hover:shadow-xl border hover:bg-blue-50 transition">Self Improvement</button>
    <button onclick="showSection('help')" class="bg-white p-6 rounded-2xl shadow hover:shadow-xl border hover:bg-blue-50 transition">Self Help</button>
    <button onclick="showSection('freizeit')" class="bg-white p-6 rounded-2xl shadow hover:shadow-xl border hover:bg-blue-50 transition">Freizeit</button>
  </section>

  <section id="wohlbefinden" class="hidden p-6 max-w-4xl mx-auto bg-white rounded-xl shadow-md mt-6">
    <h3 class="text-xl font-bold mb-3 text-blue-800">Wie fühlen sich Menschen bei der Nutzung?</h3>
    <p>Viele Menschen greifen aus Langeweile, Stress oder Einsamkeit zum Handy. Social Media kann kurzfristig ablenken, aber langfristig auch überfordern.</p>
  </section>

  <section id="self" class="hidden p-6 max-w-4xl mx-auto bg-white rounded-xl shadow-md mt-6 space-y-4">
    <h3 class="text-xl font-bold mb-3 text-blue-800">Was du stattdessen tun kannst</h3>
    <ul class="list-disc ml-6 space-y-2">
      <li><strong>Entspannung:</strong> <a class="text-blue-600 underline" href="#">Meditation & Atemübungen</a></li>
      <li><strong>Sport:</strong> <a class="text-blue-600 underline" href="#">10-Minuten Workouts</a></li>
      <li><strong>Zeitmanagement:</strong>
        <p>Nutze diese To-Do Liste zum Download:</p>
        <a href="https://example.com/todo.pdf" class="inline-block mt-2 px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">To-Do Liste herunterladen</a>
      </li>
      <li><strong>Freizeit:</strong> Brettspiele, Spaziergänge, DIY-Projekte, Bücher lesen...</li>
    </ul>
  </section>

  <section id="help" class="hidden p-6 max-w-4xl mx-auto bg-white rounded-xl shadow-md mt-6">
    <h3 class="text-xl font-bold mb-3 text-blue-800">Warum du dein Handy ständig brauchst?</h3>
    <p>Viele leiden unter digitaler Abhängigkeit ohne es zu merken. Das kann mit Stress, Leere oder sozialen Ängsten zusammenhängen.</p>
    <p class="mt-3">Wenn du dich angesprochen fühlst, sprich mit Freunden oder hole dir Hilfe bei <a class="text-blue-600 underline" href="https://www.bzga.de">bzga.de</a>.</p>
  </section>

  <section id="freizeit" class="hidden p-6 max-w-4xl mx-auto bg-white rounded-xl shadow-md mt-6">
    <h3 class="text-xl font-bold mb-3 text-blue-800">Freizeitideen – weg vom Bildschirm!</h3>
    <ul class="list-disc ml-6 space-y-2">
      <li>Gärtnern oder Pflanzenpflege</li>
      <li>Kreatives Schreiben oder Tagebuch führen</li>
      <li>Gemeinsam kochen oder backen</li>
      <li>Ein neues Hobby lernen: Origami, Malen, Ukulele</li>
      <li>Spazieren gehen oder lokale Orte erkunden</li>
    </ul>
  </section>

  <footer class="text-center p-6 mt-12 text-sm text-blue-500">
    &copy; 2025 OnLife – Für ein bewussteres Leben ohne Dauer-Scrollen.
  </footer>

  <script>
    function showSection(id) {
      document.querySelectorAll('section[id]').forEach(sec => sec.classList.add('hidden'));
      document.getElementById(id).classList.remove('hidden');
      window.scrollTo({ top: document.getElementById(id).offsetTop - 50, behavior: 'smooth' });
    }

    function sendMessage() {
      const input = document.getElementById('chat-input');
      const chat = document.getElementById('chat-box');
      const userMsg = input.value.trim();
      if (!userMsg) return;
      chat.innerHTML += `<div class='text-right mb-2'><span class='inline-block bg-blue-200 px-3 py-1 rounded-lg'>${userMsg}</span></div>`;

      const botReply = getBotReply(userMsg.toLowerCase());
      setTimeout(() => {
        chat.innerHTML += `<div class='text-left mb-2'><span class='inline-block bg-gray-200 px-3 py-1 rounded-lg'>${botReply}</span></div>`;
        chat.scrollTop = chat.scrollHeight;
      }, 500);

      input.value = '';
    }

    function getBotReply(message) {
      if (message.includes('hilfe')) return 'Du bist nicht allein – rede mit jemandem, dem du vertraust.';
      if (message.includes('ideen')) return 'Wie wär’s mit einem Spaziergang oder einem DIY-Projekt?';
      if (message.includes('müde')) return 'Vielleicht brauchst du eine Pause und ein bisschen frische Luft.';
      return 'Interessante Frage! Denk daran: kleine Pausen helfen viel 😊';
    }
  </script>
</body>
</html>
