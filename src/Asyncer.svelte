<script>
// call async function
let promise = getNumber()
function delay(ms) {
    return new Promise(res=>setTimeout(res,ms))
}
async function getNumber() {
    return await delay(1000).then(res=> Math.floor(Math.random()*10))
}
// put the returning function as the resolve in the promise returned

let handleClick =()=> {
    promise = getNumber()
}
</script>

<button on:click={handleClick}>Change</button>
{#await promise}
<p>waiting ...</p>
{:then number}
<p>number is {number}</p>
{/await}
