<svelte:head>
  <title>Story Page</title>
</svelte:head>



<div class="carousel w-full h-full pt-16">
  <div id="slide1" class="carousel-item relative w-full h-full flex items-center justify-center flex-wrap pb-6">
    <div class="h-[50%] aspect-[2/3] rounded-[20px] shadow-2xl bg-cover bg-black float-left md:mr-16" style="background-image: url(/vrdude.jpg);"></div>
    <div class="max-w-sm mx-10 md:mx-0">
      <p class="text-3xl font-bold font-serif text-center text-neutral md:text-left">The Future of VR Tech</p>
      <p class="mt-4 text-center md:text-justify">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer ac turpis vitae metus interdum pharetra et ut ligula. Aenean semper suscipit ullamcorper. In hac habitasse platea dictumst. Aenean eu metus euismod, tincidunt ante at, vulputate magna. In pulvinar, lectus sed iaculis ornare, erat magna pretium augue, eget ornare ante orci at tellus. </p>
      <div class="w-full flex justify-center md:justify-start" data-sveltekit-reload>
        <a href="/play/1234/1"><button class="btn btn-primary mt-4">Play the Preview</button></a>
      </div>
    </div>
    <div class="absolute flex justify-end transform -translate-y-1/2 left-5 right-5 top-1/2">
      <!-- <a href="#slide2" class="btn btn-circle">❮</a>  -->
      <a href="#slide2" class="btn btn-circle">❯</a>
    </div>
  </div> 
  <div id="slide2" class="carousel-item relative w-full h-full flex items-center justify-center flex-wrap pb-6">
    <div class="h-[50%] aspect-[2/3] rounded-[20px] shadow-2xl bg-cover bg-black float-left md:mr-16" style="background-image: url(/chessdude.jpg);"></div>
    <div class="max-w-sm mx-10 md:mx-0">
      <p class="text-3xl font-bold font-serif text-center text-neutral md:text-left">How does AI Play Chess?</p>
      <p class="mt-4 text-center md:text-justify">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer ac turpis vitae metus interdum pharetra et ut ligula. Aenean semper suscipit ullamcorper. In hac habitasse platea dictumst. Aenean eu metus euismod, tincidunt ante at, vulputate magna. In pulvinar, lectus sed iaculis ornare, erat magna pretium augue, eget ornare ante orci at tellus. </p>
      <div class="w-full flex justify-center md:justify-start" data-sveltekit-reload>
        <a href="/play/1234/1"><button class="btn btn-primary mt-4">Play the Preview</button></a>
      </div>
    </div>
    <div class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2">
      <a href="#slide1" class="btn btn-circle">❮</a> 
      <!-- <a href="#slide1" class="btn btn-circle">❯</a> -->
    </div>
  </div> 
</div>