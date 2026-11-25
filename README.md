# SoulVisionSketch
Focus about Digital_Media_Vision
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="VisionL — creative digital marketing, design and visual storytelling." />
  <title>VisionL — Creative Digital Studio</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts CDN -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Manrope:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['DM Sans', 'sans-serif'],
            display: ['Manrope', 'sans-serif']
          }
        }
      }
    };
  </script>

  <style>
    :root {
      --page: #101010;
      --surface: #191919;
      --surface-2: #222222;
      --text: #f4f4f4;
      --muted: #a2a2a2;
      --line: rgba(255,255,255,.12);
      --accent: #d7d7d7;
      --overlay: rgba(8,8,8,.72);
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0; background-color: var(--page); color: var(--text);
      font-family: 'DM Sans', sans-serif; transition: background .25s, color .25s;
      background-size: cover; background-position: center; background-attachment: fixed;
    }
    body::before {
      content:""; position:fixed; inset:0; z-index:-1; pointer-events:none;
      background: var(--overlay);
    }
    .display { font-family: 'Manrope', sans-serif; }
    .glass {
      background: color-mix(in srgb, var(--surface) 86%, transparent);
      border: 1px solid var(--line); backdrop-filter: blur(18px);
    }
    .muted { color: var(--muted); }
    .line { border-color: var(--line); }
    .hero-grid {
      background-image: linear-gradient(var(--line) 1px, transparent 1px),
                        linear-gradient(90deg, var(--line) 1px, transparent 1px);
      background-size: 58px 58px;
      mask-image: linear-gradient(to bottom, black, transparent 88%);
    }
    .work-card img { transition: transform .6s cubic-bezier(.2,.7,.2,1); }
    .work-card:hover img { transform: scale(1.055); }
    .work-card:hover .work-arrow { transform: translate(3px,-3px); }
    .work-arrow { transition: transform .2s; }
    .pill { border:1px solid var(--line); background:rgba(255,255,255,.035); }
    .btn-primary { background:var(--text); color:var(--page); }
    .btn-primary:hover { opacity:.86; transform:translateY(-1px); }
    .btn-ghost { border:1px solid var(--line); }
    .btn-ghost:hover { background:var(--surface-2); }
    .field {
      width:100%; border:1px solid var(--line); background:var(--page);
      color:var(--text); border-radius:10px; padding:11px 13px; outline:none;
    }
    .field:focus { border-color:var(--muted); }
    .modal-backdrop { background:rgba(0,0,0,.76); backdrop-filter:blur(8px); }
    .modal-panel { background:var(--surface); border:1px solid var(--line); }
    .theme-swatch { width:22px;height:22px;border-radius:50%;border:2px solid var(--line);cursor:pointer; }
    .toast { opacity:0; transform:translateY(10px); transition:.25s; pointer-events:none; }
    .toast.show { opacity:1; transform:translateY(0); }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { scroll-behavior:auto !important; transition:none !important; }
    }
  </style>
</head>

