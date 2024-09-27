<script>
// @ts-nocheck

    import ImagemCard from './ImagemCard.svelte'; 

    export let characters = []; 
</script>

<div class="grid">
    {#each characters as character (character.id)} <!-- Adicionando uma chave para otimização -->
        <ImagemCard
            imageSrc={character.image.large}  
            name={character.name.full}        
        />
    {/each}
</div>

<style>
    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); 
        gap: 16px; 
        margin-top: 20px;
    }
</style>
