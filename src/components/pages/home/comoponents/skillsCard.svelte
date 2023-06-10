<script>
    import { onMount } from "svelte";
    export let title = 'Default Title';
    export let content = '';
    export let extra = false;
    export let author = '';
    let titleWords = title.split(" ");

   let fullscreenIframeToggle = () => {

   }

</script>
{#if extra}
<div class="extra">
    <p>{content}</p>
    <p>{author}</p>
</div>
{:else}
<div class="skill">
    <div>
        <i></i>
        <div>
             {#each titleWords as word, i}
             {#if i % 2 == 0} 
        <h3 class='first'>{word}</h3>

             {:else}
        <h3 class='second'>{word}</h3>

             {/if}
        {/each}
        </div>
       
    </div>
    <pre><p>{content}</p></pre>
</div>
{/if}
<style>

.extra{
    min-width: 200px;
    min-height: 200px;
    max-width:275px;
    max-height: 250px;
        background-color:black;
align-self: center;
display: flex;
flex-direction: column;
justify-content: space-evenly;
text-align: center;
}

.extra>p:first-of-type{
    width: 90%;
    margin-left: 5%;
    font-size: 26px;
    line-height: 28px;
font-family: 'Dancing Script', cursive;



}
.extra>p:last-of-type{
width:fit-content;
align-self: flex-end;
margin-right: 5%;
font-family: 'caveat', cursive;
font-size:larger;
}
.extra>p:last-of-type::before{
margin-left: 5px;
content: '\2014  ';
}

.extra>p:first-of-type::before{
    content: '\201C';
margin-right: .33ch;
font-size: 34px;

}
.extra>p:first-of-type::after{
    content: "\201D";
    position:absolute;
font-size: 34px;
height: fit-content

}


.skill {
		min-width: 310px;
		min-height:50px;
        height: 100%;
        max-height: 450px;
		border: 1px dashed white;
		border-radius: 10px;
        display: flex;
        flex-direction:column;
        justify-content: space-around;
        flex-basis:  clamp(250px ,45%, 450px);
        background-color:black;
        gap:7.5%;
        margin-bottom: 25px;
	}

    .skill>div{
        display: flex;
    }
    .skill>div>i{
        min-width:20%;
    }
.skill>div>div{
    display: flex; 
    flex-direction: column;
    align-items: flex-start;
    width: 100%;
}
    div>h3{ 
        padding: 1% 0;
        margin-top: 2.5%;
        text-align: center;
        font-size: calc(32px + (42 - 32) * (100vw - 320px) / (1080 - 320));
        font-family: 'Cherry Bomb One', cursive;
    flex-basis: 100%;

     }

    div>h3:last-of-type{ 
margin-left: 40px;        margin-top: -5%;
    }

     pre{
        white-space: pre-wrap; 
        margin-left: 4%;
        overflow:visible;
        width: 92%;
        min-height: 65%;
        /*font-size: calc(12px + (14 - 12) * (100vw - 320px) / (1080 - 320));*/
        height: clamp(120px, 75%, 240px);
        min-height: 100px;
        align-self: center;        
        display: flex;
flex-direction: column;
justify-content: center;
min-height:  calc((15px + (18 - 15) * (100vw - 320px) / (1080 - 320))*12);

     }
     pre>p{
        padding: .5% 0 .5% 0;
        padding-left:5%;
        border-left: 1px solid rgb(255, 255, 255, 0.3);
		font-size: calc(19px + (21 - 19) * (100vw - 320px) / (1080 - 320));

margin-left: 1%;
text-align: center;
min-width: 28ch;
padding-right:10px;
color: #e6e6e6;

font-family: 'Nanum Pen Script', cursive;

     }
     pre::before{
        content: '<h2>';
            display: block;
        padding-left:0;
        color: #599ad1;
        font-family: Consolas,monaco,monospace; 
        font-size: 14px;
        
    }    
     pre::after{
        content: '<h2>';
            display: block;
        padding-left:0;
        margin: 0 0 2.5%  0;
        color: #599ad1;
        font-family: Consolas,monaco,monospace; 
        font-size: 14px;
        
    }
     
    @media (max-width: 800px) {
    .skill{
        flex-basis:  clamp(250px, 45%, 425px)
        
    }
}
@media (max-width: 675px) {
    .skill{
        flex-basis:  clamp(250px, 85%, 425px)   ; 
        margin-bottom: 5%;
    }
    .skill:last-of-type{
        margin-bottom: 0;
    }
} @media (max-width: 515px) {
    .skill{
        flex-basis:  clamp(250px, 95%, 425px)   ; 
    }
}
</style>