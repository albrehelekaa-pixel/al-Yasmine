<!DOCTYPE html>
<html lang="en" dir="ltr" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>الياسمين — AL-YASMIN | Authentic Syrian &amp; Wood-Fired Dining</title>

  <!-- Google Fonts: Cormorant Garamond (Editorial Serif), Plus Jakarta Sans (Clean Modern Sans), Amiri, Cairo & IBM Plex Sans Arabic (Arabic Pairing) -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cairo:wght@600;700&family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=IBM+Plex+Sans+Arabic:wght@300;400;500;600&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            alabaster: '#F7F4EF',
            warmstone: '#ECE6DC',
            espresso: '#171513',
            slatebrown: '#5E574F',
            terracotta: '#A66A46',
            hairline: '#D8CFC2',
          },
          fontFamily: {
            serif: ['"Cormorant Garamond"', '"Amiri"', 'Georgia', 'serif'],
            sans: ['"Plus Jakarta Sans"', '"IBM Plex Sans Arabic"', 'system-ui', 'sans-serif'],
          },
          letterSpacing: {
            editorial: '0.18em',
          }
        }
      }
    };
  </script>
  <style>
    /* Refined Arabic RTL typography & script integrity */
    [dir="rtl"] body {
      font-family: "IBM Plex Sans Arabic", system-ui, sans-serif;
    }
    [dir="rtl"] .font-serif {
      font-family: "Amiri", Georgia, serif;
    }
    [dir="rtl"] .hero-ar-title {
      font-family: "Cairo", "IBM Plex Sans Arabic", sans-serif;
      font-weight: 700;
      line-height: 1.25;
    }
    [dir="rtl"] * {
      letter-spacing: 0 !important;
    }
    /* Mobile-native polish: hide horizontal scrollbars & smooth touch scrolling */
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
      -webkit-overflow-scrolling: touch;
    }
    /* Prevent tap highlight flicker on mobile */
    button, a {
      -webkit-tap-highlight-color: transparent;
    }
  </style>
