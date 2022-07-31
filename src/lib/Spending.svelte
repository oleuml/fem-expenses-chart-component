<script lang="ts">
  export let last7spendings: { day: string; amount: number }[];
  export let totalMonth: number;
  export let changeToLastMonth: number;
  export let featured: string;

  export let maxSpending = Math.max(...last7spendings.map((x) => x.amount));
</script>

<section>
  <article>
    <h2>Spending - Last 7 days</h2>
    <ul style="min-height: {maxSpending * 3}px">
      {#each last7spendings as { day, amount }}
        {@const height = amount / maxSpending}
        <li class:featured={featured === day} on:click={() => (featured = day)}>
          <div
            class="bar bar-animated"
            style="--value: '${amount}';--height: calc({amount}px * 2.5)"
          />
          {day}
        </li>
      {/each}
    </ul>
  </article>
  <hr />
  <article class="total">
    <div>
      <h3>Total this month</h3>
      <p class="sum">${totalMonth}</p>
    </div>
    <div>
      <p class="percentage">+{changeToLastMonth}%</p>
      <h3>from last month</h3>
    </div>
  </article>
</section>

<style>
  ul {
    counter-reset: count;
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    padding: 0;
    text-align: center;
    align-items: flex-end;
    list-style: none;
    gap: 0.7rem;
  }
  ul > li {
    color: var(--medium-brown);
    font-size: 0.6em;
    cursor: pointer;
  }
  .featured > .bar {
    background-color: var(--cyan);
  }
  .bar {
    --value: "0";
    position: relative;
    cursor: pointer;
    height: 0;
    width: 100%;
    background-color: var(--soft-red);
    border-radius: 0.2rem;
    margin-bottom: 0.5rem;
    transition: background-color 200ms ease;
  }

  .bar:hover {
    opacity: 0.7;
  }
  .bar:hover::before {
    content: var(--value);
    display: flex;
    position: absolute;
    justify-content: center;
    text-align: center;
    color: black;
    top: -1.45rem;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 0.2rem;
    padding: 0.2rem;
    background-color: var(--dark-brown);
    font-weight: 700;
    color: var(--very-pale-orange);
  }

  .bar-animated {
    --animation-delay: 100ms;
    animation: growing-height 250ms ease-in-out forwards;
  }

  ul > li:nth-child(1) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 100ms);
  }
  ul > li:nth-child(2) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 200ms);
  }
  ul > li:nth-child(3) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 300ms);
  }
  ul > li:nth-child(4) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 400ms);
  }
  ul > li:nth-child(5) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 500ms);
  }
  ul > li:nth-child(6) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 600ms);
  }
  ul > li:nth-child(7) > .bar-animated {
    animation-delay: calc(var(--animation-delay) + 700ms);
  }

  @keyframes growing-height {
    from {
      height: 0;
    }
    to {
      height: var(--height);
    }
  }
  hr {
    display: block;
    border-style: solid;
    border-width: 1px;
    width: 100%;
    color: var(--cream);
  }
  section {
    border-radius: 0.5rem;
    padding: 1rem;
    background-color: var(--very-pale-orange);
    color: var(--dark-brown);
    width: 345px;
  }
  h2,
  p {
    padding: 0;
    margin: 0;
  }
  .sum {
    font-size: 1.5em;
    font-weight: 700;
  }

  .percentage {
    text-align: end;
    font-size: 0.8em;
    font-weight: 700;
  }
  .total {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }
  h2 {
    font-weight: 700;
    font-size: 1.3em;
  }

  h3 {
    color: var(--medium-brown);
    font-weight: 400;
    font-size: 0.8em;
  }
</style>
