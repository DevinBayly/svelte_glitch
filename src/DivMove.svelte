
<style>
#mover {
    width:50px;
    height:50px;
    background-color: red;
}</style>

<div id="mover" on:mousemove={handleMover}>
    {m.x} {m.y}
</div>

<script>
let m = {}
let handleMover = (e)=> {
    m.x = e.clientX
    m.y = e.clientY
}
</script>