<script>
    import Card from "./card.svelte";
</script>


<div class="grid">
    <Card/>
</div>

<style>
    .grid{
        display:grid;
        grid-template-columns:1fr 1fr 1fr;
        gap:30px;
    }
</style>