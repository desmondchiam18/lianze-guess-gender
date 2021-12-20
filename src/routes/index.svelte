<script>
    let name = ""
    let gender = ""

    async function getName() {
    fetch('https://api.genderize.io/?name=' + name)
      .then((response) => response.json())
      .then((data) => {
        gender = data.gender; 
      });
    }
</script>


<h1>Guess gender</h1>

<form on:submit|preventDefault={getName}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>
<p>Gender: {gender}</p>

