<script>
  import { createEventDispatcher, onMount } from 'svelte';
  
  const dispatch = createEventDispatcher();
  
  let name = '';
  let email = '';
  let company = '';
  let isSubmitting = false;
  
  onMount(() => {
    // Add staggered animation delays to orbs
    const orbs = document.querySelectorAll('.orb');
    orbs.forEach((orb, index) => {
      orb.style.animationDelay = `${index * 0.5}s`;
    });
  });
  
  async function handleSubmit(event) {
    event.preventDefault();
    
    if (isSubmitting) return;
    
    isSubmitting = true;
    
    try {
      // Simulate API call
      await new Promise(resolve => setTimeout(resolve, 1000));
      
      // Dispatch success event
      dispatch('form-submit', {
        name,
        email,
        company
      });
      
      // Show success message
      alert(`Application submitted successfully!\nName: ${name}\nEmail: ${email}\nCompany: ${company}`);
      
      // Reset form
      name = '';
      email = '';
      company = '';
      
    } catch (error) {
      console.error('Submission error:', error);
      alert('Something went wrong. Please try again.');
    } finally {
      isSubmitting = false;
    }
  }
</script>

<section class="hero">
  <!-- Background Animation - contained within hero section -->
  <div class="cosmic-background">
    <!-- Small floating orbs scattered throughout -->
    <div class="orb orb-small orb-1"></div>
    <div class="orb orb-small orb-2"></div>
    <div class="orb orb-small orb-3"></div>
    <div class="orb orb-small orb-4"></div>
    <div class="orb orb-small orb-5"></div>
    
    <!-- Medium orbs -->
    <div class="orb orb-medium orb-6"></div>
    <div class="orb orb-medium orb-7"></div>
    
    <!-- Large floating orbs positioned like in the image -->
    <div class="orb orb-large orb-main-1"></div>
    <div class="orb orb-large orb-main-2"></div>
    <div class="orb orb-large orb-main-3"></div>
    <div class="orb orb-large orb-main-4"></div>
    
    <!-- Extra large gradient orbs -->
    <div class="orb orb-xlarge orb-gradient-1"></div>
    <div class="orb orb-xlarge orb-gradient-2"></div>
    
    <!-- Stars -->
    <div class="stars"></div>
    <div class="stars stars-2"></div>
  </div>
  
  <div class="container">
    <div class="content-wrapper">
      <div class="hero-content">
        <h1>Join the CometChat partner universe</h1>
        <p>Create value for your clients, leveraging our world-class technology. Partner with us and grow your business!</p>
      </div>
      
      <div class="form-container">
        <div class="form-card">
          <h2>Become a partner</h2>
          <form class="partner-form" on:submit={handleSubmit}>
            <div class="form-group">
              <label for="fullname">Full name</label>
              <input 
                type="text" 
                id="fullname" 
                bind:value={name}
                placeholder="Type your name here..."
                required
                disabled={isSubmitting}
              />
            </div>
            
            <div class="form-group">
              <label for="email">Email address</label>
              <div class="input-with-icon">
                <span class="email-icon">✉</span>
                <input 
                  type="email" 
                  id="email" 
                  bind:value={email}
                  placeholder="Type your email here..."
                  required
                  disabled={isSubmitting}
                />
              </div>
            </div>
            
            <div class="form-group">
              <label for="company">Company name</label>
              <input 
                type="text" 
                id="company" 
                bind:value={company}
                placeholder="Type your company's name"
                required
                disabled={isSubmitting}
              />
            </div>
            
            <button 
              type="submit" 
              class="submit-btn"
              disabled={isSubmitting}
            >
              {#if isSubmitting}
                <span class="spinner"></span>
                Submitting...
              {:else}
                Submit application
              {/if}
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .hero {
    /* Take up most of viewport but leave space for customers section */
    height: 75vh;
    min-height: 600px;
    display: flex;
    align-items: center;
    padding-top: 80px; /* Account for fixed header */
    position: relative;
    overflow: hidden;
    /* Ensure content is above background */
    z-index: 1;
  }

  /* Background Animation Styles - contained within hero */
  .cosmic-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      135deg, 
      #0a0a1a 0%, 
      #1a1a2e 20%, 
      #16213e 40%, 
      #0f1419 60%, 
      #1a1a2e 80%, 
      #16213e 100%
    );
    z-index: -1;
    overflow: hidden;
  }

  .container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
    position: relative;
    z-index: 2;
  }

  .content-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }

  .hero-content {
    color: white;
  }

  .hero-content h1 {
    font-size: 2.8rem;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 1.5rem;
    background: linear-gradient(135deg, #ffffff 0%, #e0e7ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
  }

  .hero-content p {
    font-size: 1.2rem;
    line-height: 1.6;
    color: rgba(255, 255, 255, 0.9);
    max-width: 500px;
  }

  .form-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .form-card {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border-radius: 20px;
    padding: 2rem;
    border: 1px solid rgba(255, 255, 255, 0.2);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
    width: 100%;
    max-width: 380px;
    transition: transform 0.3s ease;
  }

  .form-card:hover {
    transform: translateY(-5px);
  }

  .form-card h2 {
    color: white;
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 1.5rem;
    text-align: left;
  }

  .partner-form {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .form-group label {
    color: white;
    font-size: 0.9rem;
    font-weight: 500;
  }

  .form-group input {
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 12px;
    padding: 0.8rem;
    color: white;
    font-size: 0.95rem;
    transition: all 0.3s ease;
  }

  .form-group input::placeholder {
    color: rgba(255, 255, 255, 0.5);
  }

  .form-group input:focus {
    outline: none;
    border-color: #667eea;
    box-shadow: 0 0 0 2px rgba(102, 126, 234, 0.3);
    background: rgba(255, 255, 255, 0.15);
  }

  .form-group input:disabled {
    opacity: 0.6;
    cursor: not-allowed;
  }

  .input-with-icon {
    position: relative;
  }

  .input-with-icon input {
    padding-left: 2.8rem;
  }

  .email-icon {
    position: absolute;
    left: 0.8rem;
    top: 50%;
    transform: translateY(-50%);
    color: rgba(255, 255, 255, 0.6);
    font-size: 1rem;
  }

  .submit-btn {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: none;
    border-radius: 12px;
    padding: 1rem 2rem;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
  }

  .submit-btn:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
  }

  .submit-btn:active:not(:disabled) {
    transform: translateY(0);
  }

  .submit-btn:disabled {
    opacity: 0.7;
    cursor: not-allowed;
    transform: none;
  }

  .spinner {
    width: 16px;
    height: 16px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    border-top: 2px solid white;
    border-radius: 50%;
    animation: spin 1s linear infinite;
  }

  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  /* Base orb styles */
  .orb {
    position: absolute;
    border-radius: 50%;
    animation: float 12s ease-in-out infinite;
    filter: blur(0.8px);
  }

  .orb::before {
    content: '';
    position: absolute;
    top: 20%;
    left: 25%;
    width: 30%;
    height: 30%;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 50%;
    filter: blur(2px);
  }

  .orb::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.15) 0%, transparent 60%);
  }

  /* Small orbs scattered around */
  .orb-small {
    opacity: 0.7;
    width: 30px;
    height: 30px;
  }

  .orb-1 {
    background: linear-gradient(45deg, #4a4a7a, #6a6aaa);
    top: 15%;
    left: 15%;
    animation-delay: 0s;
    box-shadow: 
      0 0 30px rgba(74, 74, 122, 0.4),
      0 0 60px rgba(106, 106, 170, 0.3);
  }

  .orb-2 {
    background: linear-gradient(45deg, #5a4a7a, #7a6aaa);
    top: 10%;
    right: 20%;
    animation-delay: 1s;
    box-shadow: 
      0 0 30px rgba(90, 74, 122, 0.4),
      0 0 60px rgba(122, 106, 170, 0.3);
  }

  .orb-3 {
    background: linear-gradient(45deg, #4a5a7a, #6a7aaa);
    top: 25%;
    left: 70%;
    animation-delay: 2s;
    box-shadow: 
      0 0 30px rgba(74, 90, 122, 0.4),
      0 0 60px rgba(106, 122, 170, 0.3);
  }

  .orb-4 {
    background: linear-gradient(45deg, #6a4a7a, #8a6aaa);
    top: 60%;
    left: 10%;
    animation-delay: 3s;
    box-shadow: 
      0 0 30px rgba(106, 74, 122, 0.4),
      0 0 60px rgba(138, 106, 170, 0.3);
  }

  .orb-5 {
    background: linear-gradient(45deg, #4a6a7a, #6a8aaa);
    top: 70%;
    right: 15%;
    animation-delay: 4s;
    box-shadow: 
      0 0 30px rgba(74, 106, 122, 0.4),
      0 0 60px rgba(106, 138, 170, 0.3);
  }

  /* Medium orbs */
  .orb-medium {
    opacity: 0.8;
    width: 60px;
    height: 60px;
  }

  .orb-6 {
    background: linear-gradient(45deg, #7a5a9a, #9a7aba);
    top: 45%;
    left: 80%;
    animation-delay: 2.5s;
    box-shadow: 
      0 0 40px rgba(122, 90, 154, 0.5),
      0 0 80px rgba(154, 122, 186, 0.4);
  }

  .orb-7 {
    background: linear-gradient(45deg, #5a7a9a, #7a9aba);
    top: 35%;
    left: 5%;
    animation-delay: 3.5s;
    box-shadow: 
      0 0 40px rgba(90, 122, 154, 0.5),
      0 0 80px rgba(122, 154, 186, 0.4);
  }

  /* Large orbs positioned like in the image */
  .orb-large {
    opacity: 0.9;
  }

  .orb-main-1 {
    width: 200px;
    height: 200px;
    background: linear-gradient(45deg, #d2691e, #ff8c00, #ffa500);
    bottom: -10%;
    left: -8%;
    animation-delay: 1s;
    box-shadow: 
      0 0 80px rgba(210, 105, 30, 0.5),
      0 0 150px rgba(255, 140, 0, 0.4),
      0 0 200px rgba(255, 165, 0, 0.3);
  }

  .orb-main-2 {
    width: 160px;
    height: 160px;
    background: linear-gradient(45deg, #9370db, #ba55d3, #dda0dd);
    bottom: -5%;
    right: -6%;
    animation-delay: 2s;
    box-shadow: 
      0 0 70px rgba(147, 112, 219, 0.5),
      0 0 130px rgba(186, 85, 211, 0.4),
      0 0 180px rgba(221, 160, 221, 0.3);
  }

  .orb-main-3 {
    width: 120px;
    height: 120px;
    background: linear-gradient(45deg, #8b5a9f, #b19cd9, #dda0dd);
    top: 20%;
    right: 5%;
    animation-delay: 3s;
    box-shadow: 
      0 0 60px rgba(139, 90, 159, 0.5),
      0 0 110px rgba(177, 156, 217, 0.4),
      0 0 160px rgba(221, 160, 221, 0.3);
  }

  .orb-main-4 {
    width: 100px;
    height: 100px;
    background: linear-gradient(45deg, #6a5acd, #8b7bc8, #9370db);
    bottom: 35%;
    right: 25%;
    animation-delay: 4s;
    box-shadow: 
      0 0 50px rgba(106, 90, 205, 0.5),
      0 0 90px rgba(139, 123, 200, 0.4),
      0 0 130px rgba(147, 112, 219, 0.3);
  }

  /* Extra large gradient orbs for depth */
  .orb-xlarge {
    opacity: 0.6;
    filter: blur(2px);
  }

  .orb-gradient-1 {
    width: 300px;
    height: 300px;
    background: radial-gradient(circle, rgba(255, 140, 0, 0.3) 0%, rgba(255, 165, 0, 0.2) 50%, transparent 70%);
    bottom: -20%;
    left: -15%;
    animation-delay: 0.5s;
  }

  .orb-gradient-2 {
    width: 250px;
    height: 250px;
    background: radial-gradient(circle, rgba(147, 112, 219, 0.3) 0%, rgba(186, 85, 211, 0.2) 50%, transparent 70%);
    top: -10%;
    right: -12%;
    animation-delay: 1.5s;
  }

  /* Enhanced stars background */
  .stars {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
      radial-gradient(1px 1px at 20px 30px, rgba(255,255,255,0.6), transparent),
      radial-gradient(1px 1px at 40px 70px, rgba(255,255,255,0.4), transparent),
      radial-gradient(1px 1px at 90px 40px, rgba(255,255,255,0.5), transparent),
      radial-gradient(1px 1px at 130px 80px, rgba(255,255,255,0.3), transparent),
      radial-gradient(1px 1px at 160px 30px, rgba(255,255,255,0.4), transparent),
      radial-gradient(1px 1px at 200px 50px, rgba(255,255,255,0.3), transparent),
      radial-gradient(1px 1px at 250px 90px, rgba(255,255,255,0.4), transparent),
      radial-gradient(1px 1px at 300px 20px, rgba(255,255,255,0.2), transparent);
    background-repeat: repeat;
    background-size: 350px 250px;
    animation: sparkle 8s linear infinite;
    opacity: 0.4;
  }

  .stars-2 {
    background-image: 
      radial-gradient(0.8px 0.8px at 60px 90px, rgba(255,255,255,0.5), transparent),
      radial-gradient(0.8px 0.8px at 120px 30px, rgba(255,255,255,0.3), transparent),
      radial-gradient(0.8px 0.8px at 180px 70px, rgba(255,255,255,0.4), transparent),
      radial-gradient(0.8px 0.8px at 240px 110px, rgba(255,255,255,0.2), transparent);
    background-size: 400px 300px;
    animation: sparkle 12s linear infinite reverse;
    opacity: 0.3;
  }

  @keyframes float {
    0%, 100% {
      transform: translateY(0px) translateX(0px) rotate(0deg);
    }
    25% {
      transform: translateY(-15px) translateX(5px) rotate(1deg);
    }
    50% {
      transform: translateY(-25px) translateX(-5px) rotate(0deg);
    }
    75% {
      transform: translateY(-10px) translateX(8px) rotate(-1deg);
    }
  }

  @keyframes sparkle {
    0%, 100% {
      opacity: 0.4;
      transform: translateX(0px);
    }
    50% {
      opacity: 0.8;
      transform: translateX(2px);
    }
  }

  /* Responsive design */
  @media (max-width: 768px) {
    .hero {
      height: auto;
      min-height: 70vh;
      padding-top: 70px;
    }

    .content-wrapper {
      grid-template-columns: 1fr;
      gap: 2rem;
      text-align: center;
    }

    .hero-content h1 {
      font-size: 2.2rem;
    }

    .hero-content p {
      font-size: 1.1rem;
    }

    .container {
      padding: 0 1rem;
    }

    .form-card {
      padding: 1.8rem;
      max-width: 100%;
    }

    .orb-large {
      opacity: 0.6;
    }
    
    .orb-main-1 {
      width: 120px;
      height: 120px;
    }
    
    .orb-main-2 {
      width: 100px;
      height: 100px;
    }
    
    .orb-main-3 {
      width: 80px;
      height: 80px;
    }
    
    .orb-main-4 {
      width: 70px;
      height: 70px;
    }
    
    .orb-medium {
      width: 40px;
      height: 40px;
      opacity: 0.5;
    }
    
    .orb-small {
      width: 20px;
      height: 20px;
      opacity: 0.4;
    }

    .orb-xlarge {
      opacity: 0.3;
    }
    
    .orb-gradient-1 {
      width: 200px;
      height: 200px;
    }
    
    .orb-gradient-2 {
      width: 150px;
      height: 150px;
    }
  }

  @media (max-width: 480px) {
    .hero-content h1 {
      font-size: 2rem;
    }

    .hero-content p {
      font-size: 1rem;
    }

    .form-card {
      padding: 1.5rem;
    }

    .stars {
      background-size: 250px 150px;
      opacity: 0.3;
    }
    
    .stars-2 {
      background-size: 300px 200px;
      opacity: 0.2;
    }
    
    .orb-large {
      opacity: 0.4;
    }
    
    .orb-small {
      opacity: 0.3;
    }
    
    .orb-medium {
      opacity: 0.3;
    }
  }
</style>