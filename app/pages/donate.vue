<template>
  <div class="donate-page">
    <!-- Main Content -->
    <div class="donate-container">
      <div class="donate-content">
        <!-- Left Column: Information -->
        <div class="donate-info">
          <h1 class="donate-title">Your Support is Our Power</h1>
          
          <div class="need-section">
            <p class="need-text">
              Our biggest challenge is raising enough funds to scale the project. 
              Your donation directly funds the development and distribution of Power Skin 
              patches to the communities who need them most.
            </p>
          </div>

          <!-- Impact Tiers -->
          <div class="impact-tiers">
            <h3>Your Impact</h3>
            <div class="tier" v-for="tier in impactTiers" :key="tier.amount">
              <div class="tier-amount">${{ tier.amount }}</div>
              <div class="tier-description">{{ tier.description }}</div>
            </div>
          </div>

          <!-- Security & Trust -->
          <div class="security-section">
            <div class="security-badge">
              <svg class="lock-icon" viewBox="0 0 24 24" width="20" height="20">
                <path fill="currentColor" d="M12,17A2,2 0 0,0 14,15C14,13.89 13.1,13 12,13A2,2 0 0,0 10,15A2,2 0 0,0 12,17M18,8A2,2 0 0,1 20,10V20A2,2 0 0,1 18,22H6A2,2 0 0,1 4,20V10C4,8.89 4.9,8 6,8H7V6A5,5 0 0,1 12,1A5,5 0 0,1 17,6V8H18M12,3A3,3 0 0,0 9,6V8H15V6A3,3 0 0,0 12,3Z"/>
              </svg>
              <span>Secure & Encrypted Donation</span>
            </div>
          </div>
        </div>

        <!-- Right Column: Donation Form -->
        <div class="donate-form-section">
          <div class="form-container">
            <div class="form-header">
              <h3>Make a Donation</h3>
              <p>Every contribution makes a difference</p>
            </div>

            <!-- Quick Amount Selection -->
            <div class="amount-selection">
              <h4>Select Amount</h4>
              <div class="amount-buttons">
                <button 
                  v-for="amount in quickAmounts" 
                  :key="amount"
                  class="amount-btn"
                  :class="{ active: selectedAmount === amount }"
                  @click="selectAmount(amount)"
                >
                  ${{ amount }}
                </button>
                <div class="custom-amount">
                  <input 
                    type="number" 
                    placeholder="Other amount"
                    v-model="customAmount"
                    @focus="selectCustomAmount"
                  >
                </div>
              </div>
            </div>

            <!-- Donation Form -->
            <form class="donation-form" @submit.prevent="processDonation">
              <div class="form-group">
                <label for="name">Full Name</label>
                <input 
                  id="name"
                  type="text" 
                  v-model="donorInfo.name"
                  placeholder="Enter your full name"
                  required
                >
              </div>

              <div class="form-group">
                <label for="email">Email Address</label>
                <input 
                  id="email"
                  type="email" 
                  v-model="donorInfo.email"
                  placeholder="Enter your email"
                  required
                >
              </div>

              <div class="form-group">
                <label for="payment">Payment Method</label>
                <select id="payment" v-model="donorInfo.paymentMethod" required>
                  <option value="">Select payment method</option>
                  <option value="credit">Credit Card</option>
                  <option value="paypal">PayPal</option>
                  <option value="bank">Bank Transfer</option>
                </select>
              </div>

              <!-- Credit Card Fields (shown when credit card selected) -->
              <div class="credit-card-fields" v-if="donorInfo.paymentMethod === 'credit'">
                <div class="form-group">
                  <label for="cardNumber">Card Number</label>
                  <input 
                    id="cardNumber"
                    type="text" 
                    placeholder="1234 5678 9012 3456"
                    maxlength="19"
                  >
                </div>
                <div class="card-details">
                  <div class="form-group">
                    <label for="expiry">Expiry Date</label>
                    <input 
                      id="expiry"
                      type="text" 
                      placeholder="MM/YY"
                      maxlength="5"
                    >
                  </div>
                  <div class="form-group">
                    <label for="cvv">CVV</label>
                    <input 
                      id="cvv"
                      type="text" 
                      placeholder="123"
                      maxlength="3"
                    >
                  </div>
                </div>
              </div>

              <button 
                type="submit" 
                class="donate-btn"
                :disabled="processing"
              >
                <span v-if="!processing">
                  Donate ${{ donationAmount }}
                </span>
                <span v-else class="processing">
                  <svg class="spinner" viewBox="0 0 24 24" width="20" height="20">
                    <path fill="currentColor" d="M12,4V2A10,10 0 0,0 2,12H4A8,8 0 0,1 12,4Z"/>
                  </svg>
                  Processing...
                </span>
              </button>

              <div class="secure-note">
                <svg class="shield-icon" viewBox="0 0 24 24" width="16" height="16">
                  <path fill="currentColor" d="M12,1L3,5V11C3,16.55 6.84,21.74 12,23C17.16,21.74 21,16.55 21,11V5L12,1M12,7C13.4,7 14.8,8.6 14.8,10V11.5C15.4,11.5 16,12.1 16,12.7V16.5C16,17.1 15.4,17.7 14.8,17.7H9.2C8.6,17.7 8,17.1 8,16.5V12.6C8,12 8.6,11.4 9.2,11.4V10C9.2,8.6 10.6,7 12,7M12,8.2C11.2,8.2 10.5,8.7 10.5,9.5V11.5H13.5V9.5C13.5,8.7 12.8,8.2 12,8.2Z"/>
                </svg>
                Your donation is secure and encrypted
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>

    <!-- Hope Image Section -->
    <div class="hope-section">
      <div class="hope-image">
        <div class="image-placeholder">
          <div class="person-illustration">
            <div class="person">
              <div class="head"></div>
              <div class="body"></div>
            </div>
            <div class="light-effect"></div>
          </div>
          <p>Bringing light to communities in need</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Reactive data
