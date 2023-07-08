<script>
    export let data;

</script>

<div class="min-h-full bg-white flex items-center justify-center">
    <div class="hero-content text-center text-neutral flex-col justify-center pt-16">
        <img src="/revali_pfp.jpg" alt="" class="rounded-full max-w-[50%] pb-3">
        <div class="max-w-md px-10">
            <h1 class="mb-5 text-4xl md:text-5xl font-bold font-serif">Welcome to Penvl</h1>
            <p class="mb-5 text-xl">A visual novel platform where you can create, publish, and share your own visual novels or enjoy others' creations!</p>
            <a href="/stories">
                <button class="btn btn-primary m-2">Explore Stories</button>
            </a>
            {#if !data.session}
                <a href="/signup">
                    <button class="btn btn-secondary m-2">Create an Account</button>
                </a>
            {/if}
        </div>
    </div>
</div>
