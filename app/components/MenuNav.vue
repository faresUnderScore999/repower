<template>
  <header class="header">
    <!-- Animated Background -->
    <div class="header-background">
      <div class="energy-pulse"></div>
    </div>

    <div class="container">
      <!-- Logo Section -->
      <div class="header-logo">
        <NuxtLink to="/" class="logo-link">
          <div class="logo-mark">RP</div>
          <span class="logo-text">RePower</span>
          <span class="visually-hidden">RePower - Human Energy Solutions</span>
        </NuxtLink>
      </div>

      <!-- Navigation Actions -->
      <div class="header-actions">
        <!-- Newsletter Signup -->
        <div class="newsletter-signup">
          <div class="signup-form">
            <input 
              type="email" 
              placeholder="Join the energy movement"
              class="signup-input"
            >
            <button class="signup-button">Sign up</button>
          </div>
        </div>

        <!-- Donate Button -->
        <div class="donate-section">
          <NuxtLink to="/donate" class="donate-button">Support Us</NuxtLink>
        </div>

        <!-- Search -->
        <div class="search-section">
          <button class="search-toggle" @click="toggleSearch">
            <svg class="search-icon" viewBox="0 0 24 24" width="20" height="20">
              <path fill="currentColor" d="M15.5 14h-.79l-.28-.27A6.471 6.471 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"/>
            </svg>
            <span class="visually-hidden">Search</span>
          </button>
          
          <div class="search-container" :class="{ 'search-open': isSearchOpen }">
            <div class="search-inner">
              <form @submit.prevent="handleSearch">
                <label for="site-search" class="visually-hidden">Search the site</label>
                <input 
                  id="site-search"
                  type="text" 
                  v-model="searchQuery"
                  placeholder="Search RePower..."
                  class="search-input"
                >
                <button type="submit" class="search-submit">Search</button>
              </form>
            </div>
          </div>
        </div>

        <!-- Mobile Menu Toggle -->
        <div class="menu-section">
          <button class="menu-toggle" @click="toggleMenu">
            <span class="menu-text" :class="{ hidden: isMenuOpen }">MENU</span>
            <span class="close-text" :class="{ hidden: !isMenuOpen }">CLOSE</span>
            <div class="menu-bars" :class="{ active: isMenuOpen }">
              <span></span>
              <span></span>
              <span></span>
            </div>
          </button>
        </div>
      </div>

      <!-- Navigation Menu -->
      <nav class="main-navigation" :class="{ 'nav-open': isMenuOpen }">
        <ul class="nav-list">
          <li class="nav-item" v-for="item in navItems" :key="item.label">
            <NuxtLink 
              :to="item.path" 
              class="nav-link"
              @click="closeMenu"
            >
              {{ item.label }}
              <svg class="nav-arrow" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M8.59 16.34l4.58-4.59-4.58-4.59L10 5.75l6 6-6 6z"/>
              </svg>
            </NuxtLink>
          </li>
        </ul>

        <!-- Call to Action in Menu -->
        <div class="nav-cta">
          <div class="cta-visual">
            <div class="energy-dot"></div>
            <div class="energy-dot" style="animation-delay: 0.3s"></div>
            <div class="energy-dot" style="animation-delay: 0.6s"></div>
          </div>
          <div class="cta-content">
            <h5>Power from Human Energy</h5>
            <p>Join our mission to transform body heat into clean electricity</p>
            <NuxtLink to="/get-involved" class="cta-button" @click="closeMenu">
              Get Involved
            </NuxtLink>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup>
const isMenuOpen = ref(false)
const isSearchOpen = ref(false)
const searchQuery = ref('')

const navItems = [
  { label: 'Our Mission', path: '/' },
  { label: 'Power Skin Technology', path: '/technology' },
  { label: 'Get Involved', path: '/get-involved' },
  { label: 'Contact', path: '/contact' },
  { label: 'About', path: '/about' }
]

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
  if (isMenuOpen.value) {
    isSearchOpen.value = false
  }
}

const toggleSearch = () => {
  isSearchOpen.value = !isSearchOpen.value
  if (isSearchOpen.value) {
    isMenuOpen.value = false
  }
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const handleSearch = () => {
  if (searchQuery.value.trim()) {
    navigateTo(`/search?q=${encodeURIComponent(searchQuery.value)}`)
    isSearchOpen.value = false
    searchQuery.value = ''
  }
}
</script>

<style scoped>
.header {
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
  position: relative;
  z-index: 1000;
  overflow: hidden;
}

.header-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.energy-pulse {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(74, 124, 89, 0.1) 0%, transparent 70%);
  animation: pulseGlow 4s ease-in-out infinite;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  position: relative;
  z-index: 2;
}

/* Logo Styles */
.header-logo {
  padding: 15px 0;
}

.logo-link {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: white;
  font-weight: bold;
  font-size: 1.5rem;
  transition: all 0.3s ease;
}

.logo-link:hover {
  transform: translateY(-2px);
}

.logo-mark {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 12px;
  font-weight: 800;
  box-shadow: 0 4px 15px rgba(74, 124, 89, 0.3);
}

.logo-text {
  font-size: 1.4rem;
  font-weight: 700;
}

