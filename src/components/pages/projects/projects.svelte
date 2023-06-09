<script>
	import { navigating } from '$app/stores';
	import { onMount, afterUpdate } from 'svelte';
	let projects = {
		project5: {
			name: 'Rental Data Web Scraper',
			liveLink: 'https://mesn-frontend-xi.vercel.app/',
			repoLinks: [
				{ for: 'Front-End', link: 'https://github.com/kDuffy93/MESN-frontend' },
				{ for: 'Back-End', link: 'https://github.com/kDuffy93/MESN-backend' }
			],
			description:
				`A web scraping application to grab local rental listings from various websites in the county and 
				save the data for further use withing the county departments.`,
			login: {
				authReq: true,
				username: 'rich',
				password: 'password'
			},
			mobile: true,
			notes: ['* The First back-end server request (Login) takes a minute to respond, Its not frozen - the server is turning on. *'],

		},
		project1: {
			name: 'Story-Maker js Assignment',
			liveLink: 'https://kduffy93.github.io/comp1073Labs/assignment1/index.html',
			repoLinks: [
				{ for: 'Fullstack', link: 'https://github.com/kDuffy93/comp1073Labs/tree/main/assignment1' }
			],
			login: {
				authReq: false,
				username: '',
				password: ''
			},
			description:`A web application built using HTML, CSS, and Vanilla JS to replicate/expand-upon a physical game built in the 90's for children`,
			mobile: true,
			notes: [],

		},
		project2: {
			name: 'Rocketship game',
			liveLink: 'https://kduffy93.github.io/comp1073Labs/lab4/lab-4-start.html',
			repoLinks: [
				{ for: 'Fullstack', link: 'https://github.com/kDuffy93/comp1073Labs/tree/main/lab4' }
			],
			description: 'A fun little rocket-ship game for any device with access to a browser. built using HTML, CSS and vanilla javascript.',
			login: {
				authReq: false,
				username: '',
				password: ''
			},
			notes: [],
			mobile: true
		},
		project3: {
			name: 'Cocktail App',
			liveLink: 'https://kduffy93.github.io/comp1073Labs/assignment4/index.html',
			repoLinks: [
				{ for: 'Fullstack', link: 'https://github.com/kDuffy93/comp1073Labs/tree/main/assignment4' }
			],
			description: 'A web application built using HTML, CSS, and Vanilla JS and utilizing an API to retrieve data and display cocktail ingredients for various drinks based on the users input. .',
			login: {
				authReq: false,
				username: '',
				password: ''
			},
			notes: [],
			mobile: false
		},
		project4: {
			name: 'Ramara Training App',
			liveLink: 'https://ramaraapp2019.onrender.com/',
			repoLinks: [{ for: 'Fullstack', link: 'https://github.com/kDuffy93/ramaraApp2019' }],
			description: 'A data driven Web-application to track employee health and safety certificates as well as contractors. Technologies Used: Node, Express, EJS, MongoDB, Bootstrap, Css, and more.',
			notes: ['* Takes a minute to start up at first - Its running on a free server *', '** Auth dosent work through iframe on all devices - view full website if it wont log you in. *'],
			mobile: true,
			login: {
				authReq: true,
				username: 'test',
				password: 'test'
			}
		},
		
	};

	let screenWidth = 0;
	let oldSW = screenWidth;
	$: selectedProject = projects.project5;

	let screenHeight;

	$: if (screenWidth < 900 && selectedProject.mobile == false) {
		selectedProject = projects.project1;
	}

	$: if (screenWidth != oldSW) {
		console.log(`new: ${screenWidth} | old: ${oldSW}`);
		updateNavButtonLocations();
		oldSW = screenWidth;
	}

	let selectProject = (e) => {
		let sideNavButtons = [...document.getElementsByClassName('sideNavButton')];
		console.log(sideNavButtons);
		sideNavButtons.forEach((button) => {
			button.classList.remove("active");
			console.log(button.id);
			console.log(e.target.id);
			if(String(button.id) == String(e.target.id)){
				console.log("this one should have active");
				button.classList.add("active");
			}
		});
		for (const project in projects) {
			if (Object.hasOwnProperty.call(projects, project)) {
				const currentProject = projects[project];
				if (project == e.target.id) {
					selectedProject = currentProject;
				}
			}
		}
	};

	$: if ($navigating) updateNavButtonLocations();

	let updateNavButtonLocations = () => {
			let sideNavButtons = [...document.getElementsByClassName('sideNavButton')];
			let tempIndex = 0;
			sideNavButtons.forEach((button) => {
				let currentButtonWidth = button.getBoundingClientRect().width;
				console.log(currentButtonWidth);
				button.style.left = `-${currentButtonWidth - 25}px`;
				console.log(button.style.left);

				button.style.top = `calc(${20 + tempIndex * 75}px + 20vh)`;
				console.log(button.style.top);
				tempIndex++;
			});
	};

	onMount(() => {
		setTimeout(() => {
			updateNavButtonLocations();
		window.addEventListener('resize', updateNavButtonLocations);

}, 1000);

		
	});


	
