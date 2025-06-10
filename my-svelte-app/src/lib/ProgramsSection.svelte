<script>
  import TitleBlock from './TitleBlock.svelte';
  
  const programs = [
    {
      title: "Affiliate partner program",
      description: "Bring value to your customers with a world-class in-app messaging tool that increases user-to-user engagement and retention. Get incentivized for referring CometChat to any of your customers.",
      icon: "affiliate"
    },
    {
      title: "Technology partner program", 
      description: "Development teams can use our plug and play solution to build top class chat solutions for their clients using our SDKs and APIs. It's simple, safe and secure!",
      icon: "technology"
    },
    {
      title: "Start up growth program",
      description: "We help incubators, accelerators, co-working space that foster an ecosystem of start-ups. This program also enables VCs to accelerate the growth of their portfolio companies.",
      icon: "startup"
    }
  ];
</script>

<section class="programs-section">
  <TitleBlock
    title="Types of partnerships programs"
    subtitle="Our programs"
  />
  
  <div class="container">
    <div class="programs-grid">
      {#each programs as program}
        <div class="program-card">
          <div class="program-icon {program.icon}">
            {#if program.icon === 'affiliate'}
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
              </svg>
            {:else if program.icon === 'technology'}
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M9.4 16.6L4.8 12l4.6-4.6L8 6l-6 6 6 6 1.4-1.4zm5.2 0L19.2 12l-4.6-4.6L16 6l6 6-6 6-1.4-1.4z"/>
              </svg>
            {:else if program.icon === 'startup'}
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M5 16c0 3.87 3.13 7 7 7s7-3.13 7-7v-4H5v4zM16.12 4.37l2.1-2.1-.82-.83-2.3 2.31C14.16 3.28 13.12 3 12 3s-2.16.28-3.09.75L6.6 1.44l-.82.83 2.1 2.1C6.14 5.64 5 7.68 5 10v1h14v-1c0-2.32-1.14-4.36-2.88-5.63z"/>
              </svg>
            {/if}
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
    background-color: #f8f9fa;
    padding: 80px 0;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }

  .programs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 32px;
    margin-top: 40px;
  }

  .program-card {
    background: white;
    padding: 40px 32px;
    border-radius: 16px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
    border: 1px solid #e5e7eb;
  }

  .program-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
  }

  .program-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 24px;
    color: white;
  }

  .program-icon.affiliate {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  }

  .program-icon.technology {
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  }

  .program-icon.startup {
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
  }

  .program-title {
    font-size: 20px;
    font-weight: 600;
    color: #1f2937;
    margin-bottom: 16px;
    line-height: 1.3;
  }

  .program-description {
    font-size: 16px;
    color: #6b7280;
    line-height: 1.6;
  }

  @media (max-width: 768px) {
    .programs-grid {
      grid-template-columns: 1fr;
      gap: 24px;
    }
    
    .program-card {
      padding: 32px 24px;
    }
  }
</style>