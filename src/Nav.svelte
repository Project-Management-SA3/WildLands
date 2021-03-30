<script>
    import Logo from './Logo.svelte'
    import Counties from './helpers/counties.js'
    import { activeCounty, results, navHeight } from './helpers/stores.js';

    function updateCounty(theCounty) {
        activeCounty.set(theCounty);
	}


    let showMenu = false;

    function toggleMenu() {
        showMenu = !showMenu;
    }

</script>

<div id="nav" bind:clientHeight={$navHeight}>
 
    <!-- First row -->
	<!-- Top bar: Burger icon, logo and About Us icon -->
    <nav class="p-nav">

        <div class="p-nav-left">
            <!-- Burger icon, TODO @petercoyne menu -->
            <a href="#" class="p-nav-a" on:click={toggleMenu}>
                <svg fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            </a>
            <!-- Site logo -->
            <a href="/" class="p-logo">
                <img src="./Logos/logo-no-text.png" alt="Logo">
                <div>
                    <h1>Wild<b>Lands</b></h1>
                    <p>Endless Discoveries</p>
                </div>
            </a>
        </div>

        <div class="p-contact">
            <a href="www.facebook.com"><img src="Logos/facebook.png" width="22" alt="Loc"></a>
            <a href="www.instagram.com"><img src="Logos/insta.png" width="30" alt="Loc"></a>
            <div>
                <img src="Logos/location.png" alt="Loc" class="inline"> 31 Mallstreet, Galway
            </div>
            <div>
                <img src="Logos/phone.png" alt="Loc" class="inline"> 091 312 543
            </div>
        </div>

        <!-- About Us link
        <a href="about.html" class="p-nav-a">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
        </a> -->

    </nav>
    <!-- Border below navbar -->
    <hr style="border: 1px solid black; margin: 0" />

    <!-- Quick Access menu -->
    {#if showMenu}
    <div id="p-quickaccess">
        <a href="#" class="p-menuclose" on:click={toggleMenu}>
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
        </a>
        <div class="p-content text-4xl">
            <h1><a href="/">Home</a></h1>
            <h1><a href="about.html">About</a></h1>
            <h1><a href="counties.html">Counties</a></h1>
        </div>
    </div>
    {/if}

    <!-- counties -->
    <div class="flex pt-2 bg-black bg-opacity-50">
        <!-- This was a thing to show and hide the counties list
            <div> 
            <svg class="w-10 h-10 ml-12 mt-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            <img src="../images/logo-no-text.png" alt="Logo" class="ml-12 h-16">
        </div> -->
        <div class="flex-grow grid grid-cols-4 md:grid-cols-8 lg:grid-cols-12 justify-center px-12 pb-2 max-w-full text-center uppercase text-xs font-bold">
            {#each Counties as county}
                <a href="#/" on:click={() => updateCounty(county)} 
                    class="p-1 text-gray-200 normallink hover:bg-gray-900 rounded-md"
                    class:selected="{$activeCounty == county}">
                    {county}
                </a>
            {/each}
        </div>
    </div>
    <hr class="border-black"/>
</div>

<style>
    
.p-nav {
	color: white;
	display: flex;
	justify-content: space-between;
	background-image: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.4));
}

.p-nav-left {
	display: flex;
}

.p-nav-a {
	display: inline-block;
	padding: 3rem;
	color: white;
	transition: color 1s;
}

.p-nav-a:hover {
	color: rgb(163, 190, 137);
}

.p-nav svg {
	width: 2rem;
}

.p-nav .p-logo {
	display: flex;
	align-items: center;
	color: white;
}

.p-logo:hover {
	text-decoration: none;
}

.p-nav .p-logo img {
	height: 4rem;
	margin-right: 0.5rem;
}

.p-nav .p-logo h1 {
	font-size: 1.6rem;
	margin-bottom: 0;
	font-weight: normal;
}

.p-nav .p-logo p {
	font-size: 0.7rem;
	margin-bottom: 0;
}

.p-contact {
	/* background-color: rgba(0,0,0,0.5); */
	padding: 0.5rem 0;
	margin: 0 3rem;
	display: flex;
	justify-content: space-evenly;
	color: white;
	font-size: 0.8rem;
	align-items: center;
}

.p-contact > * {
	padding: 1rem;
	flex-shrink: 0;
}
	
.p-contact img {
	filter: invert(1);
}

#p-quickaccess {
	background: rgba(255,255,255,0.7);
	backdrop-filter: blur(10px);
	position: absolute;
	top: 2rem;
	left: 2rem;
	right: 2rem;

	border-radius: 1rem;
	z-index: 90;
}

.p-menuclose {
	display: block;
	color: black;
	padding: 1rem;
}

.p-menuclose svg {
	width: 2rem;
}

#p-quickaccess .p-content {
	padding: 1rem;
	text-align: center;
}


</style>