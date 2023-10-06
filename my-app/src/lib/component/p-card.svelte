<script lang="ts">
    import { Card, Button } from 'flowbite-svelte';
    import{order_num} from "../store";
var amount = 1;
var cost = 20;
    var increament = () =>{
amount++
cost = cost + 20
    }

    var decreament = () =>{

  if(amount!=1){
    amount--
    cost = cost - 20
  }
}

var add_order =()=>{
   order_num.update((prev) => prev += 1)
  }




    
  </script>
  
  <Card class="text-center flex" size="lg" padding="xl">
    <div class="w-full flex justify-center">
    <img class="p-8 w-80  rounded-t-lg" src="../img/dress-1.png" alt="product 1" />
</div>
    <h5 class="mb-2 text-3xl font-bold text-gray-900 dark:text-white">Dress</h5>
    <p class="mb-5 text-base text-gray-500 sm:text-lg dark:text-gray-400">When choosing a summer dress you want to find something that will keep you cool but also looking good. While each woman will have different opinions on the best summer dress, ultimately it’s up to you to choose what you’re comfortable and confident in.</p>


    <div class="flex justify-between items-center gap-3 my-8">
<div class="flex gap-2">
<button class="bg-light-100 text-white w-12 h-12 rounded-md" on:click={increament}>+</button>
    <p class="w-14 h-12 text-center border border-2 rounded-md flex justify-center items-center ">{amount}</p>
    <button class="bg-light-100 text-white w-12 h-12 rounded-md" on:click={decreament}>-</button>
  </div>
   
   
    <p class="text-4xl flex items-ceneter">{cost}$</p>

</div>
    <div class="justify-center items-center space-y-4 sm:flex sm:space-y-0 sm:space-x-4">
      <a href="/">
      <Button class="bg-light-200 hover:bg-light-100" on:click={add_order}>ORDER</Button>
    </a>
    </div>
  </Card>