
<script>
	import SkillsCard from './comoponents/skillsCard.svelte';
	let screenWidth = 0;
	
</script>

<svelte:window bind:innerWidth={screenWidth}   />

<div class="welcome">
	<h1>Welcome,</h1>
	<h2>& Thanks for stopping by.</h2>
	<p>
		I'm Kyle, an intermediate full-stack developer located in Ontario. Over the course of my career,
		I have gained extensive experience working on diverse projects involving various aspects of web
		development. This includes working on both front-end and back-end components, as well as
		handling full-stack projects encompassing the entire development process. I have had the
		opportunity to contribute my skills and expertise to a wide range of websites, enabling me to
		tackle different challenges and adapt to the unique requirements of each project.
		<br /><br />
		I enjoy working with state-of-the-art technologies to design interfaces that are both visually appealing
		and user-friendly, while providing top-notch performance and an enjoyable user experience.
	</p>
</div>
<div class="cta">
	<!-- <div>
		<h3>A little bit about me</h3>
		<p>
			You can find some of my skills, past educational experiences and general information about me <a
				href="/projects">Here</a
			>.
		</p>
	</div>
	<div>
		<h3>Some of my work</h3>
		<p>You can find some of my past projects <a href="/projects">Here</a>.</p>
	</div> -->

<div class='skillsContainer'>
	<SkillsCard title='Software Development' content='As an experienced software developer, I have a strong foundation in both functional and object-oriented programming paradigms. I am proficient in multiple programming languages, including Java, Python, C#, JavaScript, and Go. This diverse skill set enables me to approach software development from different perspectives and choose the most suitable approach for each project. '/>
	<SkillsCard title='Web Development' content="I possess a proficient skill set in both front-end and back-end development, encompassing a wide range of technologies. These include HTML, CSS, JavaScript, jQuery, React, Node.js, and ASP.NET, among others. With expertise in these frameworks and languages, I am capable of seamlessly bridging the gap between the user interface and server-side functionalities."/>
	<SkillsCard title='Database Management' content="I possess comprehensive expertise in both SQL and NoSQL databases, having successfully worked with a range of platforms including MYSQL, SQLServer, MongoDB, Firebase, and DB2. My experience spans designing and constructing databases from scratch, as well as executing efficient ETL processes to handle data within these databases."/>
	{#if screenWidth > 1850}
	<SkillsCard extra='true' />
	{/if}
	<SkillsCard title='UX/UI Design' content='With a keen eye for design and user experience, I create intuitive and visually appealing interfaces. Leveraging industry-standard tools like Figma, Adobe XD, and Illustrator, I craft wireframes, prototypes, and pixel-perfect designs. Guided by user-centered principles, I ensure seamless interactions and captivating experiences across platforms and devices. ' />
	{#if screenWidth > 1850}
	<SkillsCard extra='true' />
	{/if}
</div>

</div>

<style>
	.welcome {
		margin: 5% 0 0 7.5%;
		width: clamp(230px, 90%, 1200px);
		height: clamp(300px, 70%, 500px);
		display: flex;
		flex-direction: column;
		align-self: flex-start;
	}
	h1 {
		font-size: clamp(36pt, 3.25em, 48pt);
		font-family: 'Permanent Marker', cursive;
		align-self: center;
	}
	h2 {
		font-size: 1.2em;
		margin-left: 5%;
		margin-top: 1%;
		font-family: 'Indie Flower', cursive;
		align-self: center;
	}

	.welcome > p {
		font-size: calc(16px + (18 - 16) * (100vw - 320px) / (1080 - 320));
		margin-top: calc(5px + (10 - 5) * (100vw - 320px) / (1080 - 320));
		width: clamp(200px, 85%, 800px);
		border-left: 3px solid white;
		padding: 10px 10px 10px 20px;
		align-self: flex-end;
	}

	.cta {
		height: 30%;
		width: 100%;
		display: flex;
		align-items: center;
		flex-direction: column;
		justify-content: space-around;
		padding:1em;
		flex-grow:2;
		
	}



	.skillsContainer
 {
width:100%;
height: auto;
min-width:240px;
display: flex;
max-width: 1400px;
flex-wrap: wrap;
row-gap: 5%;
justify-content: space-around;
align-items: flex-start;
}

	



/* 	.cta > div {
		background-color: rgba(192, 9, 9, 0.05);
		border-radius: 10px;
		border: 1px solid #f3f3f3;
		height: clamp(100px, 65%, 400px);
		width: clamp(100px, 40%, 400px);
		min-width: 100px;
		min-height: 100px;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
		text-align: center;
	}
	.cta > div > h3 {
		font-size: calc(11px + (20 - 11) * (100vw - 320px) / (1080 - 320));
		font-weight: bold;
		padding: 4pt;
		text-underline-offset: 8px;
	}
	.cta > div > p {
		font-size: calc(9px + (14 - 9) * (100vw - 320px) / (1080 - 320));
		align-self: center;
		justify-self: center;
		padding: 5pt;       
	}

	.cta > div > h3::after {
		content: '';
		border-bottom: 1px solid white;
		width: 100%;
		height: 1px;
	}
	.cta > div > a {
		font-size: calc(12px + (14 - 12) * (100vw - 320px) / (1080 - 320));
		align-self: flex-end;
		margin-right: 5%;
	} */


</style>
