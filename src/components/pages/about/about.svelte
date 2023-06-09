<script>
</script>

<div class="aboutContainer">
	<div>
		<img src="Assets/20221022_043327.jpg" />
	</div>
	<div class="resume">
		<iframe src="https://drive.google.com/file/d/1oowKdjpnO4lX6uZSDDVosulcFw1-cGcV/preview#zoom=FitH"/>
	</div>
	<div>
		<p>
			With over 13 years of experience in software development, I have cultivated a passion for
			programming and a deep appreciation for the art of problem-solving.
			<br /><br />I discovered my love for programming during high school when I was introduced to
			Java. The elegance and flexibility of the language captivated me, igniting a curiosity to
			explore its endless possibilities. From that point on, I delved deeper into the world of
			coding, continuously expanding my knowledge and skills.
			<br /><br />I am always eager to take on new challenges, collaborate with talented
			individuals, and stay up to date with the latest advancements in technology. My commitment to
			continuous learning and my passion for programming drive me to deliver high-quality solutions
			that exceed expectations.
			<br /><br />Thank you for taking the time to explore my portfolio. I invite you to review my
			resume and browse through the projects I have worked on. If you have any questions or would
			like to discuss potential collaborations, please feel free to reach out. I look forward to
			connecting with you!
		</p>
	</div>
</div>

<style>
	.aboutContainer {
		margin-top: 75px;
		width: 95%;
		min-height: 800px;
		height: fit-content;
		min-height: 75vh;
		display: grid;
        gap: 1%;
		grid-template-columns: 40% 60%;
		grid-template-areas:
			'photo resume'
			'short resume'
			'short resume'
			'short resume';
            margin-bottom: 40px;
	}


	@media screen and (max-width: 900px) {
		.aboutContainer {
			grid-template-columns: 35% 65%;
			grid-template-areas:
				'photo short'
				'photo short'
				'resume resume';
		}
        @media (max-width: 740px) {		
        .aboutContainer {
        grid-template-columns: repeat(3, 1fr);
			grid-template-areas: '. photo .'
				'short short short'
				'resume resume resume';
        row-gap: 2.5%;

        }
        .aboutContainer > div:first-of-type > img {
			width: 80% !important;
			height: auto;
			align-self: center;
			aspect-ratio: 0.75;
		}
    }
		
		.aboutContainer > div:first-of-type {
			align-items: center;
		}
	}

	.resume {
		grid-area: resume;
		width: 100%;
		display: flex;
		justify-content: flex-end;
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
		aspect-ratio: .75;
	}
	.aboutContainer > div:last-of-type {
		grid-area: short;
		max-width: 95%;
		text-align: center;
	}
</style>
