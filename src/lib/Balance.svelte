<script lang="ts">
  export let balance: number;
</script>

<section>
  <div>
    <h2>My balance</h2>
    <p>${balance}</p>
  </div>
  <svg width="72" height="48" viewBox="0 0 72 48" xmlns="http://www.w3.org/2000/svg">
    <g fill="none" fill-rule="evenodd">
      <circle fill="#382314" cx="48" cy="24" r="24" /><circle
        stroke="#FFF"
        stroke-width="2"
        cx="24"
        cy="24"
        r="23"
      />
    </g>
  </svg>
</section>

<style>
  section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 0.5rem;
    padding: 1rem;
    background-color: var(--soft-red);
    color: var(--very-pale-orange);
    width: 345px;
  }
  h2,
  p {
    padding: 0;
    margin: 0;
  }

  h2 {
    font-weight: 400;
    font-size: 0.8em;
  }

  p {
    font-weight: bold;
    font-size: 1.3em;
  }

  svg {
    transform: scale(0.8);
  }
</style>
