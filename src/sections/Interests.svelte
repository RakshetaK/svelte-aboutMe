<script>
    import {fade} from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let links = [
        "https://www.canva.com/design/DAGsXwN3Pug/_fQZbSQCe-dQ_WGwtDl2JA/view?utm_content=DAGsXwN3Pug&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hb82a19b665",
        "https://www.canva.com/design/DAGsYKrUm-k/jo9_kf-J4oPN0mQHR5Li0w/view?utm_content=DAGsYKrUm-k&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h39b017bb22",
        "https://www.canva.com/design/DAGsYDRsEgE/_XaVrz0Cqxt_mdIgfIPbTw/view?utm_content=DAGsYDRsEgE&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h10b2aff361"
    ];
    let images = [
        "Screenshot 2025-07-14 071342.png",
        "Screenshot 2025-07-14 071427.png",
        "Screenshot 2025-07-14 085905.png"
    ]
    let index = -1;
    const options = {
        threshold: 0.5,
    };

    const showCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio > 0.5) {
                index++;
                if(index===links.length){
                    index = 0;
                }
            } 
        });
    };

   
</script>
<div class="title-class" out:fade><hi class = "title">MY INTERESTS</hi></div>
<div>
    <Scroller layout="left">
        {#snippet sticky()}
            
            <div>
                <button class="interest" style=" background-image: linear-gradient(rgba(22, 1, 1, 0.608), rgba(0, 0, 0, 0.4)),url('{images[index]}');background-size: cover;"><a href={links[index]}>CLICK HERE</a></button>
               
            </div>
        {/snippet}

        {#snippet scrolly()}
           
            <ObservedArticleText callback={showCallback} {options}>
                <strong>I find book nooks to be creative and technical (especially the ones with circuits).<br>Someday, I hope to assemble my own design!</strong>
            </ObservedArticleText>
            <ObservedArticleText callback={showCallback} {options}>
                <strong>In my free time, I love to watch thrillers, murder mysteries, or horror movies.<br> Here are some recommendations!</strong>
            </ObservedArticleText>
            <ObservedArticleText callback={showCallback} {options}>
                <strong>I have worked with 3D modeling software, such as Blender and Unity<br> While they are tedious, I am interested to explore the applications of 3D models in my free time.</strong>
            </ObservedArticleText>

            
        {/snippet}
    </Scroller>
</div>

<style>
    .interest{
        width: 30vw;
        height: 70vh;
        border: none;

    }
    a{
        color: white;
        text-decoration: none;
        font-size: 1.5vw;
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
    strong{
        font-size: 1.5vw;
        z-index: 2;
    }

</style>
