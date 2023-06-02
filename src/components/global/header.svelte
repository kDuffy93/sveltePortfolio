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
        min-width: clamp(50px, 9.5vh, 9%);
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
	.k {
		background-image:  url(Assets/whiteK.svg);
		background-repeat: no-repeat;
		animation: rotationk 3s infinite linear;
		transform-origin: left;
		z-index: 10;
	}
	.d {
		background-image:  url(Assets/whiteD.svg);
		background-repeat: no-repeat;

		animation: rotationd 3s infinite linear;
		transform-origin: left;
		z-index: 10;
	}
	@keyframes rotationk {
		from {
			transform: rotateY(0deg);
			opacity: 1;
		}
		
        50%{
			opacity: .1;

        }
        75%{
            opacity: 0;
        }

		to {
			transform: rotateY(360deg);
			opacity: 1;
		}
		
	}



	@keyframes rotationd {
		from {
			opacity: 0;

			transform: rotateY(-90deg);
		}
        25%{
            opacity: 1;

        }

        75%{
            opacity: .1;
        }

		to {
			opacity: 0;
			transform: rotateY(270deg);
		}
	
	}
</style>
