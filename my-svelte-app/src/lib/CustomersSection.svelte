<section class="customers">
  <div class="container">
    <div class="customers-content">
      
      <div class="logos-grid">
        <div class="logo-item">
          <img src="/logos/aws.svg" alt="AWS" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/10x-genomics.svg" alt="10x Genomics" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/microsoft.svg" alt="Microsoft" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/nasscom.svg" alt="NASSCOM" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/techstars.svg" alt="Techstars" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/tekno-point.svg" alt="Tekno Point" class="logo" />
        </div>
        <div class="logo-item">
          <img src="/logos/cisco.svg" alt="Cisco" class="logo" />
        </div>
        <div class="logo-item">
          <div class="logo-placeholder">+50</div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
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
    margin: 0 auto;
    padding: 0 2rem;
  }

  .customers-content {
    text-align: center;
  }



  .logos-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(16px, 1fr));
    gap: 3rem 2rem;
    align-items: center;
    justify-items: center;
    max-width: 1200px;
    margin: 0 auto;
  }

  .logo-item {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 60px;
    opacity: 0.6;
    transition: all 0.3s ease;
    filter: grayscale(100%) brightness(0) invert(1);
  }

  .logo-item:hover {
    opacity: 0.9;
    transform: translateY(-2px);
  }

  .logo {
    max-height: 40px;
    max-width: 140px;
    width: auto;
    height: auto;
    object-fit: contain;
  }

  .logo-placeholder {
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 12px;
    padding: 1rem 1.5rem;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.8);
    font-size: 1rem;
    text-align: center;
    min-width: 80px;
    backdrop-filter: blur(10px);
    transition: all 0.3s ease;
  }

  .logo-placeholder:hover {
    background: rgba(255, 255, 255, 0.15);
    border-color: rgba(255, 255, 255, 0.3);
    transform: translateY(-2px);
  }

  /* Responsive design */
  @media (max-width: 768px) {
    .customers {
      padding: 3rem 0;
      min-height: 20vh;
    }

    .customers-content h2 {
      font-size: 2rem;
    }

    .customers-content p {
      font-size: 1.1rem;
      margin-bottom: 2.5rem;
    }

    .logos-grid {
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 2rem 1.5rem;
    }

    .logo-item {
      height: 50px;
    }

    .logo {
      max-height: 32px;
      max-width: 110px;
    }

    .container {
      padding: 0 1rem;
    }
  }

  @media (max-width: 480px) {
    .customers-content h2 {
      font-size: 1.7rem;
    }

    .logos-grid {
      grid-template-columns: repeat(2, 1fr);
      gap: 1.5rem 1rem;
    }

    .logo {
      max-height: 28px;
      max-width: 100px;
    }

    .logo-placeholder {
      padding: 0.8rem 1rem;
      font-size: 0.9rem;
    }
  }
</style>