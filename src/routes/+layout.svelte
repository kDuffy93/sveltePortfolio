<script>
    import Header from '../components/global/header.svelte'
    import Footer from '../components/global/footer.svelte'
</script>
    
<Header/>
<main>
    <slot></slot>
</main>
<Footer/>
    
<style>
    main{
        width:100%;
        min-height: 75%;
        
        max-height: fit-content;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
    }
</style>