const selectedAmount = ref(50)
const customAmount = ref('')
const processing = ref(false)

const donorInfo = ref({
  name: '',
  email: '',
  paymentMethod: ''
})

// Impact tiers data
const impactTiers = [
  { amount: 25, description: 'Helps us build community trust and awareness' },
  { amount: 50, description: 'Funds the materials for one Power Skin patch' },
  { amount: 100, description: 'Supports volunteer recruitment in a remote area' },
  { amount: 250, description: 'Provides training for local energy ambassadors' }
]

// Quick amount options
const quickAmounts = [25, 50, 100, 250, 500]

// Computed donation amount
const donationAmount = computed(() => {
  return customAmount.value || selectedAmount.value
})

// Methods
const selectAmount = (amount) => {
  selectedAmount.value = amount
  customAmount.value = ''
}

const selectCustomAmount = () => {
  selectedAmount.value = 0
}

const processDonation = async () => {
  processing.value = true
  
  // Simulate donation processing
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  // In a real application, this would integrate with a payment processor
  console.log('Processing donation:', {
    amount: donationAmount.value,
    donor: donorInfo.value
  })
  
  processing.value = false
  
  // Show success message or redirect to thank you page
  alert(`Thank you for your donation of $${donationAmount.value}!`)
  
  // Reset form
  donorInfo.value = {
    name: '',
    email: '',
    paymentMethod: ''
  }
  selectedAmount.value = 50
  customAmount.value = ''
}
</script>

<style scoped>
.donate-page {
  min-height: 100vh;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  display: flex;
  flex-direction: column;
}

.donate-container {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
}

.donate-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  max-width: 1200px;
  width: 100%;
  align-items: start;
}

/* Left Column - Information */
.donate-info {
  padding: 40px 0;
}

.donate-title {
  font-size: 2.5rem;
  font-weight: 800;
  color: #0a2e38;
  margin-bottom: 30px;
  line-height: 1.2;
}

.need-section {
  margin-bottom: 40px;
}

.need-text {
  font-size: 1.2rem;
  line-height: 1.6;
  color: #666;
  margin: 0;
}

.impact-tiers {
  background: white;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
  margin-bottom: 30px;
}

.impact-tiers h3 {
  color: #0a2e38;
  margin-bottom: 20px;
  font-size: 1.3rem;
}

.tier {
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 15px 0;
  border-bottom: 1px solid #e9ecef;
}

.tier:last-child {
  border-bottom: none;
}

.tier-amount {
  font-size: 1.5rem;
  font-weight: 800;
  color: #4a7c59;
  min-width: 60px;
}

.tier-description {
  color: #666;
  line-height: 1.4;
}

