<script>

import {createEventDispatcher} from 'svelte'

const dispatch = createEventDispatcher()

let text
$: text
function sayHI () {
    console.log("sending")
    text="hello!" +Math.random()
    dispatch("customEvent",{
        text,
    })
}
</script>

<button on:click={sayHI}>update text</button>
<div>{text}</div>
