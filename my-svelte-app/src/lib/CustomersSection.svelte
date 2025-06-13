<section class="customers">
  <div class="container">
    <div class="customers-content">
      <!-- Desktop Grid (original unchanged) -->
      <div class="desktop-logos">
        <div class="logos-grid">
          <div class="logo-item">
            <img src="/aws.png" alt="AWS" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/10x.png" alt="10x Genomics" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/microsoft.png" alt="Microsoft" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/path2.png" alt="NASSCOM" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/Logo.png" alt="Techstars" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/Teknopoint.png" alt="Tekno Point" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/cisco.png" alt="Cisco" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/tsc.png" alt="TSC" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/hak.png" alt="HAK" class="logo" />
          </div>
        </div>
      </div>

      <!-- Mobile Carousel (fixed) -->
      <div class="mobile-logos">
        <div class="logos-track">
          <!-- Original Logos -->
          <div class="logo-item">
            <img src="/aws.png" alt="AWS" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/10x.png" alt="10x Genomics" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/microsoft.png" alt="Microsoft" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/path2.png" alt="NASSCOM" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/Logo.png" alt="Techstars" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/Teknopoint.png" alt="Tekno Point" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/cisco.png" alt="Cisco" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/tsc.png" alt="TSC" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/hak.png" alt="HAK" class="logo" />
          </div>
          <!-- Duplicates for seamless looping -->
          <div class="logo-item">
            <img src="/aws.png" alt="AWS" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/10x.png" alt="10x Genomics" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/microsoft.png" alt="Microsoft" class="logo" />
          </div>
          <div class="logo-item">
            <img src="/path2.png" alt="NASSCOM" class="logo" />
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  /* Original Desktop Styles (UNCHANGED) */
  .customers {
    min-height: 18vh;
    background: rgba(10, 9, 20, 1);
    padding: 1rem 0;
    display: flex;
    align-items: center;
    position: relative;
    z-index: 2;
  }

  .container {
    width: 100%;
    max-width: 100%;
    margin: 0 auto;
    padding: 0 2rem;
  }

  .customers-content {
    text-align: center;
    width: 100%;
  }

  .desktop-logos {
    display: block;
  }

  .logos-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 72px;
    width: 100%;
    margin: 0 auto;
  }

  .logo-item {
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0.6;
    transition: all 0.3s ease;
    filter: grayscale(100%) brightness(0) invert(1);
    flex-shrink: 0; /* Prevent shrinking */
  }

  .logo-item:hover {
    opacity: 0.9;
    transform: translateY(-2px);
  }

  .logo {
    height: auto;
    max-height: 32px;
    width: auto;
    max-width: 140px;
    object-fit: contain;
  }

  /* Mobile Carousel (INFINITE LOOP - 3 VISIBLE) */
  .mobile-logos {
    display: none;
    width: 100%;
    margin: 0 auto;
    overflow: hidden;
  }

  .logos-track {
    display: flex;
    gap: 40px;
    animation: infiniteScroll 15s linear infinite;
    will-change: transform;
    padding: 10px 0;
  }

  /* Mobile Styles */
  @media (max-width: 768px) {
    .desktop-logos {
      display: none;
    }
    
    .mobile-logos {
      display: block;
    }
    
    .customers {
      padding: 2rem 0;
      min-height: 16vh;
    }
    
    .container {
      padding: 0 1rem;
    }
    
    .logo {
      max-height: 24px;
      max-width: 100px;
    }
  }

  @media (max-width: 480px) {
    .logos-track {
      gap: 30px;
    }
    
    .logo {
      max-height: 20px;
      max-width: 80px;
    }
  }

  @keyframes infiniteScroll {
    0% { 
      transform: translateX(0); 
    }
    100% { 
      transform: translateX(calc(-100% / 2));
    }
  }
</style>