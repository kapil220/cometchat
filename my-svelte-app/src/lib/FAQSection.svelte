<!-- App.svelte -->
<script>
  import Accordion from './components/Accordion.svelte';

  const faqs = [
    {
      question: "This is a frequently asked question?",
      answer: "Lorem ipsum dolor sit amet consectetur. Tellus eget consequat tortor odio maecenas cursus leo dui. Pulvinar quam sit quam feugiat laoreet morbi tellus dui massa."
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
    <div class="section-label">FAQ's</div>
    <h1 class="section-title">We want to help you<br>with all your doubts</h1>
    
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
    background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
    color: #333;
    line-height: 1.6;
    min-height: 100vh;
  }

  .faq-section {
    padding: 80px 20px;
    
  }

  .container {
    max-width: 800px;
    margin: 0 auto;
  }

  .section-label {
    color: #ff6b35;
    font-size: 22px;
    font-weight: 640;
    text-align: center;
    margin-bottom: 16px;
    letter-spacing: 0.5px;
  }

  .section-title {
    font-size: 48px;
    font-weight: 640;
    text-align: center;
    margin-bottom: 60px;
    color: #2c3e50;
    line-height: 1.2;
  }

  .faq-container {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  @media (max-width: 768px) {
    .faq-section {
      padding: 60px 15px;
    }

    .section-title {
      font-size: 36px;
    }
  }
</style>