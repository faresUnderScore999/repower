<template>
  <div class="homepage">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-background">
        <div class="energy-orb"></div>
        <div class="energy-orb" style="--delay: 1.5s; --size: 120px; --x: 20%; --y: 70%;"></div>
        <div class="energy-orb" style="--delay: 2.5s; --size: 80px; --x: 80%; --y: 30%;"></div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title">
              <span class="title-line">POWERING A</span>
              <span class="title-line highlight">GREEN TOMORROW</span>
            </h1>
            
            <p class="hero-subtitle">
              RePower is an NGO supporting affordable and clean energy (SDG 7) for everyone. 
              We are developing wearable technology that generates electricity from the human body.
            </p>
            
            <div class="hero-actions">
              <NuxtLink to="/solution" class="btn btn-primary">
                <svg class="btn-icon" viewBox="0 0 24 24" width="20" height="20">
                  <path fill="currentColor" d="M9.4 16.6L4.8 12l4.6-4.6L8 6l-6 6 6 6 1.4-1.4zm5.2 0l4.6-4.6-4.6-4.6L16 6l6 6-6 6-1.4-1.4z"/>
                </svg>
                Our Solution
              </NuxtLink>
              <NuxtLink to="/donate" class="btn btn-secondary">
                <svg class="btn-icon" viewBox="0 0 24 24" width="20" height="20">
                  <path fill="currentColor" d="M12,21.35L10.55,20.03C5.4,15.36 2,12.27 2,8.5C2,5.41 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.08C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.41 22,8.5C22,12.27 18.6,15.36 13.45,20.03L12,21.35Z"/>
                </svg>
                Donate Now
              </NuxtLink>
            </div>
          </div>
          
          <div class="hero-visual">
            <div class="lightbulb-graphic">
              <div class="bulb">
                <div class="filament"></div>
                <div class="glow"></div>
              </div>
              <div class="leaves">
                <div class="leaf leaf-1"></div>
                <div class="leaf leaf-2"></div>
                <div class="leaf leaf-3"></div>
              </div>
              <div class="base"></div>
            </div>
          </div>
        </div>
        
        <div class="scroll-indicator">
          <span>Scroll to explore</span>
          <div class="arrow"></div>
        </div>
      </div>
    </section>

    <!-- Problem Section -->
    <section class="problem-section">
      <div class="container">
        <div class="section-header">
          <div class="section-icon problem-icon">
            <svg viewBox="0 0 24 24" width="40" height="40">
              <path fill="currentColor" d="M19.04,7.18C20.24,8.4 21,10.09 21,12C21,13.91 20.24,15.6 19.04,16.82L17.62,15.4C18.39,14.63 19,13.38 19,12C19,10.62 18.39,9.37 17.62,8.6L19.04,7.18M12,10A2,2 0 0,1 14,12A2,2 0 0,1 12,14A2,2 0 0,1 10,12A2,2 0 0,1 12,10M4.93,5.82C3.73,7.04 3,8.74 3,10.5C3,12.26 3.73,13.96 4.93,15.18L6.35,13.76C5.58,13 5,11.8 5,10.5C5,9.2 5.58,8 6.35,7.24L4.93,5.82M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4Z"/>
            </svg>
          </div>
          <h2>The Problem</h2>
        </div>
        
        <div class="problem-content">
          <div class="problem-text">
            <p class="problem-statement">
              Millions, especially in remote communities and low-income families, lack clean, reliable energy. 
              They must rely on harmful fossil fuels that pollute, harm health, and block development.
            </p>
            
            <div class="problem-stats">
              <div class="stat">
                <div class="stat-number">789M</div>
                <div class="stat-label">People without electricity</div>
              </div>
              <div class="stat">
                <div class="stat-number">2.6B</div>
                <div class="stat-label">Rely on polluting fuels</div>
              </div>
              <div class="stat">
                <div class="stat-number">4M</div>
                <div class="stat-label">Premature deaths annually</div>
              </div>
            </div>
          </div>
          
          <div class="problem-image">
            <div class="image-placeholder">
              <div class="community-silhouette">
                <div class="house"></div>
                <div class="house"></div>
                <div class="house"></div>
                <div class="smoke"></div>
              </div>
              <p>Remote community illustration</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Solution Section -->
    <section class="solution-section">
      <div class="container">
        <div class="section-header">
          <div class="section-icon solution-icon">
            <svg viewBox="0 0 24 24" width="40" height="40">
              <path fill="currentColor" d="M12,15A2,2 0 0,1 10,13C10,11.89 10.9,11 12,11A2,2 0 0,1 14,13A2,2 0 0,1 12,15M7,7C7,5.89 7.89,5 9,5A2,2 0 0,1 11,7A2,2 0 0,1 9,9C7.89,9 7,8.1 7,7M12,2C13.11,2 14,2.9 14,4C14,5.11 13.11,6 12,6C10.89,6 10,5.1 10,4C10,2.89 10.89,2 12,2M19,13C19,11.89 19.89,11 21,11A2,2 0 0,1 23,13A2,2 0 0,1 21,15C19.89,15 19,14.1 19,13M16.5,17.5C14.89,17.5 13.5,16.1 13.5,14.5C13.5,12.89 14.89,11.5 16.5,11.5C18.11,11.5 19.5,12.89 19.5,14.5C19.5,16.11 18.11,17.5 16.5,17.5M21,2C22.11,2 23,2.9 23,4C23,5.11 22.11,6 21,6C19.89,6 19,5.1 19,4C19,2.89 19.89,2 21,2M16.5,20.5C14.89,20.5 13.5,19.1 13.5,17.5C13.5,15.89 14.89,14.5 16.5,14.5C18.11,14.5 19.5,15.89 19.5,17.5C19.5,19.11 18.11,20.5 16.5,20.5M7.5,20.5C5.89,20.5 4.5,19.1 4.5,17.5C4.5,15.89 5.89,14.5 7.5,14.5C9.11,14.5 10.5,15.89 10.5,17.5C10.5,19.11 9.11,20.5 7.5,20.5M4.5,11.5C2.89,11.5 1.5,12.89 1.5,14.5C1.5,16.11 2.89,17.5 4.5,17.5C6.11,17.5 7.5,16.11 7.5,14.5C7.5,12.89 6.11,11.5 4.5,11.5Z"/>
            </svg>
          </div>
          <h2>Our Solution</h2>
        </div>
        
        <div class="solution-content">
          <div class="solution-visual">
      <img 
        src="/img2.png" 
        alt="Power Skin Technology"
        class="solution-image"
      />
    </div>
          
          <div class="solution-text">
            <p class="solution-statement">
              Our <strong>Power Skin</strong> patch is a wearable technology that captures energy from body heat and movement. 
              It converts this natural energy into clean electricity for small devices.
            </p>
            
            <div class="solution-features">
              <div class="feature">
                <div class="feature-icon">🔥</div>
                <div class="feature-content">
                  <h4>Body Heat Conversion</h4>
                  <p>Harnesses thermal energy from skin contact</p>
                </div>
              </div>
              
              <div class="feature">
                <div class="feature-icon">⚡</div>
                <div class="feature-content">
                  <h4>Movement Energy</h4>
                  <p>Captures kinetic energy from daily activities</p>
                </div>
              </div>
              
              <div class="feature">
                <div class="feature-icon">🔋</div>
                <div class="feature-content">
                  <h4>Clean Power</h4>
                  <p>Provides sustainable electricity for small devices</p>
                </div>
              </div>
            </div>
            
            <NuxtLink to="/technology" class="btn btn-outline">
              Learn How It Works
              <svg class="btn-arrow" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M4,11V13H16L10.5,18.5L11.92,19.92L19.84,12L11.92,4.08L10.5,5.5L16,11H4Z"/>
              </svg>
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- SDG Section -->
    <section class="sdg-section">
      <div class="container">
        <div class="sdg-content">
          <div class="sdg-badge-large">
            <div class="sdg-number">7</div>
            <div class="sdg-text">
              <span>Affordable & Clean Energy</span>
              <small>Sustainable Development Goal</small>
            </div>
          </div>
          
          <div class="sdg-mission">
            <h3>Our Commitment to SDG 7</h3>
            <p>
              We're dedicated to ensuring access to affordable, reliable, sustainable, 
              and modern energy for all through innovative wearable technology.
            </p>
            <div class="mission-values">
              <div class="value-pill">Innovation</div>
              <div class="value-pill">Sustainability</div>
              <div class="value-pill">Accessibility</div>
              <div class="value-pill">Empowerment</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Join Our Energy Revolution</h2>
          <p>Be part of the movement to bring clean, portable energy to communities in need.</p>
          <div class="cta-actions">
            <NuxtLink to="/get-involved" class="btn btn-primary btn-large">
              Get Involved
            </NuxtLink>
            <NuxtLink to="/donate" class="btn btn-secondary btn-large">
              Support Our Mission
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const getDotStyle = (index) => {
  const delay = index * 0.2;
  return {
    'animation-delay': `${delay}s`
  };
};
</script>

