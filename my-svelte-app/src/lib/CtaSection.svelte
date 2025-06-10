<script>
  import Button from './components/Button.svelte';
</script>

<section class="cta-section">
  <div class="background-orbs">
    <div class="orb orb-left"></div>
    <div class="orb orb-right"></div>
    <div class="stars"></div>
  </div>
  
  <div class="container">
    <h2>Get started for free</h2>
    <p>Build and test for as long as you need.<br>Pick a plan when you're ready.</p>
    
    <div class="cta-buttons">
      <Button>Start free trial</Button>
      <Button variant="secondary">Schedule a demo</Button>
    </div>
  </div>
</section>

<style>
  .cta-section {
    position: relative;
    background: linear-gradient(135deg, 
      #1a1a2e 0%, 
      #16213e 25%, 
      #0f3460 50%, 
      #533483 75%, 
      #7209b7 100%
    );
    color: white;
    text-align: center;
    padding: 8rem 2rem;
    min-height: 70vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  
  .background-orbs {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
  }
  
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.7;
  }
  
  .orb-left {
    width: 400px;
    height: 400px;
    background: linear-gradient(45deg, #ff6b6b, #ff8e53);
    top: -100px;
    left: -200px;
  }
  
  .orb-right {
    width: 350px;
    height: 350px;
    background: linear-gradient(45deg, #4ecdc4, #44a08d);
    bottom: -100px;
    right: -150px;
  }
  
  .stars {
    position: absolute;
    width: 100%;
    height: 100%;
    background-image: 
      radial-gradient(2px 2px at 20px 30px, white, transparent),
      radial-gradient(2px 2px at 40px 70px, white, transparent),
      radial-gradient(1px 1px at 90px 40px, white, transparent),
      radial-gradient(1px 1px at 130px 80px, white, transparent),
      radial-gradient(2px 2px at 160px 30px, white, transparent),
      radial-gradient(1px 1px at 200px 90px, white, transparent),
      radial-gradient(2px 2px at 240px 50px, white, transparent),
      radial-gradient(1px 1px at 280px 10px, white, transparent),
      radial-gradient(1px 1px at 320px 70px, white, transparent),
      radial-gradient(2px 2px at 360px 40px, white, transparent);
    background-repeat: repeat;
    background-size: 400px 200px;
    opacity: 0.3;
    animation: twinkle 4s ease-in-out infinite alternate;
  }
  
  @keyframes twinkle {
    0% { opacity: 0.3; }
    100% { opacity: 0.6; }
  }
  
  .container {
    position: relative;
    z-index: 2;
    max-width: 800px;
    margin: 0 auto;
  }
  
  .cta-section h2 {
    font-size: 3.5rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    letter-spacing: -0.02em;
    line-height: 1.1;
  }
  
  .cta-section p {
    color: rgba(255, 255, 255, 0.85);
    font-size: 1.25rem;
    line-height: 1.6;
    margin: 0 auto 3rem;
    max-width: 500px;
  }
  
  .cta-buttons {
    display: flex;
    gap: 1.5rem;
    justify-content: center;
    align-items: center;
  }
  
  :global(.cta-buttons button) {
    padding: 1rem 2rem;
    font-size: 1.1rem;
    font-weight: 600;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    transition: all 0.3s ease;
    min-width: 160px;
  }
  
  :global(.cta-buttons button:first-child) {
    background-color: #1a1a1a;
    color: white;
  }
  
  :global(.cta-buttons button:first-child:hover) {
    background-color: #2a2a2a;
    transform: translateY(-2px);
  }
  
  :global(.cta-buttons button:last-child) {
    background-color: rgba(255, 255, 255, 0.1);
    color: white;
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
  }
  
  :global(.cta-buttons button:last-child:hover) {
    background-color: rgba(255, 255, 255, 0.2);
    transform: translateY(-2px);
  }
  
  @media (max-width: 768px) {
    .cta-section {
      padding: 6rem 1rem;
      min-height: 60vh;
    }
    
    .cta-section h2 {
      font-size: 2.5rem;
    }
    
    .cta-section p {
      font-size: 1.1rem;
    }
    
    .cta-buttons {
      flex-direction: column;
      gap: 1rem;
    }
    
    :global(.cta-buttons button) {
      width: 100%;
      max-width: 280px;
    }
    
    .orb-left {
      width: 300px;
      height: 300px;
      left: -150px;
    }
    
    .orb-right {
      width: 250px;
      height: 250px;
      right: -100px;
    }
  }
  
  @media (max-width: 480px) {
    .cta-section h2 {
      font-size: 2rem;
    }
    
    .cta-section p {
      font-size: 1rem;
    }
  }
</style>