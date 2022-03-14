<script>
	let count = 0;

  $: doubled = count * 2;

	function incrementCount() {
		count += 1;
	}

  $: if (count >= 10) {
	  alert('count is dangerously high! Resetting..');
	  count = 0;
}

let numbers = [1, 2, 3, 4];

	function addNumber() {
		numbers.push(numbers.length + 1);
		numbers = [...numbers, numbers.length + 1];
	}

	$: sum = numbers.reduce((t, n) => t + n, 0);

</script>

<p>{count} doubled is {doubled}</p>

<button on:click={incrementCount}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>


<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
	Add a number
</button>

<style>
  button {
    border-radius: 20px;
  }

  p {
    font-size: 20px;
    font-family: "Comic Sans MS";
  }
</style>