.security-section {
  text-align: center;
}

.security-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 15px 25px;
  background: white;
  border-radius: 25px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  color: #4a7c59;
  font-weight: 600;
}

.lock-icon {
  color: #4a7c59;
}

/* Right Column - Donation Form */
.donate-form-section {
  position: sticky;
  top: 20px;
}

.form-container {
  background: white;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
  border: 1px solid #e9ecef;
}

.form-header {
  text-align: center;
  margin-bottom: 30px;
}

.form-header h3 {
  font-size: 1.5rem;
  color: #0a2e38;
  margin-bottom: 8px;
}

.form-header p {
  color: #666;
  margin: 0;
}

.amount-selection {
  margin-bottom: 30px;
}

.amount-selection h4 {
  color: #0a2e38;
  margin-bottom: 15px;
  font-size: 1.1rem;
}

.amount-buttons {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  margin-bottom: 15px;
}

.amount-btn {
  padding: 12px;
  border: 2px solid #e9ecef;
  background: white;
  border-radius: 8px;
  font-weight: 600;
  color: #666;
  cursor: pointer;
  transition: all 0.3s ease;
}

.amount-btn:hover {
  border-color: #4a7c59;
  color: #4a7c59;
}

.amount-btn.active {
  background: #4a7c59;
  border-color: #4a7c59;
  color: white;
}

.custom-amount {
  grid-column: 1 / -1;
}

.custom-amount input {
  width: 100%;
  padding: 12px 15px;
  border: 2px solid #e9ecef;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.custom-amount input:focus {
  outline: none;
  border-color: #4a7c59;
}

.donation-form {
  display: flex;
  flex-direction: column;
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
.form-group select {
  padding: 12px 15px;
  border: 2px solid #e9ecef;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group select:focus {
  outline: none;
  border-color: #4a7c59;
}

.credit-card-fields {
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 8px;
  border: 1px solid #e9ecef;
}

.card-details {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

.donate-btn {
  background: linear-gradient(135deg, #4a7c59, #2ecc71);
  color: white;
  border: none;
  padding: 18px;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 10px;
}

.donate-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(46, 204, 113, 0.3);
}

.donate-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
  transform: none;
}

.processing {
  display: flex;
  align-items: center;
  gap: 10px;
  justify-content: center;
}

.spinner {
  animation: spin 1s linear infinite;
}

.secure-note {
  display: flex;
  align-items: center;
  gap: 8px;
  justify-content: center;
  color: #666;
  font-size: 0.9rem;
  margin-top: 15px;
}

.shield-icon {
  color: #4a7c59;
}

/* Hope Section */
.hope-section {
  background: linear-gradient(135deg, #0a2e38 0%, #1a4a5a 100%);
  padding: 60px 20px;
  text-align: center;
  color: white;
}

.hope-image {
  max-width: 400px;
  margin: 0 auto;
}

.image-placeholder {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.person-illustration {
  position: relative;
  width: 120px;
  height: 150px;
}

.person {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
}

.head {
  width: 40px;
  height: 40px;
  background: white;
  border-radius: 50%;
  margin: 0 auto 10px;
}

.body {
  width: 60px;
  height: 80px;
  background: white;
  border-radius: 30px;
}

.light-effect {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 80px;
  background: radial-gradient(circle, rgba(46, 204, 113, 0.6) 0%, transparent 70%);
  border-radius: 50%;
  animation: glowPulse 2s ease-in-out infinite;
}

.image-placeholder p {
  margin: 0;
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Animations */
@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes glowPulse {
  0%, 100% { opacity: 0.6; transform: translateX(-50%) scale(1); }
  50% { opacity: 1; transform: translateX(-50%) scale(1.1); }
}

/* Responsive Design */
@media (max-width: 1024px) {
  .donate-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .donate-form-section {
    position: static;
  }
}

@media (max-width: 768px) {
  .donate-container {
    padding: 20px 15px;
  }
  
  .donate-title {
    font-size: 2rem;
  }
  
  .form-container {
    padding: 30px 25px;
  }
  
  .amount-buttons {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .card-details {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .donate-title {
    font-size: 1.8rem;
  }
  
  .form-container {
    padding: 25px 20px;
  }
  
  .impact-tiers {
    padding: 25px 20px;
  }
  
  .tier {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }
}
</style>