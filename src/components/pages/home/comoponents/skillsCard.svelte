<script>
    export let title = 'Default Title';
    export let content = 'Default content, here is some sample text to illistrate a short paragraph';
</script>

<div class="skill">
    <div>
        <i></i>
        <h3>{title}</h3>
    </div>
    <pre><p>{content}</p></pre>
</div>

<style>
    .skill {
		min-width: 100px;
		min-height:max-content;
        height: 60%;
		border: 1px dashed white;
		border-radius: 10px;
        display: flex;
        flex-direction:column;
        justify-content: space-evenly;
        flex-basis:  clamp(200px ,45%, 700px);
	}

    .skill>div{
        display: flex;
    }
    .skill>div>i{
        min-width:20%;
    }

    div>h3{ 
        height: calc((14px + (22 - 14) * (100vw - 320px) / (1080 - 320))*2);
        padding: 1% 0;
        margin-top: 2.5%;
        text-align: center;
        font-size: calc(14px + (24 - 14) * (100vw - 320px) / (1080 - 320));
     }
     pre{
        white-space: pre-wrap; 
        margin-left: 4%;
        overflow:visible;
        width: 92%;
        min-height: 65%;
        font-size: calc(8px + (12 - 8) * (100vw - 320px) / (1080 - 320));
        height: clamp(120px, 75%, 240px);
        min-height: 100px;
        align-self: center;        
        display: flex;
flex-direction: column;
justify-content: center;
min-height:  calc((10px + (15 - 10) * (100vw - 320px) / (1080 - 320))*10);

     }
     pre>p{
        padding: 2.5% 0;
        padding-left:7.5%;
        border-left: 1px solid white;
        font-size: calc(10px + (15 - 10) * (100vw - 320px) / (1080 - 320));
margin-left: 1%;
text-align: center;
min-width: 30ch;
     }
     pre::before{
        content: '<h2>';
            display: block;
        padding-left:0;
        margin: 2.5% 0;

        
    }    
     pre::after{
        content: '<h2>';
            display: block;
        padding-left:0;
        margin: 2.5% 0;

        
    }
     
</style>