<script>
  export let label;
  export let placeholder;
  export let type = 'text';
  export let value;
</script>

<div class="input-field">
  <label>{label}</label>
  <input {type} {placeholder} bind:value />
</div>

<style>
  .input-field {
    margin-bottom: 1.5rem;
  }
  
  label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: var(--gray-dark);
  }
  
  input {
    width: 100%;
    padding: 0.75rem 1rem;
    border: 1px solid #ddd;
    border-radius: var(--border-radius);
    font-size: 1rem;
    transition: border-color 0.2s ease;
  }
  
  input:focus {
    outline: none;
    border-color: var(--primary);
  }
  
  input::placeholder {
    color: #999;
  }
</style>