<script>
    export let title = 'Default Title';
    export let content = 'Default content, here is some sample text to illistrate a short paragraph';
    export let extra = false;

</script>
{#if extra}
<div class="extra">
</div>
{:else}
<div class="skill">
    <div>
        <i></i>
        <h3>{title}</h3>
    </div>
    <pre><p>{content}</p></pre>
</div>
{/if}
<style>

.extra{
    min-width: 200px;
    min-height: 200px;
		border: 1px dashed white;
        background-color:black;
align-self: center;
}

.skill {
		min-width: 100px;
		min-height:50px;
        height: max-content;
		border: 1px dashed white;
		border-radius: 10px;
        display: flex;
        flex-direction:column;
        justify-content: space-evenly;
        flex-basis:  clamp(250px ,45%, 450px);
        background-color:black;
        gap:7.5%;
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
        font-size: calc(19px + (26 - 19) * (100vw - 320px) / (1080 - 320));
     }
     pre{
        white-space: pre-wrap; 
        margin-left: 4%;
        overflow:visible;
        width: 92%;
        min-height: 65%;
        font-size: calc(12px + (14 - 12) * (100vw - 320px) / (1080 - 320));
        height: clamp(120px, 75%, 240px);
        min-height: 100px;
        align-self: center;        
        display: flex;
flex-direction: column;
justify-content: center;
min-height:  calc((15px + (18 - 15) * (100vw - 320px) / (1080 - 320))*12);

     }
     pre>p{
        padding: 2.5% 0;
        padding-left:5%;
        border-left: 1px solid rgb(255, 255, 255, 0.3);
        font-size: calc(14.75px + (17 - 14.5) * (100vw - 320px) / (1080 - 320));
margin-left: 1%;
text-align: center;
min-width: 28ch;
padding-right:10px;
color: #e6e6e6;
     }
     pre::before{
        content: '<h2>';
            display: block;
        padding-left:0;
        margin: 2.5% 0;
        color: #599ad1;

        
    }    
     pre::after{
        content: '<h2>';
            display: block;
        padding-left:0;
        margin: 2.5% 0;
        color: #599ad1;

        
    }
     
    @media (max-width: 800px) {
    .skill{
        flex-basis:  clamp(250px, 45%, 425px)
        
    }
}
    @media (max-width: 540px) {
    .skill{
        flex-basis:  clamp(250px, 85%, 425px)    
    }
}
</style>