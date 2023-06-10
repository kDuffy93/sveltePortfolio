<script>
</script>

<div class="aboutContainer">
	<div>
		<img src="Assets/20221022_043327.jpg" />
	</div>


	<p>
		With over 13 years of experience in software development, I have cultivated a passion for
		programming and a deep appreciation for the art of problem-solving.
	</p>
	<p>
		I discovered my love for programming during high school when I was introduced to Java. The
		elegance and flexibility of the language captivated me, igniting a curiosity to explore its
		endless possibilities. From that point on, I delved deeper into the world of coding,
		continuously expanding my knowledge and skills.
	</p>
	<p>
		I am always eager to take on new challenges, collaborate with talented individuals, and stay up
		to date with the latest advancements in technology. My commitment to continuous learning and my
		passion for programming drive me to deliver high-quality solutions that exceed expectations.
	</p>
	<p>
		Thank you for taking the time to explore my portfolio. I invite you to review my resume and
		browse through the projects I have worked on. If you have any questions or would like to discuss
		potential collaborations, please feel free to reach out. I look forward to connecting with you!
	</p>
	<div class="resume">
		<iframe
			src="https://drive.google.com/file/d/1oowKdjpnO4lX6uZSDDVosulcFw1-cGcV/preview#zoom=FitH"
		/>
	</div>
</div>

<style>
	.aboutContainer {
		margin-top: 75px;
		width: 95%;
		height: fit-content;
		min-height: 75vh;
		display: grid;
		gap: 1%;
		grid-template-columns: 40% 60%;
		grid-template-areas:
			'photo resume'
			'short1 resume'
			'short2 resume'
			'short3 resume'
			'short4 resume';
margin-bottom: 60px;

	}

	@media screen and (max-width: 1075px) {
		.aboutContainer {
			grid-template-columns: 35% 65%;
			grid-template-areas:
				'photo .'
				'photo short1'
				'photo short2'
				'short3 short3'
				'short4 short4'
				'resume resume';
		}

		.aboutContainer > div:first-of-type {
			align-items: center;
		}
	}
	@media (max-width: 550px) {
		.aboutContainer {
			grid-template-columns: repeat(4, 1fr);
			grid-template-areas:
				'photo photo short1 short1'
				'short2 short2 short2 short2'
				'short3 short3 short3 short3'
				'short4 short4 short4 short4'
				'resume resume resume resume'
				'resume resume resume resume';

		}

		.aboutContainer > div:first-of-type > img {
			width: 80% !important;
			height: auto;
			align-self: center;
			aspect-ratio: 0.75;
			align-self: start;
		}
		.aboutContainer > p:first-of-type {
			width: 100%;
			align-self: end;
		}
	}

	@media (max-width: 635px) {
		.aboutContainer {
			grid-template-columns: repeat(4, 1fr);
			grid-template-areas:
				'photo photo short1 short1'
				'short2 short2 short2 short2'
				'short3 short3 short3 short3'
				'short4 short4 short4 short4'
				'resume resume resume resume'
				'resume resume resume resume'
				'. . . .';

		}
		.aboutContainer > p:first-of-type {
			width: 95%;
			align-self: end;
		}
	}

	.resume {
		grid-area: resume;
		width: 100%;
		display: flex;
		justify-content: center;
	}
	.resume > iframe {
		aspect-ratio: 0.75;
		width: 100%;
		max-width: 750px;
		max-height: fit-content;
	}
	.aboutContainer > div:first-of-type {
		grid-area: photo;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.aboutContainer > div:first-of-type > img {
		width: 60%;
		height: auto;
		aspect-ratio: 0.75;
	}

	.aboutContainer > p {
		max-width: 95%;
		text-align: center;
		justify-self: center;
		font-size: 22px;
		font-family: 'Edu NSW ACT Foundation', cursive;
	}
	.aboutContainer > p:first-of-type {
		grid-area: short1;
		align-self: end;
	}
	.aboutContainer > p:nth-of-type(2) {
		grid-area: short2;
		align-self: end;
	}
	.aboutContainer > p:nth-of-type(3) {
		grid-area: short3;
	}

	.aboutContainer > p:last-of-type {
		grid-area: short4;
	}
</style>