</head>
<body class="bg-alabaster text-espresso font-sans antialiased selection:bg-terracotta/20 selection:text-espresso overflow-x-hidden pb-20 lg:pb-0">

  <!-- ===================================================================== -->
  <!-- 1. STICKY NAVIGATION HEADER                                           -->
  <!-- ===================================================================== -->
  <header id="site-header" class="fixed top-0 inset-x-0 z-40 transition-all duration-300 border-b border-alabaster/15 bg-transparent text-alabaster">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-10 h-16 sm:h-20 flex items-center justify-between gap-2 sm:gap-4">
      <!-- Brand Wordmark -->
      <a href="#top" class="flex items-center gap-2 group focus:outline-none shrink-0">
        <span data-i18n="brand" class="font-serif text-xl sm:text-3xl tracking-[0.2em] font-medium uppercase">الياسمين</span>
      </a>

      <!-- Desktop Navigation -->
      <nav aria-label="Primary Navigation" class="hidden lg:flex items-center gap-9 text-xs uppercase tracking-[0.16em] font-medium">
        <a href="#menu" data-i18n="nav_menu" class="hover:text-terracotta transition-colors py-2">Menu</a>
        <a href="#reservations" data-i18n="nav_reservations" class="hover:text-terracotta transition-colors py-2">Reservations</a>
        <a href="#story" data-i18n="nav_story" class="hover:text-terracotta transition-colors py-2">Story</a>
        <a href="#gallery" data-i18n="nav_gallery" class="hover:text-terracotta transition-colors py-2">Gallery</a>
        <a href="#visit" data-i18n="nav_visit" class="hover:text-terracotta transition-colors py-2">Visit &amp; Hours</a>
      </nav>

      <!-- Action Controls -->
      <div class="flex items-center gap-2 sm:gap-3">
        <!-- Language Toggle Button (EN / العربية) -->
        <button
          id="lang-toggle-btn"
          type="button"
          onclick="toggleLanguage()"
          aria-label="Switch language"
          class="inline-flex items-center justify-center min-h-[40px] px-3 py-2 rounded-md border border-current/25 hover:border-terracotta hover:text-terracotta transition-colors text-xs font-medium cursor-pointer"
        >
          العربية
        </button>

        <!-- Cart / Order Bag Button -->
        <button
          id="nav-cart-btn"
          type="button"
          onclick="openCartDrawer()"
          aria-label="Open order bag"
          class="relative inline-flex items-center gap-2 min-h-[40px] px-3 sm:px-3.5 py-2 rounded-md border border-current/25 hover:border-terracotta hover:text-terracotta transition-colors text-xs uppercase tracking-[0.14em] font-medium cursor-pointer"
        >
          <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 7h12l-1 13H7L6 7z" />
            <path stroke-linecap="round" stroke-linejoin="round" d="M9 7a3 3 0 016 0" />
          </svg>
          <span data-i18n="nav_order" class="hidden sm:inline">Order</span>
          <span id="nav-cart-badge" class="hidden items-center justify-center min-w-[20px] h-5 px-1.5 rounded-full bg-terracotta text-alabaster text-[11px] font-semibold tabular-nums">0</span>
        </button>

        <!-- Book a Table CTA -->
        <button
          type="button"
          onclick="openReservationModal()"
          data-i18n="nav_book"
          class="hidden sm:inline-flex items-center justify-center px-5 py-2.5 rounded-md bg-terracotta text-alabaster hover:bg-[#8E5838] transition-colors text-xs uppercase tracking-[0.15em] font-medium cursor-pointer"
        >
          Book a Table
        </button>

        <!-- Mobile Menu Toggle -->
        <button
          id="mobile-menu-open"
          type="button"
          onclick="openMobileMenu()"
          aria-label="Open menu"
          class="lg:hidden inline-flex items-center justify-center w-10 h-10 rounded-md border border-current/25 hover:border-terracotta transition-colors cursor-pointer"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 7h16M4 12h16M4 17h16" />
          </svg>
        </button>
      </div>
    </div>
  </header>

  <!-- Mobile Navigation Drawer -->
  <div id="mobile-drawer" class="fixed inset-0 z-50 hidden" aria-hidden="true">
    <div id="mobile-drawer-backdrop" onclick="closeMobileMenu()" class="absolute inset-0 bg-espresso/60 backdrop-blur-sm opacity-0 transition-opacity duration-300"></div>
    <aside id="mobile-drawer-panel" class="absolute top-0 right-0 h-full w-full max-w-xs bg-alabaster text-espresso border-l border-hairline translate-x-full transition-transform duration-300 flex flex-col justify-between p-6 overflow-y-auto">
      <div>
        <div class="flex items-center justify-between pb-6 border-b border-hairline">
          <span data-i18n="brand" class="font-serif text-2xl tracking-[0.2em] uppercase">الياسمين</span>
          <button type="button" onclick="closeMobileMenu()" aria-label="Close navigation menu" class="w-10 h-10 rounded-md border border-hairline flex items-center justify-center hover:border-espresso transition-colors cursor-pointer">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>

        <nav class="mt-8 flex flex-col gap-2">
          <a href="#menu" onclick="closeMobileMenu()" data-i18n="mob_menu" class="py-3 px-2 font-serif text-2xl border-b border-hairline/60 hover:text-terracotta transition-colors">Menu &amp; Ordering</a>
          <a href="#reservations" onclick="closeMobileMenu()" data-i18n="nav_reservations" class="py-3 px-2 font-serif text-2xl border-b border-hairline/60 hover:text-terracotta transition-colors">Reservations</a>
          <a href="#story" onclick="closeMobileMenu()" data-i18n="mob_story" class="py-3 px-2 font-serif text-2xl border-b border-hairline/60 hover:text-terracotta transition-colors">Our Story</a>
          <a href="#gallery" onclick="closeMobileMenu()" data-i18n="nav_gallery" class="py-3 px-2 font-serif text-2xl border-b border-hairline/60 hover:text-terracotta transition-colors">Gallery</a>
          <a href="#visit" onclick="closeMobileMenu()" data-i18n="nav_visit" class="py-3 px-2 font-serif text-2xl hover:text-terracotta transition-colors">Visit &amp; Hours</a>
        </nav>

        <div class="mt-8 flex flex-col gap-3">
          <button type="button" onclick="closeMobileMenu(); openReservationModal();" data-i18n="hero_reserve" class="w-full py-3.5 px-5 rounded-md bg-espresso text-alabaster hover:bg-terracotta transition-colors text-xs uppercase tracking-[0.16em] font-medium cursor-pointer">
            Reserve a Table
          </button>
          <button type="button" onclick="closeMobileMenu(); openCartDrawer();" class="w-full py-3.5 px-5 rounded-md border border-espresso text-espresso hover:bg-warmstone transition-colors text-xs uppercase tracking-[0.16em] font-medium cursor-pointer">
            <span data-i18n="mob_view_bag">View Order Bag</span> (<span id="mobile-cart-count">0</span>)
          </button>
          <button type="button" id="mobile-lang-toggle-btn" onclick="toggleLanguage()" class="w-full py-3 px-5 rounded-md border border-hairline text-slatebrown hover:border-espresso hover:text-espresso transition-colors text-xs font-medium cursor-pointer">
            التبديل إلى العربية
          </button>
        </div>
      </div>

      <div class="pt-6 mt-6 border-t border-hairline text-xs text-slatebrown space-y-1.5">
        <p data-i18n="address_short" class="uppercase tracking-[0.14em] text-espresso font-medium">Keizersgracht 412, Amsterdam</p>
        <p data-i18n="mob_hours">Tue – Sun · Lunch &amp; Wood-Fired Dinner</p>
        <a href="tel:+31205550194" dir="ltr" class="inline-block text-terracotta hover:underline">+31 20 555 0194</a>
      </div>
    </aside>
  </div>

  <!-- ===================================================================== -->
  <!-- 2. EDITORIAL HERO SECTION                                             -->
  <!-- ===================================================================== -->
  <section id="top" class="relative min-h-[100svh] flex flex-col justify-between bg-espresso text-alabaster overflow-hidden">
    <!-- Full-bleed Culinary Atmosphere Image -->
    <div class="absolute inset-0">
      <img
        src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=2000&q=85"
        onerror="this.onerror=null;this.src='https://placehold.co/1920x1080/171513/ECE6DC?text=AL-YASMIN+Dining+Room';"
        alt="Warm candlelit interior of Al-Yasmin Syrian dining room"
        class="w-full h-full object-cover object-center scale-[1.02]"
      />
      <!-- Refined editorial gradient scrim -->
      <div class="absolute inset-0 bg-gradient-to-b from-espresso/75 via-espresso/50 to-espresso/85"></div>
      <div class="absolute inset-0 ltr:bg-gradient-to-r rtl:bg-gradient-to-l from-espresso/75 via-espresso/30 to-transparent"></div>
    </div>

    <!-- Top spacer for fixed nav -->
    <div class="h-16 sm:h-24 relative z-10"></div>

    <!-- Asymmetric Editorial Typography -->
    <div class="relative z-10 max-w-7xl mx-auto w-full px-4 sm:px-6 lg:px-10 py-10 sm:py-20">
      <div class="max-w-3xl">
        <div class="inline-flex items-center gap-3 mb-4 sm:mb-6">
          <span class="w-6 sm:w-8 h-px bg-terracotta"></span>
          <p data-i18n="hero_eyebrow" class="text-[11px] sm:text-xs uppercase tracking-[0.22em] text-warmstone/90 font-medium">
            Amsterdam · Keizersgracht 412 · Est. 2019
          </p>
        </div>

        <h1 data-i18n-html="hero_title" class="hero-ar-title font-serif text-[2.6rem] sm:text-6xl lg:text-[5.25rem] leading-[1.08] font-normal tracking-tight text-alabaster">
          Live-Fire Hearth,<br />
          <span class="italic font-normal text-warmstone">Mediterranean</span> Soul.
        </h1>

        <p data-i18n="hero_subtitle" class="mt-5 sm:mt-8 max-w-xl text-sm sm:text-lg text-warmstone/85 font-light leading-relaxed">
          Seasonal coastal produce, hand-rolled pasta, and whole fish roasted over seasoned Dutch oak embers—served in an intimate canal-side dining room.
        </p>

        <div class="mt-7 sm:mt-11 flex flex-col sm:flex-row items-stretch sm:items-center gap-3 sm:gap-4">
          <button
            type="button"
            onclick="openReservationModal()"
            data-i18n="hero_reserve"
            class="w-full sm:w-auto px-7 py-4 rounded-lg sm:rounded-md bg-terracotta text-alabaster hover:bg-[#8E5838] transition-all text-xs uppercase tracking-[0.18em] font-medium cursor-pointer text-center"
          >
            Reserve a Table
          </button>
          <a
            href="#menu"
            data-i18n="hero_explore"
            class="w-full sm:w-auto px-7 py-4 rounded-lg sm:rounded-md border border-alabaster/40 text-alabaster hover:bg-alabaster hover:text-espresso transition-all text-xs uppercase tracking-[0.18em] font-medium text-center"
          >
            Explore Menu
          </a>
        </div>
      </div>
    </div>

    <!-- Subtle Bottom Info Bar -->
    <div class="relative z-10 border-t border-alabaster/15 bg-espresso/45 backdrop-blur-sm">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-10 py-4 flex flex-col sm:flex-row sm:items-center justify-between gap-3 text-xs text-warmstone/85">
        <div class="flex flex-wrap items-center gap-x-6 gap-y-2">
          <div class="flex items-center gap-2">
            <span id="hero-open-dot" class="w-2 h-2 rounded-full bg-emerald-400"></span>
            <span id="hero-hours-text" class="tracking-wide">Today: 12:00 – 15:00 &amp; 17:30 – 22:30</span>
          </div>
          <span class="hidden sm:inline text-alabaster/30">|</span>
          <span data-i18n="address_full" class="tracking-wide">Keizersgracht 412, 1016 GC Amsterdam</span>
        </div>
        <a href="#menu" class="inline-flex items-center gap-2 uppercase tracking-[0.18em] text-[11px] text-warmstone/75 hover:text-alabaster transition-colors">
          <span data-i18n="hero_scroll">Scroll to Discover</span>
          <svg class="w-3.5 h-3.5 animate-bounce" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </a>
      </div>
    </div>
  </section>

  <!-- Subtle Press & Recognition Strip -->
  <section class="bg-warmstone border-b border-hairline">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-10 py-6">
      <div class="flex flex-col md:flex-row items-center justify-between gap-4 text-center md:text-start">
        <span data-i18n="press_label" class="text-[11px] uppercase tracking-[0.2em] text-slatebrown font-medium">Recognized By</span>
        <div data-i18n-html="press_items" class="flex flex-wrap items-center justify-center gap-x-10 gap-y-3 font-serif text-lg sm:text-xl text-espresso/85 tracking-wide">
          <span>Michelin Guide <span class="italic text-slatebrown text-base">Selected 2025</span></span>
          <span class="hidden sm:inline text-hairline">·</span>
          <span>Wine Spectator <span class="italic text-slatebrown text-base">Award of Excellence</span></span>
          <span class="hidden sm:inline text-hairline">·</span>
          <span>Architectural Digest <span class="italic text-slatebrown text-base">Great Design</span></span>
        </div>
      </div>
    </div>
  </section>

  <!-- ===================================================================== -->
  <!-- 3. INTERACTIVE MENU & ONLINE ORDERING SYSTEM                          -->
  <!-- ===================================================================== -->
  <section id="menu" class="py-20 sm:py-28 bg-alabaster">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-10">
      <!-- Editorial Header -->
      <div class="reveal opacity-0 translate-y-6 transition-all duration-700 flex flex-col lg:flex-row lg:items-end justify-between gap-8 pb-10 border-b border-hairline">
        <div class="max-w-2xl">
          <p data-i18n="menu_eyebrow" class="text-xs uppercase tracking-[0.2em] text-terracotta font-medium mb-3">Seasonal Kitchen &amp; Cellar</p>
          <h2 data-i18n="menu_title" class="font-serif text-4xl sm:text-5xl lg:text-6xl font-normal tracking-tight text-espresso">
            The Autumn Menu
          </h2>
          <p data-i18n="menu_desc" class="mt-4 text-slatebrown text-sm sm:text-base leading-relaxed">
            Crafted daily around our custom oak-fired hearth. Dine in with us or order freshly prepared dishes for pickup and local delivery.
          </p>
        </div>

        <!-- Dietary Filter Toggles -->
        <div class="flex flex-wrap items-center gap-2" role="group" aria-label="Dietary filters">
          <span data-i18n="filter_label" class="text-[11px] uppercase tracking-[0.16em] text-slatebrown me-1">Filter:</span>
          <button type="button" data-diet="all" onclick="setDietaryFilter('all')" data-i18n="filter_all" class="diet-btn px-3.5 py-2 rounded-md text-xs font-medium border border-espresso bg-espresso text-alabaster transition-colors cursor-pointer">
            All Dishes
          </button>
          <button type="button" data-diet="V" onclick="setDietaryFilter('V')" data-i18n="filter_v" class="diet-btn px-3.5 py-2 rounded-md text-xs font-medium border border-hairline bg-transparent text-slatebrown hover:border-espresso hover:text-espresso transition-colors cursor-pointer">
            Vegetarian (V)
          </button>
          <button type="button" data-diet="GF" onclick="setDietaryFilter('GF')" data-i18n="filter_gf" class="diet-btn px-3.5 py-2 rounded-md text-xs font-medium border border-hairline bg-transparent text-slatebrown hover:border-espresso hover:text-espresso transition-colors cursor-pointer">
            Gluten-Free (GF)
          </button>
        </div>
      </div>

      <!-- Category Tabs -->
      <div class="mt-7 sm:mt-8 flex items-center gap-2 overflow-x-auto no-scrollbar snap-x pb-3 border-b border-hairline" role="tablist" aria-label="Menu Categories">
        <button type="button" role="tab" data-category="starters" onclick="setCategory('starters')" data-i18n="cat_starters" class="cat-tab snap-start shrink-0 min-h-[42px] px-4 py-2.5 rounded-full sm:rounded-md text-xs uppercase tracking-[0.16em] font-medium bg-warmstone text-espresso border border-espresso/20 transition-colors cursor-pointer">
          Starters
        </button>
        <button type="button" role="tab" data-category="mains" onclick="setCategory('mains')" data-i18n="cat_mains" class="cat-tab snap-start shrink-0 min-h-[42px] px-4 py-2.5 rounded-full sm:rounded-md text-xs uppercase tracking-[0.16em] font-medium text-slatebrown hover:text-espresso border border-transparent transition-colors cursor-pointer">
          Wood-Fired Mains
        </button>
        <button type="button" role="tab" data-category="pasta" onclick="setCategory('pasta')" data-i18n="cat_pasta" class="cat-tab snap-start shrink-0 min-h-[42px] px-4 py-2.5 rounded-full sm:rounded-md text-xs uppercase tracking-[0.16em] font-medium text-slatebrown hover:text-espresso border border-transparent transi
