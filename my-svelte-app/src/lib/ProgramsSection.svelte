<script>
  const programs = [
    {
      title: "Affiliate partner program",
      description: "Bring value to your customers with a world-class in-app messaging tool that increases user-to-user engagement and retention. Get incentivized for referring CometChat to any of your customers.",
      icon: "/11.png",
    },
    {
      title: "Technology partner program", 
      description: "Development teams can use our plug and play solution to build top class chat solutions for their clients using our SDKs and APIs. It's simple, safe and secure!",
      icon: "/12.png",
    },
    {
      title: "Start up growth program",
      description: "We help incubators, accelerators, co-working space that foster an ecosystem of start-ups. This program also enables VCs to accelerate the growth of their portfolio companies.",
      icon: "/13.png",
    }
  ];
</script>

<section class="programs-section">
  <div class="container">
    <div class="header">
      <p class="subtitle">Our programs</p>
      <h2 class="title">Types of partnerships programs</h2>
    </div>
    
    <div class="programs-grid">
      {#each programs as program}
        <div class="program-card">
          <div class="icon-wrapper">
            <img src={program.icon} alt={program.title} class="program-icon" />
          </div>
          <h3 class="program-title">{program.title}</h3>
          <p class="program-description">{program.description}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .programs-section {
    padding: 120px 40px;
    width: 100%;
    background: rgba(250, 250, 255, 1);
  }

  .container {
    max-width: 1400px;
    margin: 0 auto;
  }

  .header {
    margin-bottom: 64px;
    text-align: left;
  }

  .subtitle {
    color: #6366f1;
    font-size: 22px;
    font-weight: 640;
    margin-bottom: 12px;
    letter-spacing: 0.025em;
  }

  .title {
    color: #1f2937;
    font-size: 48px;
    font-weight: 640;
    line-height: 1.1;
    max-width: 600px;
    margin-bottom: 24px;
  }

  .programs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 32px;
  }

  .program-card {
    padding: x 32px;
    border-radius: 0;
    transition: transform 0.3s ease;
    background: transparent;
    border: none;
    box-shadow: none;
  }

  .program-card:hover {
    transform: translateY(-4px);
  }

  .icon-wrapper {
    width: 48px;
    height: 48px;
    margin-bottom: 2px;
  }

  .program-icon {
    width: 38px;
    height: 38px;
    
  }

  .program-title {
    font-size: 18px;
    font-weight: 640;
    margin-bottom: 16px;
    line-height: 1.3;
    color:rgba(20, 19, 29, 1);
  }

  .program-description {
     font-size: 18px;
    font-weight: 500;
    line-height: 1.6;
    color: rgba(20, 19, 29, 1);
  }

  @media (max-width: 768px) {
    .programs-section {
      padding: 60px 20px;
    }

    .title {
      font-size: 36px;
    }

    .programs-grid {
      grid-template-columns: 1fr;
      gap: 24px;
    }

    .program-card {
      padding: 32px 24px;
    }
  }

  @media (max-width: 480px) {
    .title {
      font-size: 28px;
    }
  }
</style>