<template>
  <footer class="footer">
    <!-- Animated Background -->
    <div class="footer-background">
      <div class="energy-wave"></div>
      <div class="floating-patches">
        <div class="patch" v-for="i in 6" :key="i" :style="getPatchStyle(i)"></div>
      </div>
    </div>

    <div class="container">
      <!-- Mission Statement -->
      <div class="mission-section">
        <div class="mission-content">
          <h3>Transforming Human Energy into Clean Power</h3>
          <p>RePower supports <strong>SDG 7</strong> by ensuring access to affordable, reliable, sustainable, and modern energy for all through innovative wearable technology.</p>
          
          <div class="values-grid">
            <div class="value-item" v-for="value in values" :key="value">
              <div class="value-icon">{{ getValueIcon(value) }}</div>
              <span>{{ value }}</span>
            </div>
          </div>
        </div>
        
        <div class="technology-visual">
          <div class="skin-patch-demo">
            <div class="patch-graphic">
              <div class="energy-flow"></div>
              <div class="human-silhouette"></div>
            </div>
            <p>Power Skin Patch - Generating electricity from body heat and movement</p>
          </div>
        </div>
      </div>

      <!-- Main Footer Content -->


      <!-- Bottom Bar -->
      <div class="footer-bottom">
        <div class="copyright">
          <p>&copy; {{ new Date().getFullYear() }} RePower NGO. Empowering communities through clean energy innovation.</p>
        </div>
        
        <div class="footer-links">
          <NuxtLink to="/privacy">Privacy Policy</NuxtLink>
          <NuxtLink to="/terms">Terms of Service</NuxtLink>
          <NuxtLink to="/accessibility">Accessibility</NuxtLink>
        </div>
        
        <div class="social-links">
          <a href="#" aria-label="LinkedIn" class="social-link">
            <svg viewBox="0 0 24 24" width="18" height="18">
              <path fill="currentColor" d="M19 3A2 2 0 0 1 21 5V19A2 2 0 0 1 19 21H5A2 2 0 0 1 3 19V5A2 2 0 0 1 5 3H19M18.5 18.5V13.2A3.26 3.26 0 0 0 15.24 9.94C14.39 9.94 13.4 10.46 12.92 11.24V10.13H10.13V18.5H12.92V13.57C12.92 12.8 13.54 12.17 14.31 12.17A1.4 1.4 0 0 1 15.71 13.57V18.5H18.5M6.88 8.56A1.68 1.68 0 0 0 8.56 6.88C8.56 5.95 7.81 5.19 6.88 5.19A1.69 1.69 0 0 0 5.19 6.88C5.19 7.81 5.95 8.56 6.88 8.56M8.27 18.5V10.13H5.5V18.5H8.27Z"/>
            </svg>
          </a>
          <a href="#" aria-label="Twitter" class="social-link">
            <svg viewBox="0 0 24 24" width="18" height="18">
              <path fill="currentColor" d="M22.46,6C21.69,6.35 20.86,6.58 20,6.69C20.88,6.16 21.56,5.32 21.88,4.31C21.05,4.81 20.13,5.16 19.16,5.36C18.37,4.5 17.26,4 16,4C13.65,4 11.73,5.92 11.73,8.29C11.73,8.63 11.77,8.96 11.84,9.27C8.28,9.09 5.11,7.38 3,4.79C2.63,5.42 2.42,6.16 2.42,6.94C2.42,8.43 3.17,9.75 4.33,10.5C3.62,10.5 2.96,10.3 2.38,10C2.38,10 2.38,10 2.38,10.03C2.38,12.11 3.86,13.85 5.82,14.24C5.46,14.34 5.08,14.39 4.69,14.39C4.42,14.39 4.15,14.36 3.89,14.31C4.43,16 6,17.26 7.89,17.29C6.43,18.45 4.58,19.13 2.56,19.13C2.22,19.13 1.88,19.11 1.54,19.07C3.44,20.29 5.7,21 8.12,21C16,21 20.33,14.46 20.33,8.79C20.33,8.6 20.33,8.42 20.32,8.23C21.16,7.63 21.88,6.87 22.46,6Z"/>
            </svg>
          </a>
          <a href="#" aria-label="Instagram" class="social-link">
            <svg viewBox="0 0 24 24" width="18" height="18">
              <path fill="currentColor" d="M7.8,2H16.2C19.4,2 22,4.6 22,7.8V16.2A5.8,5.8 0 0,1 16.2,22H7.8C4.6,22 2,19.4 2,16.2V7.8A5.8,5.8 0 0,1 7.8,2M7.6,4A3.6,3.6 0 0,0 4,7.6V16.4C4,18.39 5.61,20 7.6,20H16.4A3.6,3.6 0 0,0 20,16.4V7.6C20,5.61 18.39,4 16.4,4H7.6M17.25,5.5A1.25,1.25 0 0,1 18.5,6.75A1.25,1.25 0 0,1 17.25,8A1.25,1.25 0 0,1 16,6.75A1.25,1.25 0 0,1 17.25,5.5M12,7A5,5 0 0,1 17,12A5,5 0 0,1 12,17A5,5 0 0,1 7,12A5,5 0 0,1 12,7M12,9A3,3 0 0,0 9,12A3,3 0 0,0 12,15A3,3 0 0,0 15,12A3,3 0 0,0 12,9Z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const values = ['Innovation', 'Sustainability', 'Accessibility', 'Empowerment']