/* Header Actions */
.header-actions {
  display: flex;
  align-items: center;
  gap: 20px;
}

/* Newsletter Signup */
.newsletter-signup {
  display: none;
}

.signup-form {
  display: flex;
  gap: 8px;
}

.signup-input {
  padding: 10px 15px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 6px;
  font-size: 0.9rem;
  min-width: 200px;
  background: rgba(255, 255, 255, 0.1);
  color: white;
  backdrop-filter: blur(10px);
}

.signup-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.signup-button {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.signup-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(46, 204, 113, 0.4);
}

/* Donate Button */
.donate-button {
  background: linear-gradient(135deg, #e74c3c, #c0392b);
  color: white;
  padding: 12px 24px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(231, 76, 60, 0.3);
}

.donate-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(231, 76, 60, 0.4);
}

/* Search Section */
.search-section {
  position: relative;
}

.search-toggle {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  padding: 10px;
  cursor: pointer;
  color: white;
  border-radius: 6px;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.search-toggle:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.search-container {
  position: absolute;
  top: 100%;
  right: 0;
  background: rgba(10, 46, 56, 0.95);
  padding: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  border-radius: 12px;
  display: none;
  min-width: 300px;
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  margin-top: 10px;
}

.search-open .search-container {
  display: block;
  animation: slideDown 0.3s ease;
}

.search-inner form {
  display: flex;
  gap: 10px;
}

.search-input {
  flex: 1;
  padding: 12px 15px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 6px;
  background: rgba(255, 255, 255, 0.1);
  color: white;
}

.search-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.search-submit {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.search-submit:hover {
  transform: translateY(-2px);
}

/* Menu Toggle */
.menu-toggle {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  padding: 12px 16px;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 8px;
  color: white;
  font-weight: 600;
  border-radius: 6px;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.menu-toggle:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.menu-bars {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.menu-bars span {
  width: 20px;
  height: 2px;
  background: white;
  transition: all 0.3s ease;
}

.menu-bars.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.menu-bars.active span:nth-child(2) {
  opacity: 0;
}

.menu-bars.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

.hidden {
  display: none;
}

/* Navigation Menu */
.main-navigation {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  display: none;
  padding: 40px 0;
  backdrop-filter: blur(20px);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.nav-open {
  display: block;
  animation: slideDown 0.3s ease;
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0 0 40px 0;
}

.nav-item {
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.nav-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 30px;
  text-decoration: none;
  color: white;
  font-weight: 600;
  transition: all 0.3s ease;
  font-size: 1.1rem;
}

.nav-link:hover {
  background: rgba(255, 255, 255, 0.1);
  color: #4a7c59;
  padding-left: 40px;
}

.nav-arrow {
  transition: transform 0.3s ease;
}

.nav-link:hover .nav-arrow {
  transform: translateX(5px);
}

/* Navigation CTA */
.nav-cta {
  background: rgba(255, 255, 255, 0.05);
  margin: 0 30px;
  padding: 30px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  gap: 20px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
}

.cta-visual {
  position: relative;
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.energy-dot {
  width: 8px;
  height: 8px;
  background: #4a7c59;
  border-radius: 50%;
  position: absolute;
  animation: energyPulse 2s ease-in-out infinite;
}

.energy-dot:nth-child(1) { top: 20px; left: 20px; }
.energy-dot:nth-child(2) { top: 40px; right: 20px; }
.energy-dot:nth-child(3) { bottom: 20px; left: 40px; }

.cta-content h5 {
  margin: 0 0 8px 0;
  color: white;
  font-size: 1.2rem;
}

.cta-content p {
  margin: 0 0 20px 0;
  opacity: 0.9;
  font-size: 0.95rem;
}

.cta-button {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  padding: 12px 24px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  display: inline-block;
  transition: all 0.3s ease;
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(46, 204, 113, 0.4);
}

.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Animations */
@keyframes pulseGlow {
  0%, 100% { opacity: 0.3; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 0.6; transform: translate(-50%, -50%) scale(1.1); }
}

@keyframes slideDown {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes energyPulse {
  0%, 100% { transform: scale(1); opacity: 0.7; }
  50% { transform: scale(1.5); opacity: 1; }
}

/* Desktop Styles */
@media (min-width: 768px) {
  .newsletter-signup {
    display: block;
  }
  
  .menu-toggle .menu-text,
  .menu-toggle .close-text {
    display: none;
  }
}

@media (min-width: 1024px) {
  .main-navigation {
    position: static;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0;
    box-shadow: none;
    background: none;
    border-top: none;
  }
  
  .nav-list {
    display: flex;
    gap: 5px;
    margin: 0;
  }
  
  .nav-item {
    border-bottom: none;
  }
  
  .nav-link {
    padding: 25px 20px;
    border-radius: 6px;
    font-size: 1rem;
  }
  
  .nav-link:hover {
    padding-left: 20px;
    background: rgba(255, 255, 255, 0.1);
  }
  
  .nav-cta {
    display: none;
  }
  
  .menu-section {
    display: none;
  }
}

@media (max-width: 1023px) {
  .header-actions {
    gap: 15px;
  }
  
  .newsletter-signup {
    display: none;
  }
}
</style>