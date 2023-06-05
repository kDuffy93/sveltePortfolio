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

</style>
