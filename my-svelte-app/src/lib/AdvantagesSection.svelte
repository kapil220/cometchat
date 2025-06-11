<script>
  const advantages = [
    {
      icon: "/Icon.png",
      title: "Free credits",
      description: "Empowering partners to scale with complimentary credits to get started and grow your business."
    },
    {
      icon: "/Icon1.png", 
      title: "Revenue share",
      description: "Get monthly recurring revenues when you refer clients and build a sustainable income stream."
    },
    {
      icon: "/Icon2.png", 
      title: "Training and mentoring sessions",
      description: "Enabling partners to deliver the best experience through comprehensive training programs."
    },
    {
      icon: "/Icon3.png", 
      title: "Special developer access",
      description: "Get an all-access account to build unlimited POCs for your clients with premium features."
    },
    {
      icon: "/Icon4.png",
      title: "Reduced time",
      description: "Deliver your products much faster with our partners' programs and streamlined processes."
    },
    {
      icon: "/Icon5.png",
      title: "Value addition to your users",
      description: "Enhance your product offering with our advanced communication features and capabilities."
    },
    {
      icon: "/Icon6.png",
      title: "Knowledge sessions",
      description: "Access to product and market sessions to stay ahead of industry trends and best practices."
    },
    {
      icon: "/Icon7.png",
      title: "On-demand support",
      description: "Technical assistance for implementation with dedicated support team available when you need it."
    },
    {
      icon: "/Icon8.png",
      title: "Significant passive income",
      description: "Earn substantial recurring revenue through our comprehensive partnership programs and referral system."
    }
  ];
</script>

<main class="page-container">
  <div class="content">
    <!-- Title Block with exact spacing from image -->
    <div class="title-block">
      <p class="section-subtitle">Be a partner</p>
      <h1 class="section-title">CometChat partner<br>advantages</h1>
    </div>
    
    <!-- Advantages Grid -->
    <div class="advantages-grid">
      {#each advantages as advantage}
        <div class="advantage-card">
          <img src={advantage.icon} alt={advantage.title} class="card-icon" />
          <h3 class="card-title">{advantage.title}</h3>
          <p class="card-description">{advantage.description}</p>
        </div>
      {/each}
    </div>
  </div>
</main>

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :global(:root) {
    --primary-orange: #FF7F3E;
    --dark-bg: #0A0914;
    --text-white: #ffffff;
    --text-gray: #9ca3af;
    --gradient: linear-gradient(135deg, #FF6B35 0%, #F7931E 100%);
  }

  :global(body) {
    font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: var(--dark-bg);
    color: var(--text-white);
    min-height: 100vh;
    margin: 0;
  }

  .page-container {
    background: var(--dark-bg);
    min-height: 100vh;
    padding: 4rem 2rem 2rem 2rem;
  }

  .content {
    max-width: 1400px;
    margin: 0 auto;
    text-align: start;
  }

  
  .title-block {
    text-align: left;
    margin-bottom: 3rem;
    
    
  }

  .section-subtitle {
    font-size: 1.2rem;
    color: var(--primary-orange);
    text-transform: uppercase;
    letter-spacing: 2px;
    font-weight: 600;
    margin-bottom: 1rem;
    text-align: start;
  }

  .section-title {
  
    color: var(--text-white);
    margin-bottom: 1.5rem;
    line-height: 1.1;
    margin-top: 0;
    text-align: start;
  }

  
  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 4rem;
  }

  .advantage-card {
    padding: 1.5rem 1rem;
    border-image: var(--gradient) 1;
    transition: transform 0.3s ease;
  }

  .card-icon {
    width: 38px;
    height: 38px;
    margin-bottom: 0.5rem;
    object-fit: contain;
  }

  .card-title {
    font-size: 1rem;
    font-weight: 640;
    color: var(--text-white);
    margin-bottom: 1rem;
  }

  .card-description {
    font-size: 1rem;
    font-weight: 500;
    color: var(--text-gray);
    line-height: 1.6;
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    .page-container {
      padding: 2rem 1rem;
    }
    
    .title-block {
      padding-left: 0;
      margin-bottom: 3rem;
    }
    
    .advantages-grid {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
    
    .section-title {
      font-size: 2.5rem;
    }
    
    .section-subtitle {
      font-size: 1rem;
    }
    
    .advantage-card {
      padding: 1.5rem 0;
    }
  }

  @media (max-width: 480px) {
    .section-title {
      font-size: 2rem;
    }
    
    .advantage-card {
      padding: 1.5rem;
    }
  }
</style>