<script>
  import Balance from "./lib/Balance.svelte";
  import Spending from "./lib/Spending.svelte";

  import data from "./assets/data.json";
</script>

<main>
  <Balance balance={921.48} />
  <Spending last7spendings={data} changeToLastMonth={2.4} totalMonth={478.33} featured="wed" />
</main>

<style>
  main {
    display: grid;
    place-content: center;
    gap: 1rem;
    height: 100vh;
  }
</style>