</script>

<svelte:window bind:innerWidth={screenWidth} bind:innerHeight={screenHeight}  />

<div class="projectsContainer">
	<nav id="mySidenav" class="sidenav">
		{#each Object.entries(projects) as [title, content], i}
			{#if screenWidth < 900}
				{#if content.mobile}
					{#if title == 'project5'}
					<button on:loadstart={updateNavButtonLocations}  on:click={selectProject} class="sideNavButton active"	id={title}>{content.name}</button>
					{:else}
					<button on:loadstart={updateNavButtonLocations}  on:click={selectProject} class="sideNavButton"	id={title}>{content.name}</button>
					{/if}
				{/if}
			{:else}
			{#if title == 'project5'}
			<button on:loadstart={updateNavButtonLocations}  on:click={selectProject} class="sideNavButton active"	id={title}>{content.name}</button>
			{:else}
			<button on:loadstart={updateNavButtonLocations}  on:click={selectProject} class="sideNavButton"	id={title}>{content.name}</button>
			{/if}
			{/if}
		{/each}
	</nav>

	<div class="selectedProject">
		<div class="details">
			<div class="liveLinkContainer">
				<h3>Live Link</h3>
				<div class="buttonContainer">
					<button><a href={selectedProject.liveLink}>View Website</a></button>
				</div>
			</div>
			<div class="reposContainer">
				<h3>Reposotories</h3>
				<div class="buttonContainer">
					{#each selectedProject.repoLinks as repoLink}
						<button><a href={repoLink.link}>{repoLink.for} Repo</a></button>
					{/each}
				</div>
			</div>
			<div class="descriptionContainer">
				<div class="authContainer">
					{#if selectedProject.login.authReq == true}
						<label for="un">Username: </label>
						<p id="un">{selectedProject.login.username}</p>
						<label for="pw">Password: </label>
						<p id="pw">{selectedProject.login.password}</p>
					{/if}
				</div>
				<div class="descriptionText">
					<p class='description'>
						{selectedProject.description}
					</p>
					{#each selectedProject.notes as note}
							<p>{note}</p>
					{/each}
				
				</div>
			</div>
		</div>
		<iframe src={selectedProject.liveLink} class="resized" title="selectedProject.liveLink}" />
	</div>
</div>

<style>


	.projectsContainer {
		margin-left: 2.5%;
		margin-top: 50px;
		width: 95%;
		height: 100%;
		flex-grow: 1;
		min-height: max-content;
		display: flex;
		flex-direction: column;
	}

.description{
	margin-top:2.5%;
	margin-bottom: 5%;
}	#mySidenav button {

	left: -100vw;
	}
		#mySidenav button {
			white-space: nowrap;
			position: fixed; /* Position them relative to the browser window */
			transition: 0.3s; /* Add transition on hover */
			padding: 15px; /* 15px padding */
			width: fit-content; /* Set a specific width */
			text-decoration: none; /* Remove underline */
			font-size: 20px; /* Increase font size */
			color: white;
			background-color: black; /* White text color */
			border-radius: 0 5px 5px 0; /* Rounded corners on the top right and bottom right side */
		}
		#mySidenav button::after {
			content: src('/static/Assets/right-arrow.svg');
			position: absolute;
			left: 102%;
		}
		#mySidenav button:hover{
			left: 0 !important; /* On mouse-over, make the elements appear as they should */
		}

		#mySidenav button:hover::after {
			content: '';
		}

					@media not screen and (max-device-width: 1280px) {
						.projectsContainer {
		margin-left: 6.5%;
		width: 91%;

		}	
					}
	@media only screen and (max-device-width: 1080px) {
		.projectsContainer {
		margin-left: 2.5%;
		}		nav {
		border-radius: 15px;
		padding: 10px;
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
		width: 95%;
		height: 10%;
		min-height: 40px;
		margin-left: 2.5%;
		margin-top: 2.5%;
		align-items: center;
		justify-content: space-evenly;
	}
	#mySidenav button {
		white-space: unset;
		position:unset;
		color: white;
			background-color: black; /* White text color */
			border-radius: 0 5px 5px 0;
		border-radius: 12.5px;
		padding: 5px;
		min-width: 115px;
		width: clamp(115px, 28vw, 175px);
border-radius: 7.5px;
min-height: 6ch;

	}
}
	.selectedProject {
		margin-top: 2.5%;
		margin-left: -2.5%;
		flex-grow: 1;
		display: flex;
		flex-direction: column;
		height: 90%;
	}

	.details {
		width: 100%;
		height: fit-content;
		padding: 1%;
		display: grid;
		grid-template-columns: repeat(7, 1fr);
		grid-template-areas: ' . liveLink liveLink . repoLinks repoLinks .' '.description description description description description .';
		margin-bottom: 15px;
	}
	.details > .descriptionContainer {
		grid-area: description;
		text-align: center;
		font-size: calc(16px + (20 - 16) * (100vw - 320px) / (1080 - 320));
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.descriptionContainer > .descriptionText {
		flex-grow: 1;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 15px;
	}
	.descriptionContainer > .authContainer {
		display: grid;
		grid-template-columns: repeat(4, 25%);
		align-items: center;
		justify-self: flex-start;
		margin: 5px 0 25px 0;

	}
	label {
		font-size: calc(12px + (14 - 12) * (100vw - 320px) / (1080 - 320));
		height: fit-content;
		justify-self: flex-end;
		padding-right: 7.5%;
		margin-top: 3%;
		box-sizing:content-box;


	}
	.authContainer > p {
		font-size: calc(21px + (24 - 21) * (100vw - 320px) / (1080 - 320));
		height: fit-content;
		font-weight: bold;
		justify-self: flex-start;
		background-color: rgba(0, 0, 0, 0.859);
		border-radius: 25px;
		padding: 5px 10px 10px 10px;
		border: 1px solid white;
	}

	.details > .liveLinkContainer {
		grid-area: liveLink;
	}
	.details > .liveLinkContainer,
	.details > .reposContainer {
		display: flex;
		flex-direction: column;
		padding: 5% 5% 5% 5%;
		border-radius: 20px;
		justify-content: flex-start;
		width: fit-content;
justify-self: center;
background-color: black;
margin-bottom: 25px;
	}
	.buttonContainer {
		display: flex;
		gap: 10px;
		flex-direction: column;
		height: 100%;
		align-items: center;
		justify-content: space-around;
	}
	.buttonContainer {
		margin-top: 10px;
	}
	.liveLinkContainer > .buttonContainer > button,
	.reposContainer > .buttonContainer > button {
		width: fit-content;
		min-width: 125px;
		align-self: center;
		text-decoration: underline;
		padding: 1%;
		border-radius: 7.5px;
	}
	.liveLinkContainer > h3,
	.reposContainer > h3 {
		width: fit-content;
		align-self: center;
		text-decoration: underline;
		flex-grow: 0;
	}

	.details > .reposContainer {
		grid-area: repoLinks;
	}
	.selectedProject > iframe {
		flex-grow: 1;
		width: clamp(320px, 100vw 1920px);
		height: clamp(600px, 100vh, 1080px);
		background-color: #b6b6b6;
		border: 5px solid black;
		border-radius: 5px;
		box-shadow: 1em 0.75em 0.4em rgba(0, 255, 255, 0.25), -1em -0.75em 0.4em rgba(255, 0, 0, 0.25);
		margin-bottom: 5vh;
	}


</style>