const getValueIcon = (value) => {
  const icons = {
    'Innovation': '💡',
    'Sustainability': '🌱',
    'Accessibility': '👥',
    'Empowerment': '⚡'
  }
  return icons[value] || '✨'
}

const getPatchStyle = (index) => {
  const delay = index * 0.5
  const duration = 15 + (index * 2)
  return {
    'animation-delay': `${delay}s`,
    'animation-duration': `${duration}s`
  }
}
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  color: white;
  position: relative;
  overflow: hidden;
}

.footer-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.energy-wave {
  position: absolute;
  top: -100px;
  left: 0;
  right: 0;
  height: 200px;
  background: linear-gradient(180deg, rgba(74, 124, 89, 0.1) 0%, transparent 100%);
  border-radius: 50% 50% 0 0;
  animation: waveMove 8s ease-in-out infinite;
}

.floating-patches {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.patch {
  position: absolute;
  width: 60px;
  height: 40px;
  background: linear-gradient(45deg, rgba(74, 124, 89, 0.3), rgba(46, 204, 113, 0.2));
  border-radius: 20px;
  animation: floatPatch linear infinite;
  opacity: 0.6;
}

.patch:nth-child(1) { top: 10%; left: 5%; }
.patch:nth-child(2) { top: 30%; right: 10%; }
.patch:nth-child(3) { top: 60%; left: 15%; }
.patch:nth-child(4) { top: 20%; right: 20%; }
.patch:nth-child(5) { top: 70%; right: 5%; }
.patch:nth-child(6) { top: 40%; left: 8%; }

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 60px 20px 20px;
  position: relative;
  z-index: 1;
}

/* Mission Section */
.mission-section {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 60px;
  margin-bottom: 60px;
  padding-bottom: 40px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.mission-content h3 {
  font-size: 2rem;
  margin-bottom: 20px;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.mission-content p {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 30px;
  opacity: 0.9;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.value-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  transition: all 0.3s ease;
}

.value-item:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-2px);
}

.value-icon {
  font-size: 1.2rem;
}

.technology-visual {
  display: flex;
  align-items: center;
  justify-content: center;
}

.skin-patch-demo {
  text-align: center;
}

.patch-graphic {
  width: 120px;
  height: 160px;
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  border-radius: 20px;
  position: relative;
  margin: 0 auto 20px;
  box-shadow: 0 10px 30px rgba(46, 204, 113, 0.3);
}

.energy-flow {
  position: absolute;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 60px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 2px;
  animation: energyPulse 2s ease-in-out infinite;
}

.human-silhouette {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 60px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 20px;
}

/* Footer Content */
.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 60px;
  margin-bottom: 40px;
}

.footer-sections {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
}

.footer-section h4 {
  color: #4a7c59;
  margin-bottom: 20px;
  font-size: 1.1rem;
}

.footer-section ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-section li {
  margin-bottom: 12px;
}

.footer-section a {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
}

.footer-section a:hover {
  color: #4a7c59;
  padding-left: 8px;
}

.footer-section a::before {
  content: '';
  position: absolute;
  left: -8px;
  top: 50%;
  transform: translateY(-50%);
  width: 4px;
  height: 4px;
  background: #4a7c59;
  border-radius: 50%;
  opacity: 0;
  transition: all 0.3s ease;
}

.footer-section a:hover::before {
  opacity: 1;
  left: 0;
}

/* CTA Section */
.footer-cta {
  background: linear-gradient(135deg, rgba(74, 124, 89, 0.2), rgba(46, 204, 113, 0.1));
  padding: 30px;
  border-radius: 12px;
  border: 1px solid rgba(74, 124, 89, 0.3);
}

.footer-cta h4 {
  margin-bottom: 10px;
  font-size: 1.3rem;
}

.footer-cta p {
  opacity: 0.9;
  margin-bottom: 20px;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 25px;
}

.btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 12px 20px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  text-align: center;
}

.btn-primary {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(46, 204, 113, 0.4);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.sdg-badge {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 15px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  border-left: 4px solid #4a7c59;
}

.sdg-icon {
  background: #4a7c59;
  color: white;
  padding: 8px 12px;
  border-radius: 4px;
  font-weight: bold;
  font-size: 0.9rem;
}

/* Footer Bottom */
.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 30px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  flex-wrap: wrap;
  gap: 20px;
}

.copyright p {
  opacity: 0.7;
  margin: 0;
}

.footer-links {
  display: flex;
  gap: 20px;
}

.footer-links a {
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #4a7c59;
}

.social-links {
  display: flex;
  gap: 15px;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: #4a7c59;
  transform: translateY(-2px);
}

/* Animations */
@keyframes waveMove {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@keyframes floatPatch {
  0% { transform: translateY(100px) rotate(0deg); opacity: 0; }
  10% { opacity: 0.6; }
  90% { opacity: 0.6; }
  100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
}

@keyframes energyPulse {
  0%, 100% { opacity: 0.3; height: 40px; }
  50% { opacity: 1; height: 60px; }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .footer-sections {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .mission-section {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .values-grid {
    grid-template-columns: 1fr;
  }
  
  .footer-sections {
    grid-template-columns: 1fr;
  }
  
  .footer-bottom {
    flex-direction: column;
    text-align: center;
  }
  
  .footer-links {
    justify-content: center;
  }
}
</style>