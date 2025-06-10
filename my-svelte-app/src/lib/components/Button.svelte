<script>
  export let variant = 'primary';
  export let type = 'button';
</script>

<button class="{variant}" type="{type}">
  <slot></slot>
</button>

<style>
  button {
    padding: 0.75rem 1.5rem;
    border-radius: var(--border-radius);
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    font-size: 1rem;
  }
  
  .primary {
    background: var(--primary);
    color: white;
    border: 1px solid var(--primary);
  }
  
  .primary:hover {
    background: var(--primary-dark);
    border-color: var(--primary-dark);
  }
  
  .outline {
    background: transparent;
    color: var(--primary);
    border: 1px solid var(--primary);
  }
  
  .outline:hover {
    background: rgba(61, 90, 254, 0.1);
  }
</style>