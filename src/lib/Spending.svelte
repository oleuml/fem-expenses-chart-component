<script lang="ts">
  export let month: number[];
</script>

<section>
  <article>
    <h2>Spending - Last 7 days</h2>
    <ul>
      <li>
        <div style="--height: 50px" />
        mon
      </li>
      <li>
        <div style="--height: 100px" />
        tue
      </li>
      <li class="featured">
        <div style="--height: 150px" />
        wed
      </li>
      <li>
        <div style="--height: 90px" />
        thu
      </li>
      <li>
        <div style="--height: 45px" />
        fri
      </li>
      <li>
        <div style="--height: 80px" />
        sat
      </li>
      <li>
        <div style="--height: 50px" />
        sun
      </li>
    </ul>
  </article>
  <hr />
  <article class="total">
    <div>
      <h3>Total this month</h3>
      <p class="sum">${month.reduce((a, b) => a + b, 0)}</p>
    </div>
    <div>
      <p class="percentage">+2.4%</p>
      <h3>from last month</h3>
    </div>
  </article>
</section>

<style>
  ul {
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
  }
  .featured > div {
    background-color: var(--cyan);
  }
  ul > li > div {
    height: var(--height);
    width: 100%;
    background-color: var(--soft-red);
    border-radius: 0.2rem;
    margin-bottom: 0.5rem;
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
