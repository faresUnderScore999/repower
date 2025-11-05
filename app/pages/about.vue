<template>
  <div class="about-page">
    <!-- Hero Section -->
    <section class="about-hero">
      <div class="hero-background">
        <div class="energy-grid">
          <div class="grid-line" v-for="i in 12" :key="i" :style="getGridStyle(i)"></div>
        </div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-title">About RePower</h1>
          <p class="hero-subtitle">
            Transforming human energy into clean, accessible power for communities worldwide
          </p>
        </div>
      </div>
    </section>

    <!-- Mission & Vision Section -->
    <section class="mission-vision-section">
      <div class="container">
        <div class="mission-vision-grid">
          <!-- Vision -->
          <div class="mission-card vision-card">
            <div class="card-icon">
              <svg viewBox="0 0 24 24" width="48" height="48">
                <path fill="currentColor" d="M12,9A3,3 0 0,1 15,12A3,3 0 0,1 12,15A3,3 0 0,1 9,12A3,3 0 0,1 12,9M12,4.5C17,4.5 21.27,7.61 23,12C21.27,16.39 17,19.5 12,19.5C7,19.5 2.73,16.39 1,12C2.73,7.61 7,4.5 12,4.5M3.18,12C4.83,15.36 8.24,17.5 12,17.5C15.76,17.5 19.17,15.36 20.82,12C19.17,8.64 15.76,6.5 12,6.5C8.24,6.5 4.83,8.64 3.18,12Z"/>
              </svg>
            </div>
            <h2>Our Vision</h2>
            <p class="vision-statement">Clean, portable energy for all.</p>
            <div class="card-decoration">
              <div class="decoration-orb"></div>
            </div>
          </div>

          <!-- Mission -->
          <div class="mission-card mission-card-main">
            <div class="card-icon">
              <svg viewBox="0 0 24 24" width="48" height="48">
                <path fill="currentColor" d="M13,2.03V2.05L13,4.05C17.39,4.59 20.5,8.58 19.96,12.97C19.5,16.61 16.64,19.5 13,19.93V21.93C18.5,21.38 22.5,16.5 21.95,11C21.5,6.25 17.73,2.5 13,2.03M11,2.06C9.05,2.25 7.19,3 5.67,4.26L7.1,5.74C8.22,4.84 9.57,4.26 11,4.06V2.06M4.26,5.67C3,7.19 2.25,9.04 2.05,11H4.05C4.24,9.58 4.8,8.23 5.69,7.1L4.26,5.67M2.06,13C2.26,14.96 3.03,16.81 4.27,18.33L5.69,16.9C4.81,15.77 4.24,14.42 4.06,13H2.06M7.1,18.37L5.67,19.74C7.18,21 9.04,21.79 11,22V20C9.58,19.82 8.23,19.25 7.1,18.37M12.5,7V12.25L17,14.92L16.25,16.15L11,13V7H12.5Z"/>
              </svg>
            </div>
            <h2>Our Mission</h2>
            <p class="mission-statement">To generate electricity from the human body through innovative wearable technology.</p>
            <div class="card-decoration">
              <div class="decoration-wave"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Values Section -->
    <section class="values-section">
      <div class="container">
        <div class="section-header">
          <h2>Our Values</h2>
          <p>The principles that guide our work and define who we are</p>
        </div>
        
        <div class="values-grid">
          <div class="value-card" v-for="value in values" :key="value.name">
            <div class="value-icon" :class="value.color">
              {{ value.emoji }}
            </div>
            <h3>{{ value.name }}</h3>
            <p>{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="team-section">
      <div class="container">
        <div class="section-header">
          <h2>Meet Our Team</h2>
          <p>The dedicated leaders driving RePower's mission forward</p>
        </div>
        
        <div class="team-grid">
          <div class="team-member" v-for="member in teamMembers" :key="member.name">
            <div class="member-photo">
              <div class="photo-placeholder">
                <div class="initials">{{ getInitials(member.name) }}</div>
                <div class="photo-overlay">
                  <div class="member-role">{{ member.role }}</div>
                </div>
              </div>
              <!-- In production, replace with actual photo -->
              <!-- <img :src="member.photo" :alt="member.name" /> -->
            </div>
            <div class="member-info">
              <h3>{{ member.name }}</h3>
              <p class="member-role-text">{{ member.role }}</p>
              <p class="member-bio">{{ member.bio }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Partners Section -->
    <section class="partners-section">
      <div class="container">
        <div class="section-header">
          <h2>Our Partners & Affiliations</h2>
          <p>Strong collaborations for greater impact</p>
        </div>
        
        <div class="partners-content">
          <div class="partners-statement">
            <p>
              <strong>RePower is a project by the N.G.O: HOPE-BUILDERS</strong> and is supported by 
              <strong>Esprit (espr)</strong> and <strong>Honoris United Universities</strong>.
            </p>
          </div>
          
          <div class="partners-logos">
            <div class="partner-logo" v-for="partner in partners" :key="partner.name">
              <div class="logo-placeholder">
                <div class="logo-initials">{{ partner.initials }}</div>
                <div class="logo-name">{{ partner.name }}</div>
              </div>
              <!-- In production, replace with actual logo -->
              <!-- <img :src="partner.logo" :alt="partner.name" /> -->
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="about-cta">
      <div class="container">
        <div class="cta-content">
          <h2>Join Our Mission</h2>
          <p>Be part of the movement to bring clean, portable energy to communities in need</p>
          <div class="cta-actions">
            <NuxtLink to="/get-involved" class="btn btn-primary">
              Get Involved
            </NuxtLink>
            <NuxtLink to="/contact" class="btn btn-secondary">
              Contact Us
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// Values data
const values = [
  {
    name: 'Innovation',
    emoji: '💡',
    description: 'Pushing boundaries with cutting-edge technology to solve energy challenges in new ways.',
    color: 'innovation'
  },
  {
    name: 'Sustainability',
    emoji: '🌱',
    description: 'Creating solutions that are environmentally friendly and promote long-term ecological balance.',
    color: 'sustainability'
  },
  {
    name: 'Accessibility',
    emoji: '👥',
    description: 'Ensuring our technology reaches and benefits communities most in need, regardless of location.',
    color: 'accessibility'
  },
  {
    name: 'Empowerment',
    emoji: '⚡',
    description: 'Enabling individuals and communities through access to clean, reliable energy sources.',
    color: 'empowerment'
  }
]

// Team members data
const teamMembers = [
  {
    name: 'Hiba Dogui',
    role: 'President',
    bio: 'Leading RePower\'s strategic vision and driving our mission to transform human energy into clean power.',
    photo: '/team/hiba-dogui.jpg'
  },
  {
  name: 'Fares Benali',
  role: 'IT Specialist',
  bio: 'Providing technical support, maintaining systems, and ensuring smooth IT operations.',
  photo: '/team/fares-benali.jpg'
},
  {
    name: 'Oussama Belarbi',
    role: 'Vice President',
    bio: 'Overseeing project development and ensuring the successful implementation of our technology initiatives.',
    photo: '/team/oussama-belarbi.jpg'
  },
  {
    name: 'Maïssa Sbei',
    role: 'Treasurer',
    bio: 'Managing financial operations and ensuring sustainable growth through strategic resource allocation.',
    photo: '/team/maissa-sbei.jpg'
  },
  {
    name: 'Maram Ghazel',
    role: 'Secretary',
    bio: 'Coordinating communications and maintaining organizational records and documentation.',
    photo: '/team/maram-ghazel.jpg'
  }
]

// Partners data
const partners = [
  {
    name: 'HOPE-BUILDERS',
    initials: 'HB',
    description: 'Parent NGO organization',
    logo: '/partners/hope-builders.png'
  },
  {
    name: 'Esprit',
    initials: 'ESPR',
    description: 'Academic partner and supporter',
    logo: '/partners/esprit.png'
  },
  {
    name: 'Honoris United Universities',
    initials: 'HON',
    description: 'Educational network partner',
    logo: '/partners/honoris.png'
  }
]

// Helper functions
const getInitials = (name) => {
  return name.split(' ').map(n => n[0]).join('')
}

const getGridStyle = (index) => {
  const delay = index * 0.1
  return {
    'animation-delay': `${delay}s`
  }
}
</script>

<style scoped>
.about-page {
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Hero Section */
.about-hero {
  min-height: 60vh;
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

.energy-grid {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  opacity: 0.1;
}

.grid-line {
  position: absolute;
  background: linear-gradient(90deg, transparent, #4a7c59, transparent);
  height: 1px;
  width: 100%;
  animation: gridScan 3s ease-in-out infinite;
}

.grid-line:nth-child(odd) {
  animation-delay: 0.5s;
}

.hero-content {
  text-align: center;
  position: relative;
  z-index: 2;
  max-width: 800px;
  margin: 0 auto;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, #fff, #4a7c59);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 1.3rem;
  line-height: 1.6;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

/* Mission & Vision Section */
.mission-vision-section {
  padding: 100px 0;
  background: #f8f9fa;
}

.mission-vision-grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 40px;
  max-width: 1000px;
  margin: 0 auto;
}

.mission-card {
  background: white;
  padding: 50px 40px;
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  position: relative;
  overflow: hidden;
  text-align: center;
}

.mission-card-main {
  background: linear-gradient(135deg, #0a2e38, #1a4a5a);
  color: white;
}

.mission-card h2 {
  font-size: 1.8rem;
  margin-bottom: 20px;
  color: inherit;
}

.vision-statement,
.mission-statement {
  font-size: 1.4rem;
  line-height: 1.5;
  font-weight: 600;
  margin: 0;
}

.mission-card-main .vision-statement,
.mission-card-main .mission-statement {
  color: #4a7c59;
}

.card-icon {
  margin-bottom: 25px;
}

.mission-card-main .card-icon {
  color: #4a7c59;
}

.vision-card .card-icon {
  color: #0a2e38;
}

.card-decoration {
  position: absolute;
  bottom: -50px;
  right: -50px;
  opacity: 0.1;
}

.decoration-orb {
  width: 150px;
  height: 150px;
  background: #4a7c59;
  border-radius: 50%;
}

.decoration-wave {
  width: 200px;
  height: 100px;
  background: #4a7c59;
  border-radius: 50%;
  transform: rotate(45deg);
}

/* Values Section */
.values-section {
  padding: 100px 0;
  background: white;
}

.section-header {
  text-align: center;
  margin-bottom: 60px;
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

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.value-card {
  background: #f8f9fa;
  padding: 40px 30px;
  border-radius: 15px;
  text-align: center;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.value-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  border-color: #4a7c59;
}

.value-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  margin: 0 auto 25px;
  position: relative;
}

.value-icon.innovation {
  background: linear-gradient(135deg, #ffeaa7, #fab1a0);
}

.value-icon.sustainability {
  background: linear-gradient(135deg, #55efc4, #00b894);
}

.value-icon.accessibility {
  background: linear-gradient(135deg, #74b9ff, #0984e3);
}

.value-icon.empowerment {
  background: linear-gradient(135deg, #a29bfe, #6c5ce7);
}

.value-card h3 {
  font-size: 1.5rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.value-card p {
  color: #666;
  line-height: 1.6;
  margin: 0;
}

/* Team Section */
.team-section {
  padding: 100px 0;
  background: #f8f9fa;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
}

.team-member {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.team-member:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.member-photo {
  position: relative;
  height: 250px;
  background: linear-gradient(135deg, #0a2e38, #1a4a5a);
  overflow: hidden;
}

.photo-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.initials {
  font-size: 3rem;
  font-weight: 800;
  color: rgba(255, 255, 255, 0.3);
}

.photo-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
  padding: 20px;
  color: white;
}

.member-role {
  font-weight: 600;
  color: #4a7c59;
}

.member-info {
  padding: 30px;
}

.member-info h3 {
  font-size: 1.4rem;
  color: #0a2e38;
  margin-bottom: 5px;
}

.member-role-text {
  color: #4a7c59;
  font-weight: 600;
  margin-bottom: 15px;
  font-size: 0.95rem;
}

.member-bio {
  color: #666;
  line-height: 1.6;
  margin: 0;
}

/* Partners Section */
.partners-section {
  padding: 100px 0;
  background: white;
}

.partners-content {
  max-width: 1000px;
  margin: 0 auto;
}

.partners-statement {
  text-align: center;
  margin-bottom: 60px;
}

.partners-statement p {
  font-size: 1.3rem;
  line-height: 1.7;
  color: #0a2e38;
  max-width: 800px;
  margin: 0 auto;
}

.partners-logos {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
}

.partner-logo {
  text-align: center;
  padding: 40px 20px;
  background: #f8f9fa;
  border-radius: 15px;
  transition: all 0.3s ease;
}

.partner-logo:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.logo-placeholder {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.logo-initials {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #0a2e38, #1a4a5a);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.5rem;
  font-weight: 700;
}

.logo-name {
  font-size: 1.2rem;
  font-weight: 600;
  color: #0a2e38;
}

/* CTA Section */
.about-cta {
  padding: 100px 0;
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.cta-content p {
  font-size: 1.2rem;
  opacity: 0.9;
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

/* Animations */
@keyframes gridScan {
  0% { opacity: 0; transform: translateX(-100%); }
  50% { opacity: 1; }
  100% { opacity: 0; transform: translateX(100%); }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .mission-vision-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .team-grid {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }
}

@media (max-width: 768px) {
  .mission-card {
    padding: 40px 30px;
  }
  
  .vision-statement,
  .mission-statement {
    font-size: 1.2rem;
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
  
  .partners-logos {
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
  
  .values-grid {
    grid-template-columns: 1fr;
  }
  
  .team-grid {
    grid-template-columns: 1fr;
  }
}
</style>