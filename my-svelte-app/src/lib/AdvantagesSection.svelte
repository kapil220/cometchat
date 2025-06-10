<script>
  const advantages = [
    {
      icon: "💳",
      title: "Free credits",
      description: "Empowering partners to scale with complimentary credits to get started and grow your business."
    },
    {
      icon: "💰",
      title: "Revenue share",
      description: "Get monthly recurring revenues when you refer clients and build a sustainable income stream."
    },
    {
      icon: "🎓",
      title: "Training and mentoring sessions",
      description: "Enabling partners to deliver the best experience through comprehensive training programs."
    },
    {
      icon: "🔧",
      title: "Special developer access",
      description: "Get an all-access account to build unlimited POCs for your clients with premium features."
    },
    {
      icon: "⚡",
      title: "Reduced time",
      description: "Deliver your products much faster with our partners' programs and streamlined processes."
    },
    {
      icon: "📊",
      title: "Value addition to your users",
      description: "Enhance your product offering with our advanced communication features and capabilities."
    },
    {
      icon: "📚",
      title: "Knowledge sessions",
      description: "Access to product and market sessions to stay ahead of industry trends and best practices."
    },
    {
      icon: "🆘",
      title: "On-demand support",
      description: "Technical assistance for implementation with dedicated support team available when you need it."
    },
    {
      icon: "💎",
      title: "Significant passive income",
      description: "Earn substantial recurring revenue through our comprehensive partnership programs and referral system."
    }
  ];
</script>

<main class="page-container">
  <div class="decorative-elements"></div>
  
  <div class="content">
    <!-- Title Block -->
    <div class="title-block">
      <p class="section-subtitle">Be a partner</p>
      <h1 class="section-title">CometChat partner advantages</h1>
      <p class="description">Join our partnership program and unlock exclusive benefits designed to accelerate your success</p>
    </div>
    
    <!-- Advantages Grid -->
    <div class="advantages-grid">
      {#each advantages as advantage}
        <div class="advantage-card">
          <div class="card-icon">{advantage.icon}</div>
          <h3 class="card-title">{advantage.title}</h3>
          <p class="card-description">{advantage.description}</p>
        </div>
      {/each}
    </div>
    
    <!-- CTA Section -->
    <div class="cta-section">
      <button class="cta-button">Become a Partner Today</button>
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
    --primary-orange: #FF6B35;
    --dark-bg: rgba(10, 9, 20, 1);
    --card-bg: rgba(20, 19, 30, 0.8);
    --text-white: #ffffff;
    --text-gray: #9ca3af;
    --gradient: linear-gradient(135deg, #FF6B35 0%, #F7931E 100%);
    --shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    --border-radius: 16px;
  }

  :global(body) {
    font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: var(--dark-bg);
    color: var(--text-white);
    min-height: 100vh;
    overflow-x: hidden;
  }

  .page-container {
    position: relative;
    min-height: 100vh;
    background: var(--dark-bg);
  }

  .decorative-elements {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    pointer-events: none;
  }

  .decorative-elements::before {
    content: '';
    position: absolute;
    top: -50%;
    right: -20%;
    width: 500px;
    height: 500px;
    background: radial-gradient(circle, rgba(255, 107, 53, 0.08) 0%, transparent 70%);
    border-radius: 50%;
    animation: float 6s ease-in-out infinite;
  }

  .decorative-elements::after {
    content: '';
    position: absolute;
    bottom: -30%;
    left: -20%;
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, rgba(247, 147, 30, 0.06) 0%, transparent 70%);
    border-radius: 50%;
    animation: float 8s ease-in-out infinite reverse;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px) rotate(0deg); }
    50% { transform: translateY(-30px) rotate(5deg); }
  }

  .content {
    position: relative;
    z-index: 1;
    padding: 4rem 2rem;
    max-width: 1400px;
    margin: 0 auto;
  }

  /* Title Block Styles */
  .title-block {
    text-align: center;
    margin-bottom: 4rem;
  }

  .section-subtitle {
    font-size: 1.2rem;
    color: var(--primary-orange);
    text-transform: uppercase;
    letter-spacing: 2px;
    font-weight: 600;
    margin-bottom: 1rem;
  }

  .section-title {
    font-size: clamp(2.5rem, 5vw, 4rem);
    font-weight: 800;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 1.5rem;
    line-height: 1.1;
  }

  .description {
    font-size: 1.3rem;
    color: var(--text-gray);
    max-width: 600px;
    margin: 0 auto;
    line-height: 1.6;
  }

  /* Advantages Grid Styles */
  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
  }

  .advantage-card {
    background: var(--card-bg);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 107, 53, 0.2);
    padding: 2.5rem;
    border-radius: var(--border-radius);
    position: relative;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: hidden;
  }

  .advantage-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: var(--gradient);
    transform: scaleX(0);
    transition: transform 0.4s ease;
  }

  .advantage-card:hover {
    transform: translateY(-8px) scale(1.02);
    box-shadow: var(--shadow);
    border-color: var(--primary-orange);
  }

  .advantage-card:hover::before {
    transform: scaleX(1);
  }

  .card-icon {
    width: 50px;
    height: 50px;
    background: var(--gradient);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1.5rem;
    font-size: 1.5rem;
    transition: transform 0.3s ease;
  }

  .advantage-card:hover .card-icon {
    transform: rotate(10deg) scale(1.1);
  }

  .card-title {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--text-white);
    margin-bottom: 1rem;
    line-height: 1.3;
  }

  .card-description {
    font-size: 1rem;
    color: var(--text-gray);
    line-height: 1.6;
  }

  /* CTA Section Styles */
  .cta-section {
    text-align: center;
    margin-top: 4rem;
  }

  .cta-button {
    display: inline-block;
    background: var(--gradient);
    color: white;
    padding: 1rem 2.5rem;
    border: none;
    border-radius: 50px;
    font-weight: 600;
    font-size: 1.1rem;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 20px rgba(255, 107, 53, 0.3);
  }

  .cta-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(255, 107, 53, 0.4);
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    .content {
      padding: 2rem 1rem;
    }
    
    .advantages-grid {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }
    
    .advantage-card {
      padding: 2rem;
    }
    
    .section-title {
      font-size: 2rem;
    }
    
    .section-subtitle {
      font-size: 1rem;
    }
    
    .description {
      font-size: 1.1rem;
    }
  }
</style>