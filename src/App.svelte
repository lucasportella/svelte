<script>
	import ComponentExample from "./ComponentExample.svelte";
  let people = [
    { name: 'yoshi', beltColour: 'black', age: 25, id: 1 },
    { name: 'mario', beltColour: 'orange', age: 45, id: 2 },
    { name: 'luigi', beltColour: 'brown', age: 35, id: 3 },
  ];
  let name = 'Lucas';
  let lastname = 'Portella';
  let num = 3;

  // reactive value:
  $: fullname = `${name} ${lastname}`;
  const handleInput = (e) => {
    name = e.target.value;
  };
  const handleClick = () => {
    name = 'new title';
  };
</script>

<main>
  <h1>Hello {fullname}!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
	{#if num > 10}
	<h2>greater than 10</h2>
	{:else if num > 5}
	<h2>greater than 5</h2>
	{:else}
	<h2>not greater than 5</h2>
	{/if}
  <button on:click={handleClick}>update title</button>
  <input on:input={handleInput} bind:value={name} />
  <!-- loop: -->
  <!-- (person.id) = react key -->
  {#each people as person (person.id)}
    <p>{person.name}</p>
    <p>{person.age}</p>
  {:else}
    <p>No people to show</p>
  {/each}
	<ComponentExample/>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
