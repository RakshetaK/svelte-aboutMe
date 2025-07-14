<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h1 class="title">
                ABOUT ME
            </h1>
           <div class="profile-img"></div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>Hi, I'm Raksheta Kulkarni!<br>I am a rising sophomore at USC majoring in Computer Engineering and Computer Science.</strong>
            </ArticleText>

            <ArticleText>
                <strong>I love working with computer vision and hope to work with robots in the future!</strong>
            </ArticleText>

            
        {/snippet}
    </Scroller>
</div>

<style>

    .title{
        margin: 0;
        font-size: 8.5vw;
        text-shadow: 0px 4px 10px rgba(249, 139, 65, 0.867);
        
    }
    .profile-img{
        background-image: linear-gradient(rgba(22, 1, 1, 0.608), rgba(0, 0, 0, 0.4)), url('IMG_9030.jpg');
        position: relative;
        background-size:cover;
        background-position: center;
        background-repeat: no-repeat;
        display: block;
        aspect-ratio: 6/5;
        width: 25vw;
        height: 30vw;
        left: 8%;
        z-index: 2;
        box-shadow: 0px 15px 77px -17px rgba(255, 147, 46, 0.9);
        border: black;
    }
    strong{
        font-size: 1.5vw;
    }
</style>
