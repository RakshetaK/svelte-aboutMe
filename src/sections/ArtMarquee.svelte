<script>
    import {fade} from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let visible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const showCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                visible = true;
            } 
        });
    };

    const removeCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                visible = false;
            } 
        });
    };
</script>

<div class="title-class" out:fade><hi class = "title">MY ART GALLERY</hi></div>
          
<div>
    <Scroller layout="left">
        {#snippet sticky()}
            
            <div>
                
                {#if visible}
                    <div class="marquee-wrapper" in:fade
                        out:fade>
                        <div class="marquee">
                            <img src="portraits/IMG_2709.jpg" alt="">
                            <img src="portraits/IMG_9074.jpg" alt="">
                            <img src="portraits/IMG_3644.jpg" alt="">
                            <img src="portraits/IMG_3549.jpg" alt="">
                            <img src="portraits/IMG_3860.jpg" alt="">
                            <img src="portraits/IMG_8186.jpg" alt="">
                            <img src="portraits/IMG_2709.jpg" alt="">
                            <img src="portraits/IMG_9074.jpg" alt="">
                            <img src="portraits/IMG_3644.jpg" alt="">
                            <img src="portraits/IMG_3549.jpg" alt="">
                            <img src="portraits/IMG_3860.jpg" alt="">
                            <img src="portraits/IMG_8186.jpg" alt="">
                            
                        </div>
                    </div>
                {/if}
                
               
            </div>
        {/snippet}

        {#snippet scrolly()}
           
            <ObservedArticleText callback={showCallback} {options}>
                <strong>Here are some of my art pieces!</strong>
            </ObservedArticleText>

            
        {/snippet}
    </Scroller>
</div>

<style>
    .marquee-wrapper{
        overflow: hidden;
        padding: 8vh;
        z-index: 1;
    }
    .marquee{
        display: flex;
        width: 500%;
        flex-direction: row;
        gap: 1%;
        /* border: 2px solid white; */
        animation: scroll-left 120s linear infinite;
    }
    .marquee img{
        /* aspect-ratio: 3.2/5; */
        height: 60vh;
        box-shadow: 0px 15px 60px -17px rgba(255, 147, 46, 0.9);
        border: 4px solid black;
        filter: brightness(0.7);
    
    }
    @keyframes scroll-left {
        0%{
            transform: translateX(0%);
        }
        100%{
            transform: translateX(-50%);
        }
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
       
    }
    strong{
        font-size: 1.5vw;
        z-index: 2;
    }
</style>
