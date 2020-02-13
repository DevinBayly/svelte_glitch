<script>
// call async function
import Dispatcher from './Dispatcher.svelte'
import Input from "./Input.svelte"
import {mystore} from './mystore.js'
let promise = getNumber()
function delay(ms) {
    return new Promise(res=>setTimeout(res,ms))
}
async function getNumber() {
    return await delay(1000).then(res=> Math.floor(Math.random()*10))
}
// put the returning function as the resolve in the promise returned

let eventSet
function catchCustom(event) {
   eventSet = event.detail.text
}

let handleClick =()=> {
    promise = getNumber()
    // connect to the dispatcher
    promise.then(n=> {
        mystore.update((e)=> e+n)
    })
}
let text = "default"
let handler = (e)=> {
    console.log("caugth",e.detail.text)
}
let store_value
const unsubscribe = mystore.subscribe(v=> {
    store_value = v
})
let handler2 = (e)=> {
    text = e.detail.text+"check"
}

</script>

<button on:click={handleClick}>Change</button>
{#await promise}
<p>waiting ...</p>
{:then number}
<p>number is {number}{store_value}</p>
{/await}
<Dispatcher on:customEvent={handler}/>
<div id="tset" on:customEvent={handler2}>{text}</div>
<p>{$mystore}</p>