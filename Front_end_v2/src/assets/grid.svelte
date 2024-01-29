<script>
    

    let rows = 6;
    let columns = 4;
    
    let ara = [1,0,0,1,
              1,1,1,1,
              1,0,0,1,
              0,1,0,1,
              0,0,0,1,
              0,0,0,1]

    

    
</script>
  
<div class="grid grid-cols-6 gap-4">
    {#each Array(rows) as _, rowIndex}
      {#each Array(columns) as _, colIndex}
        {#if ara[columns*rowIndex + colIndex] === 0}
        <div class="bg-green-300 p-4 text-center cursor-pointer">
          {String.fromCharCode(65 + rowIndex)}{colIndex + 1}
        </div>

        {:else}
        <div class="bg-red-300 p-4 text-center cursor-not-allowed">
            {String.fromCharCode(65 + rowIndex)}{colIndex + 1}
        </div>

        {/if}

        {#if colIndex === columns/2-1}

            <div class= "p-4"> </div>
            <div class= "p-4"> </div>
        
        {/if}

      {/each}
    {/each}
</div>