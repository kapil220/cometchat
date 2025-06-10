<script>
  export let title;
  export let subtitle;
</script>

<div class="title-block">
  <h2 class="section-title">{title}</h2>
  <p class="section-subtitle">{subtitle}</p>
</div>

<style>
  .title-block {
    text-align: center;
    margin-bottom: 3rem;
    padding: 0 1.5rem;
  }

  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--gray-dark);
    margin-bottom: 1rem;
    line-height: 1.2;
  }

  .section-subtitle {
    font-size: 1.125rem;
    color: var(--text-light, #6b7280);
    max-width: 600px;
    margin: 0 auto;
    line-height: 1.6;
  }

  @media (max-width: 768px) {
    .section-title {
      font-size: 2rem;
    }

    .section-subtitle {
      font-size: 1rem;
    }
  }
</style>
