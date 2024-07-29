<script>

  let myNameToday = "Beau gosse";

  let data = [
    { id: 1, name: "lucas", city: "lyon" },
    { id: 2, name: "jean", city: "paris" },
    { id: 3, name: "marc", city: "bordeaux" },
    { id: 4, name: "louis", city: "marseille" },
  ];

  let nameToAdd, nameToUpdate, cityToAdd, cityToUpdate;

  function addData() {
    data.push({ id: data.length, name: nameToAdd, city: cityToAdd });
  }

  function deleteData(i) {
    data.splice(i, 1);
		data = data;
  }

	function updateData(i) {
    data[i] = { id: i, name: "new", city: "new york" };
		data = data;
  }
</script>

<h1>Hello {myNameToday}!</h1>

{#each data as row, i}
  <p>
    <b>{row.id} :</b> {row.name} from {row.city}
    <button on:click={() => deleteData(i)}>X</button><br>
		<input type="text" bind:value={nameToUpdate}>
		<input type="text" bind:value={cityToUpdate}>
    <button on:click={() => updateData(i)}>Modifer</button><br>
  </p><hr>
{/each}
<h3>Ajouter une ligne</h3>
<input type="text" bind:value={nameToAdd}>
<input type="text" bind:value={cityToAdd}>

<button on:click={addData}>Ajouter une ligne</button>
