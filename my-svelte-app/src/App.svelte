<script>
  import Header from './lib/Header.svelte';
  import HeroSection from './lib/HeroSection.svelte';
  import AdvantagesSection from './lib/AdvantagesSection.svelte';
  import ProgramsSection from './lib/ProgramsSection.svelte';
  import CustomersSection from './lib/CustomersSection.svelte';
  import FAQSection from './lib/FAQSection.svelte';
  import CtaSection from './lib/CtaSection.svelte';
  import FooterSection from './lib/FooterSection.svelte';

  function handleContactSales() {
    console.log('Contact sales clicked');
  }

  function handleSignUp() {
    console.log('Sign up clicked');
  }

  function handleFormSubmit(event) {
    console.log('Form submitted:', event.detail);
  }
</script>

<main class="main-content">
  <!-- Fixed Header -->
  <Header 
    on:contact-sales={handleContactSales}
    on:sign-up={handleSignUp}
  />
  
  <!-- First Page Content -->
  <div class="first-page">
    <!-- Hero Section with Background Animation -->
    <HeroSection on:form-submit={handleFormSubmit} />
    
    <!-- Customers Section at bottom of first page -->
    <CustomersSection />
  </div>
  
  <!-- Additional Sections -->
  <div class="additional-sections">
    <AdvantagesSection />
    <ProgramsSection />
    <FAQSection />
    <CtaSection />
    <FooterSection />
  </div>
</main>

<style>
  .main-content {
    position: relative;
  }

  /* First page container - takes full viewport height */
  .first-page {
    height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
    /* Ensure first page content is above background */
    z-index: 1;
    /* Account for fixed header */
    padding-top: 80px;
    box-sizing: border-box;
  }

  /* Additional sections container */
  .additional-sections {
    position: relative;
    z-index: 2;
    /* Clean background for remaining sections */
    background: linear-gradient(180deg, #f8fafc 0%, #ffffff 100%);
    /* Ensure sections start right after first page */
    margin-top: 0;
  }
    
  /* Ensure body has clean background and smooth scrolling */
  :global(html) {
    scroll-behavior: smooth;
  }
  
  :global(body) {
    margin: 0;
    padding: 0;
    background: #0a0a1a;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    overflow-x: hidden;
  }

  /* Responsive adjustments */
  @media (max-width: 768px) {
    .first-page {
      padding-top: 70px;
    }
  }
</style>