<style scoped>
.homepage {
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Hero Section */
.hero {
  min-height: 100vh;
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.energy-orb {
  position: absolute;
  width: var(--size, 100px);
  height: var(--size, 100px);
  background: radial-gradient(circle, rgba(74, 124, 89, 0.3) 0%, transparent 70%);
  border-radius: 50%;
  top: var(--y, 20%);
  left: var(--x, 10%);
  animation: floatOrb 6s ease-in-out infinite;
  animation-delay: var(--delay, 0s);
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
}

.title-line {
  display: block;
}

.highlight {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 1.2rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
  opacity: 0.9;
  max-width: 500px;
}

.hero-actions {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 15px 30px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.btn-primary {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(46, 204, 113, 0.3);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  border-color: rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-3px);
}

.btn-outline {
  border: 2px solid #4a7c59;
  color: #4a7c59;
  background: transparent;
}

.btn-outline:hover {
  background: #4a7c59;
  color: white;
  transform: translateY(-2px);
}

.btn-large {
  padding: 18px 35px;
  font-size: 1.1rem;
}

.btn-arrow {
  transition: transform 0.3s ease;
}

.btn-outline:hover .btn-arrow {
  transform: translateX(3px);
}

/* Lightbulb Graphic */
.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.lightbulb-graphic {
  position: relative;
  width: 300px;
  height: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.bulb {
  width: 120px;
  height: 120px;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  border-radius: 50% 50% 40% 40%;
  position: relative;
  z-index: 2;
}

.filament {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 4px;
  height: 30px;
  background: #2c5530;
  border-radius: 2px;
}

.glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 140px;
  height: 140px;
  background: radial-gradient(circle, rgba(46, 204, 113, 0.4) 0%, transparent 70%);
  border-radius: 50%;
  animation: pulseGlow 2s ease-in-out infinite;
}

.leaves {
  position: absolute;
  top: 40px;
  z-index: 1;
}

.leaf {
  position: absolute;
  background: #4a7c59;
  border-radius: 50% 0 50% 0;
}

.leaf-1 {
  width: 60px;
  height: 40px;
  top: -20px;
  left: -80px;
  transform: rotate(-20deg);
}

.leaf-2 {
  width: 80px;
  height: 50px;
  top: 10px;
  right: -90px;
  transform: rotate(20deg);
}

.leaf-3 {
  width: 70px;
  height: 45px;
  top: 60px;
  left: -70px;
  transform: rotate(-40deg);
}

.base {
  width: 40px;
  height: 30px;
  background: #2c5530;
  border-radius: 0 0 10px 10px;
  margin-top: -5px;
  z-index: 2;
}

.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.9rem;
}

.arrow {
  width: 2px;
  height: 20px;
  background: rgba(255, 255, 255, 0.5);
  margin: 10px auto 0;
  position: relative;
}

.arrow::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: -3px;
  width: 8px;
  height: 8px;
  border-right: 2px solid rgba(255, 255, 255, 0.5);
  border-bottom: 2px solid rgba(255, 255, 255, 0.5);
  transform: rotate(45deg);
}

