<script>
    let { title } = $props();
</script>

<div class="title-card">
   
    <h1>{title}</h1>
        
   
</div>

<style>
    .title-card {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 80vh;
        background-image: url('Screenshot\ 2025-07-06\ 204936.png');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        opacity: 0.7;
    }

   
    @keyframes fade-in {
        0%{
            opacity: 0;
        }
        100%{
            opacity: 1;
        }
    }
  
    h1{
        color: black;
        font-family: "Lucida Handwriting", cursive;
        font-size: 13.5vw;
        animation: fade-in 3s linear;
        text-shadow: 0 4px 10px rgba(241, 3, 3, 0.867);
    }
    

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

       
    }
</style>
