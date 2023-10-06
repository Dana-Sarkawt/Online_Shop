<script>
    import { Carousel } from 'flowbite-svelte';
    
    import { scale } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
  
    // @ts-ignore
    const scaleAnimation = (x) => scale(x, { duration: 500, easing: quintOut });










  // ./imageData/+server.js has the following
  export const images = [
    {
      alt: 'Cosmic timetraveler',
      src: '../img/slide1.jpg',
      title: 'cosmic-timetraveler-pYyOZ8q7AII-unsplash.com'
    },
    {
      alt: 'Cristina Gottardi',
      src: '../img/slide2.jpg',
      title: 'cristina-gottardi-CSpjU6hYo_0-unsplash.com'
    },
    {
      alt: 'Johannes Plenio',
      src: '../img/slide1.jpg',
      title: 'johannes-plenio-RwHv7LgeC7s-unsplash.com'
    },
    
  ];
</script>
 
  
  <div class="w-5/6  container mx-auto mt-5">
    <Carousel {images} style="height:450px;" imgClass="w-full h-full bg-cover " transition={scaleAnimation} 
   
    let:Controls let:Indicators>
      <Controls class="bg-light-100 opacity-50 w-8 rounded-md "/>
      <Indicators activeClass="bg-dark-100" inactiveClass="bg-gray-200"/>
    </Carousel>
  </div>