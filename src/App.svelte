<script>
  let people = [
    { name: "yoshi", beltColoour: "black", age: 25, id: 1 },
    { name: "mario", beltColoour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColoour: "brown", age: 35, id: 3 },
  ];

  const handleClick = (id) => {
    people = people.filter((person) => person.id != id);
  };

  let num = 3
</script>

{#if num > 20}
  <p>Greater than 20</p>
  {:else if num > 5}
  <p>Greater than 5</p>
  {:else}
  <p>Not greater than 5</p>
{/if}

<main>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColoour === 'black'}
        <p><strong>MASTER NINJA</strong></p>
      {/if}
      <p>{person.age} years old, {person.beltColoour} belt</p>
      <button on:click={() => handleClick(person.id)}> delete </button>
    </div>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>

<!-- <script>
  let firstName = "Jimi";
  let lastName = "Hendrix";
  let beltColour = "black";

  $: fullName = `${firstName} ${lastName}`;
  $: {
    console.log(beltColour);
    console.log(fullName);
  }
  const handleClick = () => {
    beltColour = "orange";
  };
  const handleInput = (e) => {
    beltColour = e.target.value;
  };
</script>

<main>
  <p>{fullName} {beltColour} belt</p>
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" name="" bind:value={beltColour} />
</main>
 -->

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