<body>
  <!-- Navigation -->
  <header class="sticky top-0 z-40 border-b line" style="background:color-mix(in srgb,var(--page) 88%,transparent);backdrop-filter:blur(18px)">
    <div class="max-w-7xl mx-auto px-5 sm:px-8 h-[76px] flex items-center justify-between">
      <a href="#home" class="flex items-center gap-3 min-w-0">
        <div id="brand-mark" class="w-10 h-10 rounded-xl flex items-center justify-center overflow-hidden shrink-0" style="background:var(--text);color:var(--page)">
          <span id="brand-monogram" class="display font-extrabold text-lg">V.</span>
          <img id="brand-logo" class="hidden w-full h-full object-cover" alt="Brand logo">
        </div>
        <div class="min-w-0">
          <div id="brand-name" class="display font-extrabold tracking-[.18em] text-sm sm:text-base truncate">VISIONL</div>
          <div id="brand-tagline-small" class="muted text-[9px] tracking-[.2em] uppercase">Creative digital studio</div>
        </div>
      </a>

      <nav class="hidden md:flex items-center gap-8 text-sm muted">
        <a class="hover:text-current transition" href="#services">Services</a>
        <a class="hover:text-current transition" href="#work">Selected work</a>
        <a class="hover:text-current transition" href="#about">About</a>
        <a class="hover:text-current transition" href="#contact">Contact</a>
      </nav>

      <div class="flex items-center gap-2">
        <button id="open-settings" class="btn-ghost rounded-full px-3 sm:px-4 py-2 text-xs sm:text-sm flex items-center gap-2" aria-label="Open website settings">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.7 1.7 0 0 0 .34 1.88l.06.06-1.7 2.94-.08-.02a1.7 1.7 0 0 0-1.82.55l-.05.07h-3.4l-.04-.08a1.7 1.7 0 0 0-1.55-1.02 1.7 1.7 0 0 0-.3.03l-.09.02-2.94-1.7.02-.09a1.7 1.7 0 0 0-.55-1.81l-.07-.05v-3.4l.08-.04a1.7 1.7 0 0 0 .99-1.85l-.02-.09 1.7-2.94.09.02a1.7 1.7 0 0 0 1.81-.55l.05-.07h3.4l.04.08a1.7 1.7 0 0 0 1.85.99l.09-.02 2.94 1.7-.02.09a1.7 1.7 0 0 0 .55 1.81l.07.05v3.4z"/></svg>
          <span class="hidden sm:inline">Customize</span>
        </button>
        <a href="#contact" class="btn-primary rounded-full px-4 sm:px-5 py-2.5 text-xs sm:text-sm font-semibold transition">Let's talk <span aria-hidden="true">↗</span></a>
      </div>
    </div>
  </header>

  <main id="home">
    <!-- Hero -->
    <section class="relative overflow-hidden">
      <div class="hero-grid absolute inset-0 pointer-events-none opacity-50"></div>
      <div class="max-w-7xl mx-auto px-5 sm:px-8 pt-24 sm:pt-32 pb-24 sm:pb-32 relative">
        <div class="flex items-center gap-3 mb-8">
          <span class="w-2 h-2 rounded-full" style="background:var(--text)"></span>
          <p id="hero-eyebrow" class="muted text-xs sm:text-sm tracking-[.22em] uppercase">Independent digital marketing studio · Sri Lanka</p>
        </div>
        <div class="max-w-5xl">
          <h1 id="hero-title" class="display font-extrabold tracking-[-.065em] leading-[.98] text-5xl sm:text-7xl lg:text-[100px]">
            We make brands<br><span class="muted">impossible to ignore.</span>
          </h1>
          <div class="mt-9 flex flex-col sm:flex-row sm:items-end justify-between gap-8">
            <p id="hero-description" class="muted text-base sm:text-lg leading-8 max-w-xl">
              Strategy, content and design for businesses ready to make their mark.
              We turn bold ideas into meaningful digital experiences.
            </p>
            <a href="#work" class="inline-flex items-center gap-3 text-sm font-semibold group whitespace-nowrap">
              Explore our work <span class="w-10 h-10 rounded-full border line flex items-center justify-center group-hover:translate-x-1 transition">↘</span>
            </a>
          </div>
        </div>

        <div class="mt-20 sm:mt-28 grid grid-cols-2 md:grid-cols-4 border-t line">
          <div class="py-6 pr-4 border-r line">
            <div class="display text-3xl sm:text-4xl font-bold">01<span class="muted">.</span></div>
            <p class="muted text-xs mt-2 tracking-wider uppercase">Think strategically</p>
          </div>
          <div class="py-6 px-4 md:px-7 md:border-r line">
            <div class="display text-3xl sm:text-4xl font-bold">02<span class="muted">.</span></div>
            <p class="muted text-xs mt-2 tracking-wider uppercase">Create with purpose</p>
          </div>
          <div class="py-6 pr-4 pl-4 md:px-7 border-r line">
            <div class="display text-3xl sm:text-4xl font-bold">03<span class="muted">.</span></div>
            <p class="muted text-xs mt-2 tracking-wider uppercase">Connect with people</p>
          </div>
          <div class="py-6 pl-4 md:pl-7">
            <div class="display text-3xl sm:text-4xl font-bold">04<span class="muted">.</span></div>
            <p class="muted text-xs mt-2 tracking-wider uppercase">Grow consistently</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services -->
    <section id="services" class="py-20 sm:py-28 border-t line">
      <div class="max-w-7xl mx-auto px-5 sm:px-8">
        <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-14">
          <div>
            <p class="muted text-xs tracking-[.22em] uppercase mb-4">What we do</p>
            <h2 id="services-title" class="display text-4xl sm:text-6xl font-bold tracking-[-.05em]">Creative thinking.<br>Real-world impact.</h2>
          </div>
          <p id="services-subtitle" class="muted max-w-sm leading-7">A focused set of services to help your business stand out, connect and move forward.</p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 border-t line">
          <article class="py-8 pr-6 lg:border-r line">
            <span class="muted text-xs">01 / STRATEGY</span>
            <h3 class="display text-2xl font-bold mt-9 mb-3">Brand strategy</h3>
            <p class="muted text-sm leading-6">Clear positioning, thoughtful direction and a brand people remember.</p>
          </article>
          <article class="py-8 px-0 md:px-6 lg:border-r line">
            <span class="muted text-xs">02 / SOCIAL</span>
            <h3 class="display text-2xl font-bold mt-9 mb-3">Social media</h3>
            <p class="muted text-sm leading-6">Content and campaigns that build community and keep your brand moving.</p>
          </article>
          <article class="py-8 px-0 md:px-6 lg:border-r line">
            <span class="muted text-xs">03 / VISUALS</span>
            <h3 class="display text-2xl font-bold mt-9 mb-3">Photo & design</h3>
            <p class="muted text-sm leading-6">Distinctive visuals, photography and creative assets made with intention.</p>
          </article>
          <article class="py-8 pl-0 md:pl-6">
            <span class="muted text-xs">04 / DIGITAL</span>
            <h3 class="display text-2xl font-bold mt-9 mb-3">Digital campaigns</h3>
            <p class="muted text-sm leading-6">Digital experiences and campaigns designed to reach the right audience.</p>
          </article>
        </div>
      </div>
    </section>

    <!-- Work / Gallery -->
    <section id="work" class="py-20 sm:py-28" style="background:var(--surface)">
      <div class="max-w-7xl mx-auto px-5 sm:px-8">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-6 mb-12">
          <div>
            <p class="muted text-xs tracking-[.22em] uppercase mb-4">The portfolio</p>
            <h2 id="work-title" class="display text-4xl sm:text-6xl font-bold tracking-[-.05em]">Selected work<span class="muted">.</span></h2>
            <p id="work-subtitle" class="muted mt-4 max-w-lg">A collection of visuals, campaigns and creative experiments.</p>
          </div>
          <label class="btn-primary rounded-full px-5 py-3 text-sm font-semibold cursor-pointer inline-flex items-center gap-2 w-fit">
            <span>＋</span> Add project images
            <input id="image-upload" type="file" accept="image/*" multiple class="hidden">
          </label>
        </div>
        <div id="gallery" class="grid sm:grid-cols-2 lg:grid-cols-3 gap-5">
          <!-- Projects are rendered here -->
        </div>
        <p id="empty-gallery" class="hidden text-center muted py-16 border line rounded-2xl">Your portfolio is ready for its first project. Add images to get started.</p>
        <p class="muted text-xs mt-5">Tip: add your own campaign images, photography and design work. Your images are saved in this browser.</p>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="py-20 sm:py-28 border-t line">
      <div class="max-w-7xl mx-auto px-5 sm:px-8 grid lg:grid-cols-2 gap-14 lg:gap-24">
        <div>
          <p class="muted text-xs tracking-[.22em] uppercase mb-4">A little about us</p>
          <h2 id="about-title" class="display text-4xl sm:text-6xl font-bold tracking-[-.05em] leading-[1.05]">Good ideas deserve<br><span class="muted">great execution.</span></h2>
        </div>
        <div class="flex flex-col justify-end">
          <p id="about-description" class="muted leading-8 text-base sm:text-lg">VisionL is a creative digital marketing studio built around one simple belief: the best work happens when clear thinking meets bold creativity. We partner with ambitious businesses to shape their story and bring it to life online.</p>
          <a href="#contact" class="mt-8 inline-flex items-center gap-3 text-sm font-semibold">Start a conversation <span>↗</span></a>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section id="contact" class="py-20 sm:py-28 border-t line">
      <div class="max-w-7xl mx-auto px-5 sm:px-8">
        <p class="muted text-xs tracking-[.22em] uppercase mb-5">Have a project in mind?</p>
        <div class="flex flex-col lg:flex-row lg:items-end justify-between gap-10">
          <h2 id="contact-title" class="display text-5xl sm:text-7xl lg:text-8xl font-extrabold tracking-[-.065em] leading-[.95]">Let's make<br>something <span class="muted">matter.</span></h2>
          <div class="max-w-sm">
            <p id="contact-description" class="muted leading-7 mb-6">Tell us what you're building. We'd love to hear about your next big idea.</p>
            <a id="contact-link" href="mailto:hello@visionl.lk" class="btn-primary rounded-full px-6 py-3.5 inline-flex items-center gap-3 font-semibold text-sm transition">hello@visionl.lk <span>↗</span></a>
          </div>
        </div>
      </div>
    </section>
  </main>


  <!-- Floating WhatsApp contact button -->
  <a id="whatsapp-button" href="https://wa.me/947XXXXXXXX" target="_blank" rel="noopener noreferrer" aria-label="Chat with VisionL on WhatsApp" title="Chat with us on WhatsApp" class="fixed bottom-5 right-5 z-40 flex items-center gap-3 rounded-full px-4 py-3 shadow-2xl transition hover:-translate-y-1" style="background:#25D366;color:#071b0e;">
    <svg width="23" height="23" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M20.52 3.48A11.82 11.82 0 0 0 12.08 0C5.5 0 .15 5.34.15 11.92c0 2.1.55 4.15 1.6 5.96L0 24l6.28-1.65a11.9 11.9 0 0 0 5.8 1.48h.01c6.57 0 11.92-5.35 11.92-11.92 0-3.18-1.24-6.17-3.49-8.43ZM12.09 21.8h-.01a9.9 9.9 0 0 1-5.04-1.38l-.36-.21-3.73.98 1-3.64-.24-.37a9.87 9.87 0 0 1-1.52-5.26c0-5.46 4.44-9.9 9.91-9.9a9.84 9.84 0 0 1 7.01 2.9 9.84 9.84 0 0 1 2.9 7.02c0 5.46-4.44 9.9-9.92 9.9Zm5.43-7.42c-.3-.15-1.76-.87-2.03-.97-.27-.1-.47-.15-.67.15-.2.3-.77.97-.94 1.17-.17.2-.35.22-.65.07-.3-.15-1.26-.46-2.4-1.47-.89-.79-1.49-1.77-1.66-2.07-.17-.3-.02-.46.13-.61.13-.13.3-.35.45-.52.15-.17.2-.3.3-.5.1-.2.05-.37-.02-.52-.08-.15-.67-1.62-.92-2.22-.24-.58-.49-.5-.67-.51h-.57c-.2 0-.52.07-.79.37-.27.3-1.04 1.02-1.04 2.49s1.07 2.89 1.22 3.09c.15.2 2.1 3.2 5.08 4.49.71.31 1.27.5 1.7.64.71.23 1.36.2 1.87.12.57-.08 1.76-.72 2.01-1.42.25-.7.25-1.3.17-1.42-.07-.12-.27-.2-.57-.35Z"/></svg>
    <span class="text-sm font-semibold">Chat on WhatsApp</span>
  </a>

  <footer class="border-t line py-7">
    <div class="max-w-7xl mx-auto px-5 sm:px-8 flex flex-col sm:flex-row justify-between gap-3 muted text-xs">
      <p id="footer-copy">© 2025 VISIONL. ALL RIGHTS RESERVED.</p>
      <p id="footer-note">Independent minds. Creative outcomes.</p>
    </div>
  </footer>

  <!-- Customization panel -->
  <div id="settings-modal" class="hidden fixed inset-0 z-50 modal-backdrop overflow-y-auto p-4 sm:p-8">
    <div class="modal-panel rounded-2xl max-w-2xl mx-auto my-5 p-5 sm:p-8 shadow-2xl">
      <div class="flex items-start justify-between gap-5 mb-7">
        <div>
          <p class="muted text-[10px] tracking-[.2em] uppercase mb-2">Website control centre</p>
          <h2 class="display text-2xl sm:text-3xl font-bold">Customize your brand</h2>
          <p class="muted text-sm mt-2">Update your identity, text, colours and background image.</p>
        </div>
        <button id="close-settings" class="btn-ghost rounded-full w-10 h-10 shrink-0" aria-label="Close settings">✕</button>
      </div>

      <div class="grid sm:grid-cols-2 gap-x-5 gap-y-4">
        <label class="block text-xs muted">Website / brand name
          <input id="setting-name" class="field mt-2" placeholder="VISIONL">
        </label>
        <label class="block text-xs muted">Small tagline
          <input id="setting-tagline" class="field mt-2" placeholder="Creative digital studio">
        </label>
        <label class="block text-xs muted sm:col-span-2">Upload logo (PNG, JPG, SVG)
          <input id="setting-logo" class="field mt-2" type="file" accept="image/*">
        </label>
        <label class="block text-xs muted sm:col-span-2">Main hero heading
          <textarea id="setting-hero" class="field mt-2" rows="2" placeholder="We make brands impossible to ignore."></textarea>
        </label>
        <label class="block text-xs muted sm:col-span-2">Hero description
          <textarea id="setting-hero-desc" class="field mt-2" rows="3"></textarea>
        </label>
        <label class="block text-xs muted">Services heading
          <input id="setting-services" class="field mt-2">
        </label>
        <label class="block text-xs muted">Portfolio heading
          <input id="setting-work" class="field mt-2">
        </label>
        <label class="block text-xs muted sm:col-span-2">About description
          <textarea id="setting-about" class="field mt-2" rows="3"></textarea>
        </label>
        <label class="block text-xs muted">Contact email
          <input id="setting-email" class="field mt-2" type="email" placeholder="hello@example.com">
        </label>
        <label class="block text-xs muted">Footer note
          <input id="setting-footer" class="field mt-2">
        </label>
        <div class="sm:col-span-2">
          <p class="text-xs muted mb-3">Colour theme</p>
          <div class="flex flex-wrap gap-3">
            <button class="theme-choice pill rounded-full px-4 py-2 text-xs flex items-center gap-2" data-theme="dark"><span class="theme-swatch" style="background:#151515"></span> Black / white</button>
            <button class="theme-choice pill rounded-full px-4 py-2 text-xs flex items-center gap-2" data-theme="light"><span class="theme-swatch" style="background:#f4f4f4"></span> White / grey</button>
            <button class="theme-choice pill rounded-full px-4 py-2 text-xs flex items-center gap-2" data-theme="grey"><span class="theme-swatch" style="background:#777"></span> Grey / black</button>
          </div>
        </div>
        <label class="block text-xs muted sm:col-span-2">Change page background picture
          <input id="setting-background" class="field mt-2" type="file" accept="image/*">
        </label>
        <div class="sm:col-span-2 flex flex-wrap gap-2">
          <button id="remove-background" class="btn-ghost rounded-full px-4 py-2 text-xs">Remove background image</button>
          <button id="reset-settings" class="btn-ghost rounded-full px-4 py-2 text-xs">Reset text & theme</button>
        </div>
      </div>

      <div class="border-t line mt-7 pt-5 flex justify-end gap-3">
        <button id="cancel-settings" class="btn-ghost rounded-full px-5 py-2.5 text-sm">Cancel</button>
        <button id="save-settings" class="btn-primary rounded-full px-6 py-2.5 text-sm font-semibold">Save changes</button>
      </div>
    </div>
  </div>

  <!-- Project edit modal -->
  <div id="project-modal" class="hidden fixed inset-0 z-[60] modal-backdrop p-4 flex items-center justify-center">
    <div class="modal-panel rounded-2xl w-full max-w-md p-6">
      <div class="flex justify-between items-center mb-5">
        <h3 class="display font-bold text-xl">Edit project</h3>
        <button id="close-project" class="btn-ghost rounded-full w-9 h-9">✕</button>
      </div>
      <label class="block text-xs muted mb-4">Project title<input id="project-title" class="field mt-2"></label>
      <label class="block text-xs muted mb-5">Short description<input id="project-description" class="field mt-2"></label>
      <div class="flex justify-end gap-2">
        <button id="delete-project" class="btn-ghost rounded-full px-4 py-2 text-sm mr-auto">Delete</button>
        <button id="save-project" class="btn-primary rounded-full px-5 py-2 text-sm font-semibold">Save project</button>
      </div>
    </div>
  </div>

  <div id="toast" class="toast fixed bottom-5 left-1/2 -translate-x-1/2 z-[80] glass rounded-full px-5 py-3 text-sm shadow-xl">Saved successfully</div>

  <script>
    /* -------------------------------------------------------
       VISIONL — simple browser-based portfolio + customization
       Images/settings stay in this browser (IndexedDB).
       ------------------------------------------------------- */
    // Replace with your WhatsApp number: country code + number, no + or spaces.
    // Sri Lanka example: 94771234567
    const WHATSAPP_NUMBER = '94754361469';
  
    const WHATSAPP_MESSAGE = "Hello VisionLk, I'd like to know more about your services.";
    document.getElementById('whatsapp-button').href =
      `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(WHATSAPP_MESSAGE)}`;

    const DB_NAME = 'visionl-studio-db';
    const STORE = 'assets';
    let db;
    let currentTheme = 'dark';
    let editingProjectId = null;
    let backgroundAssetId = null;
    let logoAssetId = null;
    const objectUrls = new Map();

    const defaults = {
      name: 'VISIONL',
      tagline: 'Creative digital studio',
      hero: 'We make brands\\nimpossible to ignore.',
      heroDesc: 'Strategy, content and design for businesses ready to make their mark. We turn bold ideas into meaningful digital experiences.',
      services: 'Creative thinking. Real-world impact.',
      work: 'Selected work',
      about: 'VisionL is a creative digital marketing studio built around one simple belief: the best work happens when clear thinking meets bold creativity. We partner with ambitious businesses to shape their story and bring it to life online.',
      email: 'hello@visionl.lk',
      footer: 'Independent minds. Creative outcomes.',
      theme: 'dark'
    };

    const $ = id => document.getElementById(id);

    function openDatabase() {
      return new Promise((resolve, reject) => {
        const request = indexedDB.open(DB_NAME, 1);
        request.onupgradeneeded = () => {
          const database = request.result;
          if (!database.objectStoreNames.contains(STORE)) database.createObjectStore(STORE, { keyPath: 'id' });
        };
        request.onsuccess = () => resolve(request.result);
        request.onerror = () => reject(request.error);
      });
    }

    function putAsset(id, blob) {
      return new Promise((resolve, reject) => {
        const tx = db.transaction(STORE, 'readwrite');
        tx.objectStore(STORE).put({ id, blob });
        tx.oncomplete = resolve;
        tx.onerror = () => reject(tx.error);
      });
    }

    function getAsset(id) {
      return new Promise((resolve, reject) => {
        const req = db.transaction(STORE, 'readonly').objectStore(STORE).get(id);
        req.onsuccess = () => resolve(req.result ? req.result.blob : null);
        req.onerror = () => reject(req.error);
      });
    }

    function deleteAsset(id) {
      return new Promise(resolve => {
        const tx = db.transaction(STORE, 'readwrite');
        tx.objectStore(STORE).delete(id);
        tx.oncomplete = resolve;
      });
    }

    function readData(key, fallback) {
      try { return JSON.parse(localStorage.getItem(key)) ?? fallback; }
      catch { return fallback; }
    }
    function writeData(key, value) { localStorage.setItem(key, JSON.stringify(value)); }
    function getProjects() { return readData('visionl-projects', []); }

    function makeId(prefix='asset') {
      return prefix + '-' + Date.now() + '-' + Math.random().toString(36).slice(2,8);
    }

    async function assetUrl(id) {
      if (!id) return '';
      if (objectUrls.has(id)) return objectUrls.get(id);
      const blob = await getAsset(id);
      if (!blob) return '';
      const url = URL.createObjectURL(blob);
      objectUrls.set(id, url);
      return url;
    }

    function setTheme(theme) {
      currentTheme = theme;
      const root = document.documentElement;
      const palettes = {
        dark: { page:'#101010', surface:'#191919', surface2:'#222222', text:'#f4f4f4', muted:'#a2a2a2', line:'rgba(255,255,255,.12)', overlay:'rgba(8,8,8,.72)' },
        light: { page:'#f2f2f2', surface:'#ffffff', surface2:'#e9e9e9', text:'#171717', muted:'#707070', line:'rgba(0,0,0,.13)', overlay:'rgba(245,245,245,.80)' },
        grey: { page:'#777777', surface:'#858585', surface2:'#969696', text:'#101010', muted:'#303030', line:'rgba(0,0,0,.18)', overlay:'rgba(95,95,95,.78)' }
      };
      const p = palettes[theme] || palettes.dark;
      Object.entries(p).forEach(([key,value]) => root.style.setProperty('--' + key, value));
      document.querySelectorAll('.theme-choice').forEach(b => b.style.outline = b.dataset.theme === theme ? '1px solid var(--text)' : 'none');
    }

    function applyText(s) {
      $('brand-name').textContent = s.name || defaults.name;
      $('brand-tagline-small').textContent = s.tagline || defaults.tagline;
      $('brand-monogram').textContent = (s.name || defaults.name).trim().charAt(0).toUpperCase() + '.';
      $('hero-title').innerHTML = escapeHtml(s.hero || defaults.hero).replace(/\\n/g, '<br>').replace('impossible to ignore.', '<span class="muted">impossible to ignore.</span>');
      $('hero-description').textContent = s.heroDesc || defaults.heroDesc;
      $('services-title').textContent = s.services || defaults.services;
      $('work-title').textContent = (s.work || defaults.work) + '.';
      $('about-description').textContent = s.about || defaults.about;
      $('contact-link').href = 'mailto:' + (s.email || defaults.email);
      $('contact-link').innerHTML = escapeHtml(s.email || defaults.email) + ' <span>↗</span>';
      $('footer-note').textContent = s.footer || defaults.footer;
      $('footer-copy').textContent = '© ' + new Date().getFullYear() + ' ' + (s.name || defaults.name).toUpperCase() + '. ALL RIGHTS RESERVED.';
      setTheme(s.theme || defaults.theme);
    }

    function escapeHtml(value) {
      return String(value).replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
    }

    async function applyBrandAssets() {
      const settings = readData('visionl-settings', defaults);
      logoAssetId = settings.logoId || null;
      backgroundAssetId = settings.backgroundId || null;
      const logo = $('brand-logo');
      const logoUrl = await assetUrl(logoAssetId);
      if (logoUrl) {
        logo.src = logoUrl; logo.classList.remove('hidden'); $('brand-monogram').classList.add('hidden');
      } else {
        logo.classList.add('hidden'); $('brand-monogram').classList.remove('hidden');
      }
      const bgUrl = await assetUrl(backgroundAssetId);
      document.body.style.backgroundImage = bgUrl ? `url("${bgUrl}")` : 'none';
    }

    async function loadAll() {
      const settings = readData('visionl-settings', defaults);
      applyText({ ...defaults, ...settings });
      await applyBrandAssets();
      await renderProjects();
    }

    function showToast(message) {
      $('toast').textContent = message;
      $('toast').classList.add('show');
      clearTimeout(showToast.timer);
      showToast.timer = setTimeout(() => $('toast').classList.remove('show'), 2200);
    }

    function openSettings() {
      const s = { ...defaults, ...readData('visionl-settings', {}) };
      $('setting-name').value = s.name;
      $('setting-tagline').value = s.tagline;
      $('setting-hero').value = s.hero;
      $('setting-hero-desc').value = s.heroDesc;
      $('setting-services').value = s.services;
      $('setting-work').value = s.work;
      $('setting-about').value = s.about;
      $('setting-email').value = s.email;
      $('setting-footer').value = s.footer;
      setTheme(s.theme || 'dark');
      $('settings-modal').classList.remove('hidden');
      document.body.style.overflow = 'hidden';
    }

    function closeSettings() {
      $('settings-modal').classList.add('hidden');
      document.body.style.overflow = '';
    }

    async function saveSettings() {
      const old = readData('visionl-settings', defaults);
      const s = {
        ...old,
        name: $('setting-name').value.trim() || defaults.name,
        tagline: $('setting-tagline').value.trim() || defaults.tagline,
        hero: $('setting-hero').value.trim() || defaults.hero,
        heroDesc: $('setting-hero-desc').value.trim() || defaults.heroDesc,
        services: $('setting-services').value.trim() || defaults.services,
        work: $('setting-work').value.trim() || defaults.work,
        about: $('setting-about').value.trim() || defaults.about,
        email: $('setting-email').value.trim() || defaults.email,
        footer: $('setting-footer').value.trim() || defaults.footer,
        theme: currentTheme
      };

      const logoFile = $('setting-logo').files[0];
      const bgFile = $('setting-background').files[0];

      if (logoFile) {
        const id = makeId('logo');
        await putAsset(id, logoFile);
        if (old.logoId) await deleteAsset(old.logoId);
        s.logoId = id;
      }
      if (bgFile) {
        const id = makeId('background');
        await putAsset(id, bgFile);
        if (old.backgroundId) await deleteAsset(old.backgroundId);
        s.backgroundId = id;
      }

      writeData('visionl-settings', s);
      await loadAll();
      $('setting-logo').value = '';
      $('setting-background').value = '';
      closeSettings();
      showToast('Your website changes have been saved.');
    }

    function resetSettings() {
      const existing = readData('visionl-settings', {});
      const reset = { ...defaults, logoId: existing.logoId || null, backgroundId: existing.backgroundId || null };
      writeData('visionl-settings', reset);
      openSettings();
      showToast('Text and theme reset. Your logo and background were kept.');
    }

    async function removeBackground() {
      const s = readData('visionl-settings', defaults);
      if (s.backgroundId) await deleteAsset(s.backgroundId);
      s.backgroundId = null;
      writeData('visionl-settings', s);
      backgroundAssetId = null;
      document.body.style.backgroundImage = 'none';
      showToast('Background image removed.');
    }

    async function addProjects(files) {
      const projects = getProjects();
      for (const file of files) {
        if (!file.type.startsWith('image/')) continue;
        const id = makeId('project');
        await putAsset(id, file);
        projects.unshift({
          id, title: file.name.replace(/\.[^/.]+$/, ''),
          description: 'Add a short description for this project.'
        });
      }
      writeData('visionl-projects', projects);
      await renderProjects();
      showToast('Images added to your portfolio.');
      $('image-upload').value = '';
    }

    async function renderProjects() {
      const gallery = $('gallery');
      const empty = $('empty-gallery');
      gallery.innerHTML = '';
      const projects = getProjects();
      empty.classList.toggle('hidden', projects.length > 0);

      for (const project of projects) {
        const url = await assetUrl(project.id);
        const card = document.createElement('article');
        card.className = 'work-card group overflow-hidden rounded-2xl border line';
        const imageWrap = document.createElement('div');
        imageWrap.className = 'aspect-[4/3] overflow-hidden bg-black/10';
        const img = document.createElement('img');
        img.src = url; img.alt = project.title;
        img.className = 'w-full h-full object-cover';
        imageWrap.appendChild(img);

        const details = document.createElement('div');
        details.className = 'p-5 flex justify-between items-start gap-4';
        const textWrap = document.createElement('div');
        const title = document.createElement('h3');
        title.className = 'font-semibold text-base';
        title.textContent = project.title;
        const desc = document.createElement('p');
        desc.className = 'muted text-xs mt-2 leading-5';
        desc.textContent = project.description;
        textWrap.append(title, desc);

        const edit = document.createElement('button');
        edit.className = 'work-arrow btn-ghost rounded-full w-9 h-9 shrink-0';
        edit.setAttribute('aria-label', 'Edit ' + project.title);
        edit.textContent = '↗';
        edit.addEventListener('click', () => openProjectEditor(project.id));
        details.append(textWrap, edit);
        card.append(imageWrap, details);
        gallery.appendChild(card);
      }
    }

    function openProjectEditor(id) {
      const project = getProjects().find(p => p.id === id);
      if (!project) return;
      editingProjectId = id;
      $('project-title').value = project.title;
      $('project-description').value = project.description;
      $('project-modal').classList.remove('hidden');
    }

    function closeProjectEditor() {
      $('project-modal').classList.add('hidden');
      editingProjectId = null;
    }

    async function saveProjectEditor() {
      const projects = getProjects();
      const project = projects.find(p => p.id === editingProjectId);
      if (!project) return;
      project.title = $('project-title').value.trim() || 'Untitled project';
      project.description = $('project-description').value.trim();
      writeData('visionl-projects', projects);
      closeProjectEditor();
      await renderProjects();
      showToast('Project updated.');
    }

    async function deleteProject() {
      if (!editingProjectId || !confirm('Delete this project image?')) return;
      const projects = getProjects();
      const remaining = projects.filter(p => p.id !== editingProjectId);
      await deleteAsset(editingProjectId);
      objectUrls.delete(editingProjectId);
      writeData('visionl-projects', remaining);
      closeProjectEditor();
      await renderProjects();
      showToast('Project deleted.');
    }

    // Event listeners
    $('open-settings').addEventListener('click', openSettings);
    $('close-settings').addEventListener('click', closeSettings);
    $('cancel-settings').addEventListener('click', closeSettings);
    $('save-settings').addEventListener('click', saveSettings);
    $('reset-settings').addEventListener('click', resetSettings);
    $('remove-background').addEventListener('click', removeBackground);
    $('settings-modal').addEventListener('click', e => { if (e.target === $('settings-modal')) closeSettings(); });
    document.querySelectorAll('.theme-choice').forEach(button => button.addEventListener('click', () => setTheme(button.dataset.theme)));
    $('image-upload').addEventListener('change', e => addProjects(e.target.files));
    $('close-project').addEventListener('click', closeProjectEditor);
    $('save-project').addEventListener('click', saveProjectEditor);
    $('delete-project').addEventListener('click', deleteProject);

    // Escape key closes dialogs
    document.addEventListener('keydown', e => {
      if (e.key === 'Escape') { closeSettings(); closeProjectEditor(); }
    });

    (async function start() {
      try {
        db = await openDatabase();
        await loadAll();
      } catch (error) {
        console.error(error);
        alert('Could not start the portfolio storage. Please open this page in a modern browser with site storage enabled.');
      }
    })();
  </script>
</body>
</html>