/* Problem Section */
.problem-section {
  padding: 100px 0;
  background: #f8f9fa;
}

.section-header {
  text-align: center;
  margin-bottom: 60px;
}

.section-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 80px;
  height: 80px;
  background: white;
  border-radius: 50%;
  margin-bottom: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.problem-icon {
  color: #e74c3c;
}

.solution-icon {
  color: #4a7c59;
}

.section-header h2 {
  font-size: 2.5rem;
  color: #2c5530;
  margin: 0;
}

.problem-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.problem-statement {
  font-size: 1.3rem;
  line-height: 1.7;
  color: #2c5530;
  margin-bottom: 40px;
}

.problem-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

.stat {
  text-align: center;
  padding: 20px;
  background: white;
  border-radius: 12px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
}

.stat-number {
  font-size: 2rem;
  font-weight: 800;
  color: #e74c3c;
  margin-bottom: 8px;
}

.stat-label {
  font-size: 0.9rem;
  color: #666;
  line-height: 1.4;
}

.problem-image {
  display: flex;
  justify-content: center;
}

.image-placeholder {
  width: 100%;
  max-width: 400px;
  height: 300px;
  background: white;
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.community-silhouette {
  position: relative;
  width: 200px;
  height: 150px;
  margin-bottom: 20px;
}

.house {
  position: absolute;
  bottom: 0;
  width: 40px;
  height: 40px;
  background: #ddd;
  border-radius: 4px;
}

.house:nth-child(1) { left: 30px; }
.house:nth-child(2) { left: 80px; height: 50px; }
.house:nth-child(3) { left: 130px; }

.smoke {
  position: absolute;
  top: 20px;
  left: 90px;
  width: 20px;
  height: 20px;
  background: #ccc;
  border-radius: 50%;
}

.image-placeholder p {
  color: #999;
  font-style: italic;
  margin: 0;
}

/* Solution Section */
.solution-section {
  padding: 100px 0;
  background: white;
}

.solution-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.solution-visual {
  max-width: 500px;
}

.solution-image {
  width: 100%;
  height: auto;
  border-radius: 10px;
}
.skin-patch-demo {
  position: relative;
  width: 300px;
  height: 400px;
}

.patch {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 180px;
  height: 120px;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  border-radius: 20px;
  box-shadow: 0 15px 35px rgba(74, 124, 89, 0.3);
}

.circuit-lines {
  position: absolute;
  top: 20px;
  left: 20px;
  right: 20px;
  bottom: 20px;
}

.line {
  height: 2px;
  background: rgba(255, 255, 255, 0.3);
  margin-bottom: 15px;
  border-radius: 1px;
}

.energy-dots {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.dot {
  position: absolute;
  width: 6px;
  height: 6px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 50%;
  animation: energyFlow 2s ease-in-out infinite;
}

.dot:nth-child(1) { top: 25px; left: 30px; }
.dot:nth-child(2) { top: 45px; right: 40px; }
.dot:nth-child(3) { bottom: 35px; left: 50px; }
.dot:nth-child(4) { bottom: 25px; right: 30px; }
.dot:nth-child(5) { top: 60px; left: 25px; }
.dot:nth-child(6) { top: 35px; right: 25px; }

.arm-silhouette {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 200px;
  height: 300px;
  background: linear-gradient(to top, #f0f0f0, #e0e0e0);
  border-radius: 100px 100px 0 0;
}

.solution-statement {
  font-size: 1.3rem;
  line-height: 1.7;
  color: #2c5530;
  margin-bottom: 40px;
}

.solution-features {
  margin-bottom: 40px;
}

.feature {
  display: flex;
  align-items: flex-start;
  gap: 15px;
  margin-bottom: 25px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 12px;
  transition: all 0.3s ease;
}

.feature:hover {
  transform: translateX(10px);
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
}

.feature-icon {
  font-size: 1.5rem;
  flex-shrink: 0;
}

.feature-content h4 {
  margin: 0 0 5px 0;
  color: #2c5530;
}

.feature-content p {
  margin: 0;
  color: #666;
  font-size: 0.95rem;
}

/* SDG Section */
.sdg-section {
  padding: 80px 0;
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
}

.sdg-content {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 60px;
  align-items: center;
  max-width: 800px;
  margin: 0 auto;
}

.sdg-badge-large {
  display: flex;
  align-items: center;
  gap: 20px;
  background: rgba(255, 255, 255, 0.1);
  padding: 30px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.sdg-number {
  font-size: 4rem;
  font-weight: 800;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
}

.sdg-text {
  display: flex;
  flex-direction: column;
}

.sdg-text span {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 5px;
}

.sdg-text small {
  opacity: 0.8;
  font-size: 0.9rem;
}

.sdg-mission h3 {
  font-size: 2rem;
  margin-bottom: 20px;
}

.sdg-mission p {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 30px;
  opacity: 0.9;
}

.mission-values {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.value-pill {
  padding: 8px 20px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  font-size: 0.9rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

/* CTA Section */
.cta-section {
  padding: 100px 0;
  background: #f8f9fa;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  color: #2c5530;
  margin-bottom: 20px;
}

.cta-content p {
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 40px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.cta-actions {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

/* Animations */
@keyframes floatOrb {
  0%, 100% { transform: translateY(0) scale(1); opacity: 0.7; }
  50% { transform: translateY(-20px) scale(1.1); opacity: 1; }
}

@keyframes pulseGlow {
  0%, 100% { opacity: 0.4; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 0.8; transform: translate(-50%, -50%) scale(1.1); }
}

@keyframes energyFlow {
  0%, 100% { opacity: 0.3; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.5); }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .hero-content,
  .problem-content,
  .solution-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .problem-stats {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .sdg-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 40px;
  }
  
  .sdg-badge-large {
    justify-content: center;
    text-align: left;
  }
}

@media (max-width: 768px) {
  .hero-actions,
  .cta-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .btn {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }
  
  .mission-values {
    justify-content: center;
  }
  
  .lightbulb-graphic {
    transform: scale(0.8);
  }
  
  .skin-patch-demo {
    transform: scale(0.8);
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 15px;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .problem-statement,
  .solution-statement {
    font-size: 1.1rem;
  }
}
</style>