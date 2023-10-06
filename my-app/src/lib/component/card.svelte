<script>
// @ts-nocheck

    import { Card, Button, Rating, Badge } from 'flowbite-svelte';



var cost = 20

    var favourite = 0
    let like = false;
   
function toggleLike() {
  like = !like;
  like == true  ? favourite += 1 : favourite -= 1
}
   
  </script>
 
  <Card padding="none" class="w-44">
    <a href="/dress">
      <img class="p-8 rounded-t-lg" src="../img/dress-1.png" alt="product 1" />
    </a>

   
    <div class="px-5 pb-5">
      <a href="/dress">
        <h5 class="text-xl font-normal tracking-tight text-gray-900 dark:text-white">Dress</h5>
      </a>
      <Rating rating="4" size="24" class="mt-2.5 mb-5">

        <Badge slot="text" class="ml-3">{favourite}</Badge>
      </Rating>
      <div class="flex justify-between w-full items-center">
        <span class="text-2xl font-bold text-gray-900 dark:text-white">{cost}$</span>
      <button on:click={toggleLike}>
        {#if like}
        <i class="fa-solid fa-heart cursor-pointer text-red-600" id="heart"></i>
    {:else}
        <i class="fa-regular fa-heart cursor-pointer" id="heart"></i>
        {/if}
    </button>
      </div>
    </div>
  </Card>

