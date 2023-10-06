<script lang="ts">
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
    import { page } from '$app/stores';
    $: activeUrl = $page.url.pathname;

   import {order_num} from "../store"
   var order_count = 0
   order_num.subscribe((val)=> val = order_count)
   
  </script>

<Navbar rounded color="form" class="bg-light-100 rounded-none text-white">
    <div class="flex justify-between flex-row-reverse flex-wrap md:flex-nowrap md:justify-between w-full h-auto items-center">
      <div class="flex flex-row-reverse gap-5 items-center ">
        <i class="fa-solid fa-basket-shopping fa-xl">
        
          <p class = "bg-orange-400 w-5 h-5 text-xs p-2 rounded-lg absolute text-white flex items-center justify-center">{$order_num}</p>
        </i>
        <button class="rounded-md bg-light-200 px-2">Favourites</button>
      </div>
    <NavBrand href="/" >
      <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Online Shop</span>
    </NavBrand>
   
    
    
</div>
  </Navbar>





  
  <Navbar rounded color="form" class="bg-light-200 rounded-none text-white">
    <div class="flex justify-center flex-wrap md:flex-nowrap md:justify-around w-full h-auto items-center">
        

    <NavHamburger />
    
    <NavUl {activeUrl}
  
    activeClass="bg-white text-black rounded-lg md:px-2 md:py-2 flex justify-center"
    nonActiveClass="text-white md:px-2 md:py-2"
    >
    
      <NavLi href="/" active={true}>Home</NavLi>
      <NavLi href="/about">Category</NavLi>
      <NavLi href="/docs/components/navbar">Blog</NavLi>
      <NavLi href="/contact">Contact</NavLi>
    </NavUl>
    
</div>
  </Navbar>
  