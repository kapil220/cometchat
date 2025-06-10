<script>
  import { createEventDispatcher } from 'svelte';
  
  const dispatch = createEventDispatcher();
  
  function handleContactSales() {
    dispatch('contact-sales');
  }
  
  function handleSignUp() {
    dispatch('sign-up');
  }
</script>

<header class="header">
  <div class="header-container">
    <div class="logo">
      <h1>CometChat</h1>
    </div>
    
    <nav class="nav">
      <a href="/products" class="nav-link">Products</a>
      <a href="/solutions" class="nav-link">Solutions</a>
      <a href="/pricing" class="nav-link">Pricing</a>
      <a href="/partners" class="nav-link active">Partners</a>
      <a href="/resources" class="nav-link">Resources</a>
    </nav>
    
    <div class="header-actions">
      <button class="btn btn-outline" on:click={handleContactSales}>
        Contact sales
      </button>
      <button class="btn btn-primary" on:click={handleSignUp}>
        Sign up free
      </button>
    </div>
    
    <!-- Mobile menu button -->
    <button class="mobile-menu-btn">
      <span></span>
      <span></span>
      <span></span>
    </button>
  </div>
</header>

<style>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: rgba(10, 10, 26, 0.95);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 1000;
    padding: 1rem 0;
  }

  .header-container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo h1 {
    color: white;
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0;
  }

  .nav {
    display: flex;
    gap: 2rem;
    margin: 0 2rem;
  }

  .nav-link {
    text-decoration: none;
    color: rgba(255, 255, 255, 0.8);
    font-weight: 500;
    padding: 0.5rem 0;
    position: relative;
    transition: color 0.3s ease;
  }

  .nav-link:hover {
    color: white;
  }

  .nav-link.active {
    color: white;
  }

  .nav-link.active::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    border-radius: 1px;
  }

  .header-actions {
    display: flex;
    gap: 1rem;
    align-items: center;
  }

  .btn {
    padding: 0.75rem 1.5rem;
    border-radius: 8px;
    font-weight: 500;
    font-size: 0.9rem;
    cursor: pointer;
    transition: all 0.3s ease;
    border: none;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  .btn-outline {
    background: transparent;
    color: white;
    border: 1px solid rgba(255, 255, 255, 0.3);
  }

  .btn-outline:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: rgba(255, 255, 255, 0.5);
  }

  .btn-primary {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: 1px solid transparent;
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
  }

  .mobile-menu-btn {
    display: none;
    flex-direction: column;
    gap: 4px;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
  }

  .mobile-menu-btn span {
    width: 24px;
    height: 2px;
    background: white;
    border-radius: 1px;
    transition: all 0.3s ease;
  }

  @media (max-width: 768px) {
    .nav {
      display: none;
    }

    .header-actions {
      display: none;
    }

    .mobile-menu-btn {
      display: flex;
    }

    .header-container {
      padding: 0 1rem;
    }
  }
</style>