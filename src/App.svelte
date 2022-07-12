<script>

  // count
  let count = 0;
  $: doubled = count * 2;
  $: if (count >= 10) {
    alert('count is dangerously high!');
    count = 9;
  }

  function incrementCount() {
    count += 1;
  }
  //arrays
  let numbers = [1, 2, 3, 4];

  function addNumber() {
    numbers.push(numbers.length + 1);
    numbers = numbers;
  }

  $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<button on:click={incrementCount} >
  Clicked {count} {count === 1 ? 'time' : 'times'}
  Doubled is {doubled}
</button>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
  Add a number
</button>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  img {
    height: 16rem;
    width: 16rem;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
