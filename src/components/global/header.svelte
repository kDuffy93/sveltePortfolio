<script>
	import Nav from './nav.svelte';
</script>

<header>
<!-- 	For some reason this causes errors in FF > had to use the divs below and set a background-image.
	<img alt="logo" class="logo k" src="Assets/k.svg" />
	<img alt="logo" class="logo d" src="Assets/d.svg" /> -->
	<div class="logo k" ></div>
	<div class="logo d" ></div>
	<div class="navContainer">
		<Nav />
	</div>
</header>

<style>




	header {
		min-height: clamp(50px, 10vh, 10%);
		display: flex;
	}

	.logo {
        max-height: auto;
        min-width: 50px;
		aspect-ratio: 1;
		position: absolute;
		top: 5vh;
		left: 15vw;
	}
	.d,
	.k {
		pointer-events: none;
		will-change: transform, opacity; 
	}
	
.navContainer {
    position: relative;
    size:inherit;
    min-width: 80%;
    max-width: 80%;
    margin-left:20%;
    display: flex;
    justify-content: end;
    align-items: center;
}

	@media (max-width: 415px) {
	.logo {
		top: 1vh;
		left: 12.5vw;

	}
}

</style>
