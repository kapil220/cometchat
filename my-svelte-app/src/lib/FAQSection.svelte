<script>
  import Accordion from './components/Accordion.svelte';
  
  const faqs = [
    {
      question: "This is a frequently asked question?",
      answer: "Lorem ipsum dolor sit amet consectetur. Tellus eget consequat tortor odio maceenas cursus leo dui. Pulvinar quam sit quam feugiat laoreet morbi tellus dui massa."
    },
    {
      question: "This is a frequently asked question?",
      answer: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum."
    },
    {
      question: "This is a very long frequently asked question about our services with more than one line?",
      answer: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum."
    },
    {
      question: "This is a frequently asked question?",
      answer: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum."
    },
    {
      question: "This is a question?",
      answer: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum."
    },
    {
      question: "This is a question?",
      answer: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum."
    }
  ];

  let openAccordionIndex = 0; // First accordion is open by default

  function handleAccordionToggle(index) {
    openAccordionIndex = openAccordionIndex === index ? -1 : index;
  }
</script>

<section class="faq-section">
  <div class="container">
    <h2 class="section-title">FAQ's</h2>
    <h1 class="section-subtitle">We want to help you<br>with all your doubts</h1>
    
    <div class="faq-container">
      {#each faqs as faq, index}
        <Accordion 
          question={faq.question} 
          answer={faq.answer} 
          isOpen={openAccordionIndex === index}
          on:toggle={() => handleAccordionToggle(index)}
        />
      {/each}
    </div>
  </div>
</section>

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :global(body) {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    background-color: #f8f9fa;
    color: #333;
    line-height: 1.6;
  }

  .faq-section {
    min-height: 100vh;
    padding: 60px 20px;
    background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  }

  .container {
    max-width: 800px;
    margin: 0 auto;
  }

  .section-title {
    color: #ff6b35;
    font-size: 18px;
    font-weight: 600;
    text-align: center;
    margin-bottom: 16px;
    letter-spacing: 0.5px;
  }

  .section-subtitle {
    font-size: 42px;
    font-weight: 700;
    text-align: center;
    margin-bottom: 60px;
    color: #2c3e50;
    line-height: 1.2;
  }

  .faq-container {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  @media (max-width: 768px) {
    .section-subtitle {
      font-size: 32px;
    }
    
    .faq-section {
      padding: 40px 15px;
    }
  }
</style>
