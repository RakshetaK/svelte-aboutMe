<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    
</script>
<div class="title-class"><hi class = "title">MY KWK JOURNEY</hi></div>
<div>
    <Scroller layout="right">
        {#snippet sticky()}
            
           <div class="profile-img"></div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>APP DEVELOPMENT</strong><br>
                <strong>I began my KWK journey with the app development camp in 2022, where I learned to work with Swift and XCode!</strong>
            </ArticleText>

            <ArticleText>
                <strong>WEB DEVELOPMENT</strong><br>
                <strong>In 2023, I continued my KWK journey, learning the fundamentals of frontend development. My team and I worked on a productivity, 'to-do list' based, website called "Chime In"</strong>
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
    .title-class{
        width: 100%;
        display: block;
        text-align: center;
        z-index: -10;
    }
    .title{
        margin: 0;
        font-size: 8.5vw;
        text-shadow: 0px 4px 10px rgba(255, 147, 46, 0.9);
        z-index: -10;
    }
    .profile-img{
        background-image: linear-gradient(rgba(22, 1, 1, 0.608), rgba(0, 0, 0, 0.4)), url('duck.png');
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
