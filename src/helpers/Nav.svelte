<script>
    import Tailwindcss from '../helpers/Tailwindcss.svelte';
</script>

<Tailwindcss />

<div id="nav">

    <nav class="flex w-full justify-between items-center">\
        <!-- burger menu -->
        <a href="#/menu" class="p-10 pl-12 z-10 text-black hover:text-blue-500 transition-colors duration-300 bg-white rounded-full fixed bg-opacity-80">
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
        </a>
        <!-- need an invisible item because burger menu stays on page -->
        <div id="dummyitem" class="p-12 w-8"></div>
        <!-- logo -->
        <a href="#/" class="text-black">
            <div class="flex items-center justify-center">
                <img src="../images/logo-no-text.png" alt="Logo" class="h-16">
                <div class="ml-2">
                    <h1 class="text-2xl m-0">Wild<span class="font-black">Lands</span></h1>
                    <p class="text-xs m-0">Endless Discoveries</p>
                </div>
            </div>
        </a>
        <!-- about icon -->
        <a href="#/about" class="p-12 text-black hover:text-blue-500 transition-colors duration-300">
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
        </a>
    </nav>
    <!-- line below page header-->
    <hr class="-mt-2 mb-2 border-0 border-b-2 border-gray-300 mx-12"/>
</div>