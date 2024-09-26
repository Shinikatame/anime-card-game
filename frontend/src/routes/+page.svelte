<script>
    import { onMount } from "svelte"

    let data = []

    const query = `
        query {
            Page (page: 1, perPage: 50) {
                pageInfo {
                    total
                    currentPage
                    lastPage
                    hasNextPage
                }

                characters {    
                    id
                    name {
                        first
                        middle
                        last
                        full
                        userPreferred
                    }
                    image {
                        medium
                        large
                    }
                    description
                    gender
                    age
                    dateOfBirth {
                        year
                        month
                        day
                    }
                    bloodType
                    favourites
                }
            }
        }
    `

    const options = {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
            'Accept': 'application/json',
        },
        body: JSON.stringify({
            query: query,
            variables: {
                id: 15125
            }
        })
    }

    async function fetchData() {
        try {
            const response = await fetch('https://graphql.anilist.co', options)
            data = await response.json()

            console.log(data)
        } catch (error) {
            console.error("Erro ao buscar dados:", error)
        }
    }

    onMount(() => {
        fetchData()
    })
</script>

<template>
    HELLO EVERYONE
</template>

    <!-- <div>
    {#if data.length > 0}
      <ul>
        {#each data as item}
          <li>{item.name}</li>
        {/each}
      </ul>
    {:else}
      <p>Carregando dados...</p>
    {/if}
  </div> -->