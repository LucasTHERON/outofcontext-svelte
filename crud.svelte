<script>

  let myNameToday = "Beau gosse";

  let data = [
    { id: 1, name: "lucas", city: "lyon" },
    { id: 2, name: "jean", city: "paris" },
    { id: 3, name: "marc", city: "bordeaux" },
    { id: 4, name: "louis", city: "marseille" },
  ];

  let nameToAdd, cityToAdd;

  function addData() {
    data.push({ id: data.length, name: nameToAdd, city: cityToAdd });
  }

  function deleteData(i) {
    data.splice(i, 1);
		data = data;
  }
</script>

<h1>Hello {myNameToday}!</h1>

{#each data as row, i}
  <p>
    <b>{row.id} :</b> {row.name} from {row.city}
    <button on:click={() => deleteData(i)}>X</button>
  </p>
{/each}

<input type="text" bind:value={nameToAdd}>
<input type="text" bind:value={cityToAdd}>

<button on:click={addData}>Ajouter une ligne</button>
