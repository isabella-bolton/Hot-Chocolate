<script>
let name = ""
let tempC = 20
$: tempF = Math.round (tempC * 1.8 + 32)
</script>

<h1>Hot Chocolate</h1>

<label>
Name: 
<input type= "text" bind:value={name}>
</label>

<label>
Drink temperature 
<input type="range" min= "0" max= "100" bind:value={tempC} >
</label>

{#if name.length >0}
    <p> Hi {name}, your drink is {tempC} degrees ({tempF} degrees Fahrenheight).</p>


    {#if tempC < 40}
    ... Fairly tepid 🥶
    {:else if tempC > 90}
    ... Very hot! 🥵
    {:else}
    ... Looks good 🙂
    {/if}

{/if}