<template>
  <div class="solution-page">
    <!-- Hero Section -->
    <!-- <section class="solution-hero">
      <div class="hero-background">
        <div class="energy-flow">
          <div class="flow-line" v-for="i in 8" :key="i" :style="getFlowStyle(i)"></div>
        </div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title">
              The Power Skin:
              <span class="title-highlight">Energy from You, Power for the Planet</span>
            </h1>
            <p class="hero-subtitle">
              A revolutionary wearable patch that transforms your body's natural energy 
              into clean, portable electricity for everyday devices.
            </p>
            <div class="hero-features">
              <div class="feature-tag">Clean Energy</div>
              <div class="feature-tag">Portable</div>
              <div class="feature-tag">Sustainable</div>
              <div class="feature-tag">Accessible</div>
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
      </div>
    </section> -->

    <!-- What It Is Section -->
    <section class="what-is-section">
      <div class="container">
        <div class="section-content">
          <div class="section-text">
            <h2>What is the Power Skin?</h2>
            <p class="lead-text">
              The <strong>Power Skin</strong> is a wearable patch that provides a clean, portable source of power. 
              It's designed to help reduce reliance on polluting fuels and batteries.
            </p>
            <div class="benefits-grid">
              <div class="benefit-item" v-for="benefit in benefits" :key="benefit.title">
                <div class="benefit-icon">{{ benefit.emoji }}</div>
                <div class="benefit-content">
                  <h4>{{ benefit.title }}</h4>
                  <p>{{ benefit.description }}</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="section-visual">
            <div class="patch-concept">
    <div class="patch-display">
      <div class="patch-outline">
        <!-- Your image here -->
        <img 
          src="/img1.png" 
          alt="Power Skin Patch"
          class="patch-image"
        />
      </div>
      <div class="patch-label">Power Skin Patch</div>
    </div>
  </div>
          </div>
        </div>
      </div>
    </section>

    <!-- How It Works Section -->
    <section class="how-it-works-section">
      <div class="container">
        <div class="section-header">
          <h2>How It Works</h2>
          <p>Simple, efficient energy conversion in three steps</p>
        </div>
        
        <div class="process-flow">
          <!-- Step 1: Capture -->
          <div class="process-step">
            <div class="step-visual">
              <div class="step-number">1</div>
              <div class="step-icon">🔥</div>
              <div class="step-illustration">
                <div class="human-silhouette">
                  <div class="body"></div>
                  <div class="arm">
                    <div class="patch-position">
                      <div class="heat-waves">
                        <div class="wave"></div>
                        <div class="wave"></div>
                        <div class="wave"></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="step-content">
              <h3>Capture</h3>
              <p>The patch captures natural energy from the human body, such as heat and movement.</p>
              <div class="step-details">
                <div class="detail-item">
                  <span class="detail-label">Body Heat</span>
                  <span class="detail-value">Thermal energy conversion</span>
                </div>
                <div class="detail-item">
                  <span class="detail-label">Movement</span>
                  <span class="detail-value">Kinetic energy harvesting</span>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Step 2: Convert -->
          <div class="process-step">
            <div class="step-visual">
              <div class="step-number">2</div>
              <div class="step-icon">⚡</div>
              <div class="step-illustration">
                <div class="conversion-diagram">
                  <div class="input-energy">
                    <div class="energy-source heat">HEAT</div>
                    <div class="energy-source motion">MOTION</div>
                  </div>
                  <div class="converter">
                    <div class="converter-core"></div>
                  </div>
                  <div class="output-energy">
                    <div class="energy-output electricity">ELECTRICITY</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="step-content">
              <h3>Convert</h3>
              <p>It converts this energy into electricity through advanced thermoelectric and piezoelectric materials.</p>
              <div class="step-details">
                <div class="detail-item">
                  <span class="detail-label">Efficiency</span>
                  <span class="detail-value">Optimized energy conversion</span>
                </div>
                <div class="detail-item">
                  <span class="detail-label">Technology</span>
                  <span class="detail-value">Advanced nanomaterials</span>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Step 3: Power -->
          <div class="process-step">
            <div class="step-visual">
              <div class="step-number">3</div>
              <div class="step-icon">💡</div>
              <div class="step-illustration">
                <div class="power-application">
                  <div class="device-grid">
                    <div class="device" v-for="device in poweredDevices" :key="device.name">
                      <div class="device-icon">{{ device.emoji }}</div>
                      <div class="device-name">{{ device.name }}</div>
                    </div>
                  </div>
                  <div class="power-flow">
                    <div class="flow-arrow"></div>
                  </div>
                </div>
              </div>
            </div>
            <div class="step-content">
              <h3>Power</h3>
              <p>This provides power for small devices, helping users in remote communities stay connected and safe.</p>
              <div class="step-details">
                <div class="detail-item">
                  <span class="detail-label">Applications</span>
                  <span class="detail-value">LED lights, phone charging</span>
                </div>
                <div class="detail-item">
                  <span class="detail-label">Impact</span>
                  <span class="detail-value">Enhanced safety & connectivity</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Technical Features -->
    <section class="features-section">
      <div class="container">
        <div class="section-header">
          <h2>Technical Features</h2>
          <p>Designed for reliability and maximum impact</p>
        </div>
        
        <div class="features-grid">
          <div class="feature-card" v-for="feature in technicalFeatures" :key="feature.title">
            <div class="feature-icon">{{ feature.emoji }}</div>
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.description }}</p>
            <div class="feature-specs">
              <div class="spec" v-for="spec in feature.specs" :key="spec">
                <span class="spec-dot"></span>
                <span>{{ spec }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Impact Section -->
    <section class="impact-section">
      <div class="container">
        <div class="impact-content">
          <div class="impact-text">
            <h2>Real World Impact</h2>
            <p class="impact-statement">
              The Power Skin is more than technology—it's a tool for empowerment, education, 
              and environmental protection in communities that need it most.
            </p>
            
            <div class="impact-stats">
              <div class="impact-stat" v-for="stat in impactStats" :key="stat.label">
                <div class="impact-value">{{ stat.value }}</div>
                <div class="impact-label">{{ stat.label }}</div>
              </div>
            </div>
            
            <NuxtLink to="/impact" class="btn btn-primary">
              See Our Impact Stories
              <svg class="btn-arrow" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M4,11V13H16L10.5,18.5L11.92,19.92L19.84,12L11.92,4.08L10.5,5.5L16,11H4Z"/>
              </svg>
            </NuxtLink>
          </div>
          
          <div class="impact-visual">
            <div class="community-scene">
              <div class="scene-background">
                <div class="house"></div>
                <div class="house"></div>
                <div class="tree"></div>
              </div>
              <div class="scene-foreground">
                <div class="person-with-light">
                  <div class="person"></div>
                  <div class="light-glow"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="solution-cta">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Learn More?</h2>
          <p>Discover how the Power Skin technology can transform energy access in your community or organization.</p>
          <div class="cta-actions">
            <NuxtLink to="/contact" class="btn btn-primary btn-large">
              Get in Touch
            </NuxtLink>
            <NuxtLink to="/technology-details" class="btn btn-secondary btn-large">
              Technical Specifications
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// Benefits data
const benefits = [
  {
    title: 'Clean Energy',
    emoji: '🌿',
    description: 'Zero emissions, no pollution, completely renewable energy source'
  },
  {
    title: 'Portable Power',
    emoji: '🎒',
    description: 'Lightweight and wearable, provides energy wherever you go'
  },
  {
    title: 'Reduces Waste',
    emoji: '🗑️',
    description: 'Decreases reliance on disposable batteries and fossil fuels'
  },
  {
    title: 'Accessible',
    emoji: '👥',
    description: 'Designed for remote communities with limited energy access'
  }
]

// Powered devices data
const poweredDevices = [
  { name: 'LED Lights', emoji: '💡' },
  { name: 'Phone Charging', emoji: '📱' },
  { name: 'Radios', emoji: '📻' },
  { name: 'Medical Devices', emoji: '❤️' }
]

// Technical features data
const technicalFeatures = [
  {
    title: 'Advanced Materials',
    emoji: '🔬',
    description: 'Utilizes cutting-edge thermoelectric and piezoelectric nanomaterials',
    specs: [
      'Flexible substrate',
      'Biocompatible materials',
      'Durable construction'
    ]
  },
  {
    title: 'Energy Efficiency',
    emoji: '📊',
    description: 'Optimized for maximum energy capture from body heat and movement',
    specs: [
      'Thermal conversion',
      'Motion harvesting',
      'Low power consumption'
    ]
  },
  {
    title: 'User-Friendly',
    emoji: '👤',
    description: 'Designed for easy use in diverse environments and conditions',
    specs: [
      'Simple application',
      'Comfortable wear',
      'Easy maintenance'
    ]
  }
]

// Impact statistics data
const impactStats = [
  { value: '5-10W', label: 'Power Output' },
  { value: '24/7', label: 'Continuous Operation' },
  { value: '0g CO₂', label: 'Carbon Emissions' },
  { value: '5+ Years', label: 'Lifespan' }
]

// Helper functions for animations
const getFlowStyle = (index) => {
  const delay = index * 0.3
  const duration = 4 + (index * 0.5)
  return {
    'animation-delay': `${delay}s`,
    'animation-duration': `${duration}s`
  }
}

const getCircuitStyle = (index) => {
  const rotation = index * 30
  const length = 40 + (index % 3) * 20
  return {
    transform: `rotate(${rotation}deg)`,
    height: `${length}%`
  }
}

const getEnergyDotStyle = (index) => {
  const positions = [
    { top: '20%', left: '30%' },
    { top: '40%', left: '70%' },
    { top: '60%', left: '20%' },
    { top: '25%', left: '60%' },
    { top: '75%', left: '40%' },
    { top: '50%', left: '25%' },
    { top: '35%', left: '45%' },
    { top: '65%', left: '65%' },
    { top: '45%', left: '80%' }
  ]
  const delay = index * 0.2
  return {
    ...positions[index % positions.length],
    'animation-delay': `${delay}s`
  }
}
</script>

<style scoped>
.solution-page {
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Hero Section */
.solution-hero {
  min-height: 80vh;
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

.energy-flow {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.flow-line {
  position: absolute;
  width: 2px;
  height: 100%;
  background: linear-gradient(to bottom, transparent, rgba(74, 124, 89, 0.5), transparent);
  animation: flowMove 6s ease-in-out infinite;
}

.flow-line:nth-child(odd) {
  left: 20%;
}

.flow-line:nth-child(even) {
  left: 80%;
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
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
}

.title-highlight {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: block;
}

.hero-subtitle {
  font-size: 1.3rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 2rem;
}

.hero-features {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.feature-tag {
  background: rgba(255, 255, 255, 0.1);
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.lightbulb-graphic {
  position: relative;
  width: 250px;
  height: 350px;
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

/* What It Is Section */
.what-is-section {
  padding: 100px 0;
  background: white;
}

.section-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.section-text h2 {
  font-size: 2.5rem;
  color: #0a2e38;
  margin-bottom: 20px;
}

.lead-text {
  font-size: 1.3rem;
  line-height: 1.7;
  color: #666;
  margin-bottom: 40px;
}

.benefits-grid {
  display: grid;
  gap: 25px;
}

.benefit-item {
  display: flex;
  align-items: flex-start;
  gap: 20px;
  padding: 25px;
  background: #f8f9fa;
  border-radius: 12px;
  transition: all 0.3s ease;
}

.benefit-item:hover {
  transform: translateX(10px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.benefit-icon {
  font-size: 2rem;
  flex-shrink: 0;
}

.benefit-content h4 {
  margin: 0 0 8px 0;
  color: #0a2e38;
  font-size: 1.2rem;
}

.benefit-content p {
  margin: 0;
  color: #666;
  line-height: 1.5;
}

.section-visual {
  display: flex;
  justify-content: center;
}
.patch-concept {
  width: 100%;
  max-width: 400px;
}

.patch-display {
  text-align: center;
}

.patch-outline {
  width: 100%;
  height: 80%;
  margin: 0 auto 20px;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(74, 124, 89, 0.3);
}

.patch-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.patch-label {
  font-weight: 600;
  color: #0a2e38;
  font-size: 1.1rem;
}
.circuit-pattern {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  opacity: 0.3;
}

.circuit-line {
  position: absolute;
  top: 50%;
  left: 50%;
  transform-origin: center;
  width: 2px;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 1px;
}

.energy-dots {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.energy-dot {
  position: absolute;
  width: 6px;
  height: 6px;
  background: rgba(255, 255, 255, 0.9);
  border-radius: 50%;
  animation: energyPulse 2s ease-in-out infinite;
}

.patch-label {
  font-weight: 600;
  color: #0a2e38;
  font-size: 1.1rem;
}

/* How It Works Section */
.how-it-works-section {
  padding: 100px 0;
  background: #f8f9fa;
}

.section-header {
  text-align: center;
  margin-bottom: 80px;
}

.section-header h2 {
  font-size: 2.5rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.section-header p {
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
}

.process-flow {
  display: flex;
  flex-direction: column;
  gap: 80px;
  max-width: 1000px;
  margin: 0 auto;
}

.process-step {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.process-step:nth-child(even) {
  direction: rtl;
}

.process-step:nth-child(even) > * {
  direction: ltr;
}

.step-visual {
  text-align: center;
  position: relative;
}

.step-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.5rem;
  font-weight: 800;
  margin: 0 auto 20px;
  position: relative;
  z-index: 2;
}

.step-icon {
  font-size: 3rem;
  margin-bottom: 30px;
}

.step-illustration {
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Step 1 Illustration */
.human-silhouette {
  position: relative;
  width: 150px;
  height: 150px;
}

.body {
  width: 80px;
  height: 120px;
  background: #0a2e38;
  border-radius: 40px;
  position: absolute;
  top: 0;
  left: 35px;
}

.arm {
  position: absolute;
  top: 30px;
  right: -20px;
  width: 60px;
  height: 80px;
}

.patch-position {
  width: 40px;
  height: 30px;
  background: #4a7c59;
  border-radius: 8px;
  position: relative;
}

.heat-waves {
  position: absolute;
  top: -30px;
  left: 50%;
  transform: translateX(-50%);
}

.wave {
  width: 20px;
  height: 20px;
  border: 2px solid #e74c3c;
  border-radius: 50%;
  position: absolute;
  animation: heatWave 2s ease-in-out infinite;
}

.wave:nth-child(1) { animation-delay: 0s; }
.wave:nth-child(2) { animation-delay: 0.5s; }
.wave:nth-child(3) { animation-delay: 1s; }

/* Step 2 Illustration */
.conversion-diagram {
  display: flex;
  align-items: center;
  gap: 20px;
}

.input-energy, .output-energy {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.energy-source, .energy-output {
  padding: 10px 15px;
  border-radius: 8px;
  font-size: 0.8rem;
  font-weight: 600;
  text-align: center;
}

.heat { background: #ffeaa7; color: #2d3436; }
.motion { background: #74b9ff; color: white; }
.electricity { background: #a29bfe; color: white; }

.converter {
  width: 60px;
  height: 60px;
  background: #0a2e38;
  border-radius: 12px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.converter-core {
  width: 30px;
  height: 30px;
  background: #4a7c59;
  border-radius: 50%;
  animation: rotate 4s linear infinite;
}

/* Step 3 Illustration */
.power-application {
  text-align: center;
}

.device-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  margin-bottom: 20px;
}

.device {
  padding: 15px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.device-icon {
  font-size: 1.5rem;
  margin-bottom: 5px;
}

.device-name {
  font-size: 0.8rem;
  color: #666;
  font-weight: 600;
}

.power-flow {
  position: relative;
  height: 30px;
}

.flow-arrow {
  width: 0;
  height: 0;
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-top: 15px solid #4a7c59;
  margin: 0 auto;
}

.step-content h3 {
  font-size: 1.8rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.step-content p {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #666;
  margin-bottom: 25px;
}

.step-details {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.detail-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 0;
  border-bottom: 1px solid #e9ecef;
}

.detail-label {
  font-weight: 600;
  color: #0a2e38;
}

.detail-value {
  color: #666;
  font-size: 0.9rem;
}

/* Features Section */
.features-section {
  padding: 100px 0;
  background: white;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 40px;
  max-width: 1000px;
  margin: 0 auto;
}

.feature-card {
  background: #f8f9fa;
  padding: 40px 30px;
  border-radius: 15px;
  text-align: center;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.feature-card:hover {
  transform: translateY(-10px);
  border-color: #4a7c59;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.feature-icon {
  font-size: 3rem;
  margin-bottom: 20px;
}

.feature-card h3 {
  font-size: 1.4rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.feature-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 25px;
}

.feature-specs {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.spec {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #666;
  font-size: 0.9rem;
}

.spec-dot {
  width: 6px;
  height: 6px;
  background: #4a7c59;
  border-radius: 50%;
  flex-shrink: 0;
}

/* Impact Section */
.impact-section {
  padding: 100px 0;
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
}

.impact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.impact-text h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.impact-statement {
  font-size: 1.2rem;
  line-height: 1.7;
  opacity: 0.9;
  margin-bottom: 40px;
}

.impact-stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
  margin-bottom: 40px;
}

.impact-stat {
  text-align: center;
  padding: 20px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.impact-value {
  font-size: 2rem;
  font-weight: 800;
  color: #4a7c59;
  margin-bottom: 8px;
}

.impact-label {
  font-size: 0.9rem;
  opacity: 0.8;
}

.impact-visual {
  display: flex;
  justify-content: center;
}

.community-scene {
  position: relative;
  width: 300px;
  height: 200px;
}

.scene-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.house {
  position: absolute;
  bottom: 0;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 4px;
}

.house:nth-child(1) { left: 30px; }
.house:nth-child(2) { right: 30px; height: 50px; }

.tree {
  position: absolute;
  bottom: 0;
  left: 120px;
  width: 30px;
  height: 60px;
  background: rgba(74, 124, 89, 0.5);
  border-radius: 15px;
}

.scene-foreground {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.person-with-light {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}

.person {
  width: 20px;
  height: 40px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 10px;
  position: relative;
}

.light-glow {
  position: absolute;
  top: -30px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 40px;
  background: radial-gradient(circle, rgba(46, 204, 113, 0.6) 0%, transparent 70%);
  border-radius: 50%;
  animation: glowPulse 2s ease-in-out infinite;
}

/* CTA Section */
.solution-cta {
  padding: 100px 0;
  background: #f8f9fa;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  color: #0a2e38;
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

/* Button Styles */
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
  color: #0a2e38;
  border-color: #4a7c59;
}

.btn-secondary:hover {
  background: #4a7c59;
  color: white;
  transform: translateY(-3px);
}

.btn-large {
  padding: 18px 35px;
  font-size: 1.1rem;
}

.btn-arrow {
  transition: transform 0.3s ease;
}

.btn-primary:hover .btn-arrow {
  transform: translateX(3px);
}

/* Animations */
@keyframes flowMove {
  0%, 100% { transform: translateY(-100%); opacity: 0; }
  50% { opacity: 1; }
  100% { transform: translateY(100%); opacity: 0; }
}

@keyframes pulseGlow {
  0%, 100% { opacity: 0.4; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 0.8; transform: translate(-50%, -50%) scale(1.1); }
}

@keyframes energyPulse {
  0%, 100% { opacity: 0.3; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.5); }
}

@keyframes heatWave {
  0% { transform: translateX(-50%) scale(0); opacity: 1; }
  100% { transform: translateX(-50%) scale(3); opacity: 0; }
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes glowPulse {
  0%, 100% { opacity: 0.6; transform: translateX(-50%) scale(1); }
  50% { opacity: 1; transform: translateX(-50%) scale(1.2); }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .hero-content,
  .section-content,
  .impact-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .process-step {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .process-step:nth-child(even) {
    direction: ltr;
  }
}

@media (max-width: 768px) {
  .hero-features {
    justify-content: center;
  }
  
  .benefits-grid {
    grid-template-columns: 1fr;
  }
  
  .impact-stats {
    grid-template-columns: 1fr;
  }
  
  .cta-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .btn {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
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
  
  .step-illustration {
    height: 150px;
  }
}
</style>