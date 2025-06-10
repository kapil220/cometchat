<script>
  import { createEventDispatcher } from 'svelte';
  
  export let question;
  export let answer;
  export let isOpen = false;
  
  const dispatch = createEventDispatcher();
  
  function toggle() {
    dispatch('toggle');
  }
</script>

<div class="accordion-item" class:active={isOpen}>
  <button class="accordion-header" on:click={toggle}>
    <h3 class="accordion-question">{question}</h3>
    <div class="accordion-icon">
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 9L12 15L18 9" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>
  </button>
  
  {#if isOpen}
    <div class="accordion-content">
      <div class="accordion-answer">
        <p>{answer}</p>
      </div>
    </div>
  {/if}
</div>

<style>
  .accordion-item {
    background: white;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .accordion-item:hover {
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12);
  }

  .accordion-header {
    padding: 24px 28px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: white;
    border: none;
    width: 100%;
    text-align: left;
    transition: background-color 0.3s ease;
  }

  .accordion-header:hover {
    background-color: #f8f9fa;
  }

  .accordion-question {
    font-size: 18px;
    font-weight: 500;
    color: #2c3e50;
    margin: 0;
    flex: 1;
    padding-right: 20px;
    line-height: 1.4;
  }

  .accordion-icon {
    width: 24px;
    height: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.3s ease;
    color: #6c757d;
    flex-shrink: 0;
  }

  .accordion-item.active .accordion-icon {
    transform: rotate(180deg);
  }

  .accordion-content {
    background: white;
    border-top: 1px solid #f0f0f0;
  }

  .accordion-answer {
    padding: 24px 28px;
  }

  .accordion-answer p {
    color: #6c757d;
    font-size: 16px;
    line-height: 1.6;
    margin: 0;
  }

  @media (max-width: 768px) {
    .accordion-header {
      padding: 20px;
    }
    
    .accordion-question {
      font-size: 16px;
      padding-right: 15px;
    }
    
    .accordion-answer {
      padding: 20px;
    }
    
    .accordion-answer p {
      font-size: 14px;
    }
  }
</style>