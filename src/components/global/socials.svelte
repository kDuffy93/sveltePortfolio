<script>
export let className = 'icon';
</script>

<ul class={className}>
    {#if className == 'text'}
    <li><a href="https://www.linkedin.com/in/kyle-duffy-776723100/"><img src="Assets/linkedInText.svg"/></a></li>
    <li><a href="https://github.com/kDuffy93"><img src="Assets/gitHubTextWhite.svg"/></a></li>
    <li><a href="mailto:kyleduffy83@gmail.com"><img src='Assets/email.svg'/></a></li>
    {:else}
    <li><a href="https://www.linkedin.com/in/kyle-duffy-776723100/"><img src="Assets/linkedInlogo.svg"/></a></li>
    <li><a href="https://github.com/kDuffy93"><img src="Assets/github-mark-white.svg"/></a></li>
    <li><a href="mailto:kyleduffy83@gmail.com"><img src='Assets/email.svg'/></a></li>
    {/if}
</ul>



<style>
    /* text */
.text{
    display: flex;
    justify-content: space-around;
    width: 50vw;
    margin-left: 25vw;
    }
.text>li{
   width: clamp(18.75vw, 30%, 350px);
   text-align: center;
   font-size: clamp(.95rem, 2vw, 1.4rem); 

   
}
.text>li>a{
    pointer-events: none;
    height:100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.text>li>a>img{
    color: #d1d1d1;
    pointer-events: visible;
    width: clamp(60px, 65% , 100px);
    height:auto;
    max-height: 45%;
}


/*icons*/

.icon{
    display: flex;
    justify-content: space-around;
    width: 50vw;
    margin-left: 25vw;
    margin-top:2vh;
    }
.icon>li{
   width: clamp(18.75vw, 30%, 350px);
   text-align: center;
   font-size: clamp(.95rem, 2vw, 1.4rem); 

   
}
.icon>li>a{
    pointer-events: none;
    height:100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.icon>li>a>img{
    pointer-events: visible;
    width: clamp(40px, 55% , 4.5vw);
    height: clamp(50px 6vh, 7.5vh);
padding:1vh 1vw;
}
.icon>li:nth-of-type(3)>a>img{
    scale:1.25;
}


img{
    transition: transform 0.4s ease-in-out; 
}

img:hover{
    transform: scale(1.15) !important;
}
</style>