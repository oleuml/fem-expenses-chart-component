<script>
  import Balance from "./lib/Balance.svelte";
  import Spending from "./lib/Spending.svelte";
</script>

<main>
  <Balance balance={921.48} />
  <Spending month={[1, 2, 3, 4, 34, 4.33, 1, 234, 34]} />
</main>

<style>
  main {
    display: grid;
    place-content: center;
    gap: 1rem;
    height: 100vh;
  }
</style>
