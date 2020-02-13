<script>
  let name = "worlda";
  let a = 5
  let mytestattr
  let widthattr
$: widthattr = `width:${mytestattr}px;height:${mytestattr}px` 
setInterval(()=> {mytestattr=Math.floor(Math.random()*150)},1500)
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

<input type="text" name="" id="" bind:value={mytestattr}>
<div id="fake"  style={widthattr}></div>

<label >
    <input type="range" name="" id="" bind:value={a}>
    <input type="text" name="" id="num" bind:value={a}>
</label>