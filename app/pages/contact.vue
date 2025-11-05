<template>
  <div class="contact-page">
    <div class="contact-container">
      <!-- Header -->
      <div class="contact-header">
        <h1>Get In Touch</h1>
        <p>We'd love to hear from you. Send us a message and we'll respond as soon as possible.</p>
      </div>

      <!-- Contact Content -->
      <div class="contact-content">
        <!-- Contact Form -->
        <div class="contact-form-section">
          <form class="contact-form" @submit.prevent="submitForm">
            <div class="form-row">
              <div class="form-group">
                <label for="name">Full Name *</label>
                <input 
                  id="name"
                  type="text" 
                  v-model="form.name"
                  placeholder="Your full name"
                  required
                >
              </div>
              <div class="form-group">
                <label for="email">Email Address *</label>
                <input 
                  id="email"
                  type="email" 
                  v-model="form.email"
                  placeholder="your.email@example.com"
                  required
                >
              </div>
            </div>

            <div class="form-group">
              <label for="subject">Subject *</label>
              <select id="subject" v-model="form.subject" required>
                <option value="">Select a subject</option>
                <option value="partnership">Partnership Inquiry</option>
                <option value="volunteer">Volunteer Opportunity</option>
                <option value="donation">Donation Question</option>
                <option value="technology">Technology Information</option>
                <option value="general">General Inquiry</option>
              </select>
            </div>

            <div class="form-group">
              <label for="message">Message *</label>
              <textarea 
                id="message"
                v-model="form.message"
                placeholder="Tell us how we can help you..."
                rows="5"
                required
              ></textarea>
            </div>

            <button 
              type="submit" 
              class="submit-btn"
              :disabled="submitting"
            >
              <span v-if="!submitting">Send Message</span>
              <span v-else class="submitting">
                <svg class="spinner" viewBox="0 0 24 24" width="18" height="18">
                  <path fill="currentColor" d="M12,4V2A10,10 0 0,0 2,12H4A8,8 0 0,1 12,4Z"/>
                </svg>
                Sending...
              </span>
            </button>
          </form>
        </div>

        <!-- Contact Info -->
        <div class="contact-info">
          <div class="info-card">
            <h3>Contact Information</h3>
            
            <div class="info-item">
              <div class="info-icon">📧</div>
              <div class="info-content">
                <strong>Email</strong>
                <p>contact@repower.org</p>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon">🌐</div>
              <div class="info-content">
                <strong>Based In</strong>
                <p>Tunis, Tunisia</p>
              </div>
            </div>

            <div class="info-item">
              <div class="info-icon">🕒</div>
              <div class="info-content">
                <strong>Response Time</strong>
                <p>Within 24 hours</p>
              </div>
            </div>

            <div class="quick-links">
              <h4>Quick Links</h4>
              <div class="links">
                <NuxtLink to="/volunteer" class="link">Volunteer Program</NuxtLink>
                <NuxtLink to="/partnership" class="link">Partnerships</NuxtLink>
                <NuxtLink to="/donate" class="link">Make a Donation</NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const submitting = ref(false)

const submitForm = async () => {
  submitting.value = true
  
  // Simulate form submission
  await new Promise(resolve => setTimeout(resolve, 1500))
  
  // In real app, this would send to your backend
  console.log('Form submitted:', form.value)
  
  // Show success message
  alert('Thank you for your message! We will get back to you soon.')
  
  // Reset form
  form.value = {
    name: '',
    email: '',
    subject: '',
    message: ''
  }
  
  submitting.value = false
}
</script>

<style scoped>
.contact-page {
  min-height: 80vh;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  padding: 60px 20px;
}

.contact-container {
  max-width: 1000px;
  margin: 0 auto;
}

.contact-header {
  text-align: center;
  margin-bottom: 50px;
}

.contact-header h1 {
  font-size: 2.5rem;
  color: #0a2e38;
  margin-bottom: 15px;
  font-weight: 800;
}

.contact-header p {
  font-size: 1.2rem;
  color: #666;
  max-width: 500px;
  margin: 0 auto;
  line-height: 1.6;
}

.contact-content {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 50px;
  align-items: start;
}

/* Contact Form */
.contact-form-section {
  background: white;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-group label {
  font-weight: 600;
  color: #0a2e38;
  font-size: 0.9rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  padding: 12px 15px;
  border: 2px solid #e9ecef;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #4a7c59;
}

.form-group textarea {
  resize: vertical;
  min-height: 120px;
}

.submit-btn {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  border: none;
  padding: 16px;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 10px;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(46, 204, 113, 0.3);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
  transform: none;
}

.submitting {
  display: flex;
  align-items: center;
  gap: 10px;
  justify-content: center;
}

.spinner {
  animation: spin 1s linear infinite;
}

/* Contact Info */
.contact-info {
  position: sticky;
  top: 20px;
}

.info-card {
  background: white;
  padding: 35px;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  height: fit-content;
}

.info-card h3 {
  color: #0a2e38;
  margin-bottom: 25px;
  font-size: 1.3rem;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 15px;
  padding: 20px 0;
  border-bottom: 1px solid #e9ecef;
}

.info-item:last-child {
  border-bottom: none;
}

.info-icon {
  font-size: 1.2rem;
  flex-shrink: 0;
}

.info-content strong {
  color: #0a2e38;
  display: block;
  margin-bottom: 4px;
}

.info-content p {
  color: #666;
  margin: 0;
  font-size: 0.95rem;
}

.quick-links {
  margin-top: 30px;
  padding-top: 25px;
  border-top: 1px solid #e9ecef;
}

.quick-links h4 {
  color: #0a2e38;
  margin-bottom: 15px;
  font-size: 1.1rem;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.link {
  color: #4a7c59;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  padding: 8px 0;
}

.link:hover {
  color: #2ecc71;
}

/* Animations */
@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* Responsive Design */
@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .contact-info {
    position: static;
  }
  
  .form-row {
    grid-template-columns: 1fr;
  }
  
  .contact-header h1 {
    font-size: 2rem;
  }
  
  .contact-form-section,
  .info-card {
    padding: 30px 25px;
  }
}

@media (max-width: 480px) {
  .contact-page {
    padding: 40px 15px;
  }
  
  .contact-header h1 {
    font-size: 1.8rem;
  }
  
  .contact-form-section,
  .info-card {
    padding: 25px 20px;
  }
}
</style>