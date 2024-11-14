<script>
    export let todos;
    export let removeFromList;
</script>

<div class='rounded-lg shadow-lg p-8 flex flex-col gap -4'>
    {#each todos as item, index}
   <div class='rounded-md p-4 justify-between flex flex-row border-2 border-gray-800'>
       <div class="font-medium text-sm">{item.text}</div>
       <button on:click={() => removeFromList(index)}>X</button>
   </div>
   {/each}
</div>