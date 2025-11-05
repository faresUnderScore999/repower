<template>
  <div class="get-involved-page">
    <!-- Hero Section -->
    <section class="involved-hero">
      <div class="hero-background">
        <div class="floating-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
          <div class="shape shape-4"></div>
        </div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-title">Help Us Power a Green Tomorrow</h1>
          <p class="hero-subtitle">
            Join our movement to bring clean, portable energy to communities in need. 
            Your involvement can light up lives and create sustainable change.
          </p>
          <div class="hero-stats">
            <div class="stat">
              <div class="stat-number">50+</div>
              <div class="stat-label">Active Volunteers</div>
            </div>
            <div class="stat">
              <div class="stat-number">15</div>
              <div class="stat-label">Communities Reached</div>
            </div>
            <div class="stat">
              <div class="stat-number">2K+</div>
              <div class="stat-label">Lives Impacted</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Challenges Section -->
    <section class="challenges-section">
      <div class="container">
        <div class="section-header">
          <h2>Our Challenges</h2>
          <p>To bring our solution to the world, we need to overcome key challenges</p>
        </div>
        
        <div class="challenges-grid">
          <div class="challenge-card" v-for="challenge in challenges" :key="challenge.title">
            <div class="challenge-icon" :class="challenge.color">
              {{ challenge.emoji }}
            </div>
            <h3>{{ challenge.title }}</h3>
            <p>{{ challenge.description }}</p>
            <div class="challenge-progress">
              <div class="progress-bar">
                <div class="progress-fill" :style="{ width: challenge.progress + '%' }"></div>
              </div>
              <span class="progress-text">{{ challenge.progress }}% addressed</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Volunteer Section -->
    <section class="volunteer-section">
      <div class="container">
        <div class="volunteer-content">
          <div class="volunteer-text">
            <h2>Become a Volunteer</h2>
            <p class="volunteer-description">
              We are looking for passionate volunteers to help with community outreach, 
              project coordination, and raising awareness. Fill out our form to join the team!
            </p>
            
            <div class="volunteer-roles">
              <h3>Volunteer Opportunities</h3>
              <div class="roles-grid">
                <div class="role-card" v-for="role in volunteerRoles" :key="role.title">
                  <div class="role-icon">{{ role.emoji }}</div>
                  <h4>{{ role.title }}</h4>
                  <p>{{ role.description }}</p>
                  <ul class="role-tasks">
                    <li v-for="task in role.tasks" :key="task">{{ task }}</li>
                  </ul>
                </div>
              </div>
            </div>
            
            <NuxtLink to="/volunteer-form" class="btn btn-primary btn-large">
              <svg class="btn-icon" viewBox="0 0 24 24" width="20" height="20">
                <path fill="currentColor" d="M12,4A4,4 0 0,1 16,8A4,4 0 0,1 12,12A4,4 0 0,1 8,8A4,4 0 0,1 12,4M12,14C16.42,14 20,15.79 20,18V20H4V18C4,15.79 7.58,14 12,14Z"/>
              </svg>
              Join as Volunteer
            </NuxtLink>
          </div>
          
          <div class="volunteer-visual">
            <div class="visual-placeholder">
              <div class="team-illustration">
                <div class="person person-1">
                  <div class="head"></div>
                  <div class="body"></div>
                </div>
                <div class="person person-2">
                  <div class="head"></div>
                  <div class="body"></div>
                </div>
                <div class="person person-3">
                  <div class="head"></div>
                  <div class="body"></div>
                </div>
                <div class="collaboration-lines">
                  <div class="line"></div>
                  <div class="line"></div>
                  <div class="line"></div>
                </div>
              </div>
              <p>Diverse team working together</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Partnership Section -->
    <section class="partnership-section">
      <div class="container">
        <div class="partnership-content">
          <div class="partnership-visual">
            <div class="visual-placeholder">
              <div class="partnership-illustration">
                <div class="org-connection">
                  <div class="org org-1">
                    <div class="org-icon">🏢</div>
                    <div class="org-name">Organization</div>
                  </div>
                  <div class="org org-2">
                    <div class="org-icon">🤝</div>
                    <div class="org-name">Partnership</div>
                  </div>
                  <div class="org org-3">
                    <div class="org-icon">🌍</div>
                    <div class="org-name">Community</div>
                  </div>
                  <div class="connection-line"></div>
                  <div class="connection-line"></div>
                </div>
              </div>
              <p>Building partnerships for impact</p>
            </div>
          </div>
          
          <div class="partnership-text">
            <h2>Partner With Us</h2>
            <p class="partnership-description">
              Are you an organization, distributor, or local leader? We are seeking partners 
              to help us scale our project and navigate regulations. Contact us to collaborate.
            </p>
            
            <div class="partnership-benefits">
              <h3>Partnership Benefits</h3>
              <div class="benefits-list">
                <div class="benefit-item" v-for="benefit in partnershipBenefits" :key="benefit">
                  <svg class="benefit-icon" viewBox="0 0 24 24" width="20" height="20">
                    <path fill="currentColor" d="M21,7L9,19L3.5,13.5L4.91,12.09L9,16.17L19.59,5.59L21,7Z"/>
                  </svg>
                  <span>{{ benefit }}</span>
                </div>
              </div>
            </div>
            
            <div class="partner-types">
              <h3>We're Looking For</h3>
              <div class="type-tags">
                <span class="type-tag" v-for="type in partnerTypes" :key="type">{{ type }}</span>
              </div>
            </div>
            
            <NuxtLink to="/contact" class="btn btn-secondary btn-large">
              <svg class="btn-icon" viewBox="0 0 24 24" width="20" height="20">
                <path fill="currentColor" d="M20,8L12,13L4,8V6L12,11L20,6M20,4H4C2.89,4 2,4.89 2,6V18A2,2 0 0,0 4,20H20A2,2 0 0,0 22,18V6C22,4.89 21.1,4 20,4Z"/>
              </svg>
              Contact for Partnership
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- Other Ways to Help -->
    <section class="other-ways-section">
      <div class="container">
        <div class="section-header">
          <h2>Other Ways to Get Involved</h2>
          <p>Multiple pathways to support our mission</p>
        </div>
        
        <div class="ways-grid">
          <div class="way-card" v-for="way in otherWays" :key="way.title">
            <div class="way-icon">{{ way.emoji }}</div>
            <h3>{{ way.title }}</h3>
            <p>{{ way.description }}</p>
            <NuxtLink :to="way.link" class="way-link">
              Learn More
              <svg class="link-arrow" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M4,11V13H16L10.5,18.5L11.92,19.92L19.84,12L11.92,4.08L10.5,5.5L16,11H4Z"/>
              </svg>
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="involved-cta">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Make a Difference?</h2>
          <p>Join thousands of supporters who are helping us bring clean energy to communities in need</p>
          <div class="cta-actions">
            <NuxtLink to="/volunteer-form" class="btn btn-primary btn-large">
              Volunteer Today
            </NuxtLink>
            <NuxtLink to="/contact" class="btn btn-secondary btn-large">
              Partner With Us
            </NuxtLink>
            <NuxtLink to="/donate" class="btn btn-outline btn-large">
              Make a Donation
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// Challenges data
const challenges = [
  {
    title: 'Remote Area Volunteers',
    description: 'Recruiting and supporting volunteers in hard-to-reach communities where energy needs are greatest.',
    emoji: '🏔️',
    progress: 40,
    color: 'challenge-1'
  },
  {
    title: 'Community Trust',
    description: 'Building trust and awareness in local communities to ensure adoption and proper use of our technology.',
    emoji: '🤝',
    progress: 60,
    color: 'challenge-2'
  },
  {
    title: 'Regulations & Distribution',
    description: 'Navigating local regulations and ensuring consistent distribution of Power Skin patches.',
    emoji: '📋',
    progress: 35,
    color: 'challenge-3'
  }
]

