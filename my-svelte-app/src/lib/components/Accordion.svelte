<!-- Accordion.svelte -->
<script>
  import { createEventDispatcher } from 'svelte';
  
  export let question = '';
  export let answer = '';
  export let isOpen = false;
  
  const dispatch = createEventDispatcher();
  
  function handleToggle() {
    dispatch('toggle');
  }
</script>

<div class="faq-item">
  <button 
    class="faq-question"
    class:active={isOpen}
    on:click={handleToggle}
  >
    {question}
    <div class="faq-icon" class:active={isOpen}>
      <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M4 6L8 10L12 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>
  </button>
  
  <div class="faq-answer" class:active={isOpen}>
    <p>{answer}</p>
  </div>
</div>

<style>
  .faq-item {
    background: rgba(20, 19, 29, 0.04);
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s ease;
  }
  
  .faq-question {
    padding: 24px 28px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(20, 19, 29, 0.02);
    border: none;
    width: 100%;
    text-align: left;
    font-size: 22px;
    line-height: 106%;
    font-weight: 640;
    color: rgba(20, 19, 29, 1);
    transition: all 0.3s ease;
    border: 1px;
    border: rgba(20, 19, 29, 0.04);
  }
  
  .faq-question.active {
    background: rgba(20, 19, 29, 0.02);
    border: 1px;
    border: rgba(20, 19, 29, 0.04);
  }
  
  .faq-icon {
    width: 24px;
    height: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.3s ease;
    color: #6c757d;
  }
  
  .faq-icon.active {
    transform: rotate(180deg);
  }
  
  .faq-answer {
    max-height: 0;
    overflow: hidden;
     
    transition: max-height 0.3s ease, padding 0.3s ease;
    
  }
  
  .faq-answer.active {
    max-height: 200px;
    font-size: 22px;
    font-weight: 500;
    color: rgba(20, 19, 29, 1);
    padding: 0 28px 24px 28px;
    
    background: rgba(20, 19, 29, 0.04);
  }
  
  .faq-answer p {
    color: #6c757d;
    font-size: 16px;
    line-height: 1.6;
  }
  
  @media (max-width: 768px) {
    .faq-question {
      padding: 20px 24px;
      font-size: 16px;
    }
    
    .faq-answer.active {
      padding: 0 24px 20px 24px;
    }
  }
</style>