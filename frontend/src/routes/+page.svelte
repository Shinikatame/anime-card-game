<script>
    import ImagemListona from '../lib/components/ImagemListona.svelte'; 
    let characters = []; 
    let showImages = false; 

    async function fetchData() {
        const query = `
            query {
                Page(page: 1, perPage: 50) {
                    characters {
                        id
                        name {
                            full
                        }
                        image {
                            large
                        }
                    }
                }
            }
        `;

        const response = await fetch('https://graphql.anilist.co', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Accept': 'application/json',
            },
            body: JSON.stringify({ query })
        });

        const data = await response.json();
        characters = data.data.Page.characters; 
        showImages = true; 
    }
</script>


{#if !showImages} 
    <div class="button-container">
        <button class="fetch-button" on:click={fetchData}>Clique Aqui</button>
    </div>
{/if}


{#if showImages} 
    <ImagemListona {characters} /> 
{/if}

<style>
    .button-container {
        display: flex;                
        justify-content: center;      
        align-items: center;          
        height: 100vh;                
    }

    .fetch-button {
        background-color: #6a0dad; 
        color: white;              
        border: none;              
        border-radius: 8px;       
        padding: 12px 24px;      
        font-size: 18px;          
        cursor: pointer;          
        transition: background-color 0.3s; 
    }

    .fetch-button:hover {
        background-color: #5a0ca6;
    }
</style>