// Volunteer roles data
const volunteerRoles = [
  {
    title: 'Community Outreach',
    emoji: '📢',
    description: 'Engage with local communities and raise awareness about clean energy solutions.',
    tasks: [
      'Organize community workshops',
      'Distribute educational materials',
      'Collect community feedback'
    ]
  },
  {
    title: 'Project Coordination',
    emoji: '📊',
    description: 'Help manage and coordinate Power Skin deployment projects.',
    tasks: [
      'Coordinate volunteer activities',
      'Track project progress',
      'Manage distribution logistics'
    ]
  },
  {
    title: 'Awareness Campaigns',
    emoji: '🌟',
    description: 'Spread the word about our mission through various channels.',
    tasks: [
      'Social media management',
      'Content creation',
      'Event organization'
    ]
  }
]

// Partnership benefits data
const partnershipBenefits = [
  'Access to innovative clean energy technology',
  'Positive brand association with sustainable development',
  'Direct impact on SDG 7 targets',
  'Networking with like-minded organizations',
  'Corporate social responsibility fulfillment'
]

// Partner types data
const partnerTypes = [
  'NGOs & Non-profits',
  'Educational Institutions',
  'Local Distributors',
  'Government Agencies',
  'Corporate Partners',
  'Community Leaders'
]

// Other ways to help data
const otherWays = [
  {
    title: 'Spread Awareness',
    emoji: '📱',
    description: 'Share our mission on social media and within your networks to help us reach more people.',
    link: '/share'
  },
  {
    title: 'Host an Event',
    emoji: '🎪',
    description: 'Organize fundraising or awareness events in your community to support our cause.',
    link: '/events'
  },
  {
    title: 'Skill-Based Volunteering',
    emoji: '💻',
    description: 'Offer your professional skills in areas like marketing, tech, or design to support our work.',
    link: '/skills'
  }
]
</script>

