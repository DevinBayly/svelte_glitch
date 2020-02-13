<script>
  let name = "worlda";
  let a = 5;
</script>

<style>
  input {
    width: 50%;
  }
  #fake {
    background-color: blue;
  }
</style>

<input type="text" bind:value={name} />

<h1>hello {name}</h1>


<label>
  <input type="range" name="" id="" bind:value={a} />
  <input type="text" name="" id="num" bind:value={a} />
</label>
