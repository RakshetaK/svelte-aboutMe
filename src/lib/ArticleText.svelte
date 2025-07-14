<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
       <strong>{@render children()}</strong> 
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 70%;
        color: rgba(156, 88, 23, 0.9);
        padding: 20px;
        box-shadow: 0px 15px 77px -17px rgba(255, 147, 46, 0.9);
    }
</style>