<style scoped>
.get-involved-page {
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Hero Section */
.involved-hero {
  min-height: 70vh;
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

.floating-shapes {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.shape {
  position: absolute;
  border-radius: 50%;
  background: rgba(74, 124, 89, 0.1);
  animation: floatShape 8s ease-in-out infinite;
}

.shape-1 {
  width: 100px;
  height: 100px;
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 150px;
  height: 150px;
  top: 60%;
  right: 15%;
  animation-delay: 1.5s;
}

.shape-3 {
  width: 80px;
  height: 80px;
  bottom: 20%;
  left: 20%;
  animation-delay: 3s;
}

.shape-4 {
  width: 120px;
  height: 120px;
  top: 30%;
  right: 25%;
  animation-delay: 4.5s;
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
  margin-bottom: 3rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.hero-stats {
  display: flex;
  justify-content: center;
  gap: 40px;
  flex-wrap: wrap;
}

.stat {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 800;
  color: #4a7c59;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.8;
}

/* Challenges Section */
.challenges-section {
  padding: 100px 0;
  background: #f8f9fa;
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

.challenges-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.challenge-card {
  background: white;
  padding: 40px 30px;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  text-align: center;
  transition: all 0.3s ease;
}

.challenge-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.challenge-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  margin: 0 auto 25px;
}

.challenge-icon.challenge-1 {
  background: linear-gradient(135deg, #ffeaa7, #fab1a0);
}

.challenge-icon.challenge-2 {
  background: linear-gradient(135deg, #74b9ff, #0984e3);
}

.challenge-icon.challenge-3 {
  background: linear-gradient(135deg, #a29bfe, #6c5ce7);
}

.challenge-card h3 {
  font-size: 1.4rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.challenge-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 25px;
}

.challenge-progress {
  text-align: left;
}

.progress-bar {
  width: 100%;
  height: 8px;
  background: #e9ecef;
  border-radius: 4px;
  overflow: hidden;
  margin-bottom: 8px;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  border-radius: 4px;
  transition: width 1s ease-in-out;
}

.progress-text {
  font-size: 0.9rem;
  color: #666;
  font-weight: 600;
}

/* Volunteer Section */
.volunteer-section {
  padding: 100px 0;
  background: white;
}

.volunteer-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.volunteer-text h2 {
  font-size: 2.5rem;
  color: #0a2e38;
  margin-bottom: 20px;
}

.volunteer-description {
  font-size: 1.2rem;
  line-height: 1.7;
  color: #666;
  margin-bottom: 40px;
}

.volunteer-roles {
  margin-bottom: 40px;
}

.volunteer-roles h3 {
  font-size: 1.5rem;
  color: #0a2e38;
  margin-bottom: 25px;
}

.roles-grid {
  display: grid;
  gap: 20px;
  margin-bottom: 30px;
}

.role-card {
  background: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
  border-left: 4px solid #4a7c59;
  transition: all 0.3s ease;
}

.role-card:hover {
  transform: translateX(10px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.role-icon {
  font-size: 2rem;
  margin-bottom: 15px;
}

.role-card h4 {
  font-size: 1.2rem;
  color: #0a2e38;
  margin-bottom: 10px;
}

.role-card p {
  color: #666;
  margin-bottom: 15px;
  font-size: 0.95rem;
}

.role-tasks {
  list-style: none;
  padding: 0;
  margin: 0;
}

.role-tasks li {
  padding: 5px 0;
  color: #666;
  font-size: 0.9rem;
  position: relative;
  padding-left: 20px;
}

.role-tasks li::before {
  content: '•';
  color: #4a7c59;
  font-weight: bold;
  position: absolute;
  left: 0;
}

.volunteer-visual {
  display: flex;
  justify-content: center;
}

.visual-placeholder {
  width: 100%;
  max-width: 400px;
  height: 300px;
  background: #f8f9fa;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.team-illustration {
  position: relative;
  width: 200px;
  height: 150px;
  margin-bottom: 20px;
}

.person {
  position: absolute;
}

.person-1 { top: 20px; left: 30px; }
.person-2 { top: 40px; left: 80px; }
.person-3 { top: 20px; left: 130px; }

.head {
  width: 25px;
  height: 25px;
  background: #4a7c59;
  border-radius: 50%;
  margin: 0 auto 5px;
}

.body {
  width: 35px;
  height: 40px;
  background: #0a2e38;
  border-radius: 8px;
}

.collaboration-lines {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.line {
  position: absolute;
  height: 2px;
  background: #4a7c59;
  opacity: 0.3;
}

.line:nth-child(1) { top: 35px; left: 55px; right: 55px; }
.line:nth-child(2) { top: 55px; left: 55px; right: 55px; }
.line:nth-child(3) { top: 75px; left: 55px; right: 55px; }

.visual-placeholder p {
  color: #999;
  font-style: italic;
  margin: 0;
}

/* Partnership Section */
.partnership-section {
  padding: 100px 0;
  background: #f8f9fa;
}

.partnership-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.partnership-text h2 {
  font-size: 2.5rem;
  color: #0a2e38;
  margin-bottom: 20px;
}

.partnership-description {
  font-size: 1.2rem;
  line-height: 1.7;
  color: #666;
  margin-bottom: 40px;
}

.partnership-benefits {
  margin-bottom: 30px;
}

.partnership-benefits h3 {
  font-size: 1.5rem;
  color: #0a2e38;
  margin-bottom: 20px;
}

.benefits-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: 12px;
  color: #666;
}

.benefit-icon {
  color: #4a7c59;
  flex-shrink: 0;
}

.partner-types {
  margin-bottom: 40px;
}

.partner-types h3 {
  font-size: 1.5rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.type-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.type-tag {
  background: white;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9rem;
  color: #0a2e38;
  border: 1px solid #4a7c59;
}

.partnership-visual {
  display: flex;
  justify-content: center;
}

.partnership-illustration {
  position: relative;
  width: 300px;
  height: 200px;
}

.org-connection {
  position: relative;
  width: 100%;
  height: 100%;
}

.org {
  position: absolute;
  text-align: center;
}

.org-1 { top: 20px; left: 20px; }
.org-2 { top: 80px; left: 50%; transform: translateX(-50%); }
.org-3 { top: 20px; right: 20px; }

.org-icon {
  font-size: 2rem;
  margin-bottom: 8px;
}

.org-name {
  font-size: 0.9rem;
  color: #0a2e38;
  font-weight: 600;
}

.connection-line {
  position: absolute;
  height: 2px;
  background: #4a7c59;
  opacity: 0.5;
  top: 45px;
}

.connection-line:nth-child(4) { left: 70px; right: 50%; }
.connection-line:nth-child(5) { left: 50%; right: 70px; }

/* Other Ways Section */
.other-ways-section {
  padding: 100px 0;
  background: white;
}

.ways-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  max-width: 1000px;
  margin: 0 auto;
}

.way-card {
  background: #f8f9fa;
  padding: 40px 30px;
  border-radius: 15px;
  text-align: center;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.way-card:hover {
  transform: translateY(-10px);
  border-color: #4a7c59;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.way-icon {
  font-size: 3rem;
  margin-bottom: 20px;
}

.way-card h3 {
  font-size: 1.4rem;
  color: #0a2e38;
  margin-bottom: 15px;
}

.way-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 25px;
}

.way-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #4a7c59;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.way-link:hover {
  gap: 12px;
}

.link-arrow {
  transition: transform 0.3s ease;
}

.way-link:hover .link-arrow {
  transform: translateX(3px);
}

/* CTA Section */
.involved-cta {
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
  color: white;
  border-color: rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-3px);
}

.btn-outline {
  background: transparent;
  color: white;
  border-color: rgba(255, 255, 255, 0.5);
}

.btn-outline:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-3px);
}

.btn-large {
  padding: 18px 35px;
  font-size: 1.1rem;
}

/* Animations */
@keyframes floatShape {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(180deg); }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .volunteer-content,
  .partnership-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .volunteer-visual,
  .partnership-visual {
    order: -1;
  }
}

@media (max-width: 768px) {
  .hero-stats {
    gap: 20px;
  }
  
  .stat-number {
    font-size: 2rem;
  }
  
  .challenges-grid {
    grid-template-columns: 1fr;
  }
  
  .roles-grid {
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
  
  .ways-grid {
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
  
  .type-tags {
    justify-content: center;
  }
}
</style>