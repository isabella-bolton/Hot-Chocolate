<script>
let name = ""
let tempC = 20
$: tempF = Math.round (tempC * 1.8 + 32)
</script>

<h1>Hot Chocolate</h1>

<section class= "section">

<label class= "label"> 
    Name: 
    <input class= "input" type= "text" bind:value={name}>
</label>

<label class= "label">
Drink temperature 
<input class= "input" type="range" min= "0" max= "100" bind:value={tempC} >
</label>

{#if name.length >0}
    <p> Hi {name}, your drink is {tempC}°C ({tempF}°F).</p>


    {#if tempC < 40}
    ... Fairly tepid 🥶
    {:else if tempC > 90}
    ... Very hot! 🥵
    {:else}
    ... Looks good 🙂
    {/if}

{/if}
</section>