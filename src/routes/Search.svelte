<script lang="ts">
    import { onMount } from "svelte";
    import { Secrets } from "../secrets";
    import type { DataStructre } from "../dto";
    import ProductCard from "../components/ProductCard.svelte";
    let queryValue:string;
    let data:DataStructre[] = [];
    onMount(async () => {
        const urlParams = new URLSearchParams(window.location.search);
        const searchParamsQuery = urlParams.get("query");
        if (searchParamsQuery) {
            queryValue = searchParamsQuery;
            try {
                const response = await fetch(
                    `http://${Secrets.DOMAIN_LINK}/db/search`,
                    {
                        method: "POST",
                        headers: {
                            "Content-Type": "application/json", // Set the appropriate content type
                        },
                        body: JSON.stringify({ queryValue }),
                    }
                );

                if (response.ok) {
                    data = await response.json();
                    // Handle the response data here
                    console.log(data);
                } else {
                    console.error(
                        "Request failed with status:",
                        response.status
                    );
                }
            } catch (error) {
                console.error("Error:", error);
            }
        }
    });
</script>

{#if queryValue}
    <div class="search">
        <h2 class="search_text">
            Vous avez recherché : {queryValue}
        </h2>
        <div class="product_number">
            Produits ({data.length})
        </div>
    </div>
    <ul class="product-grid">
        {#each data as product}
          <ProductCard product={product}/>
        {:else}
           <div>There is no products found</div>
        {/each}
    </ul>
    
{:else}
    <div>No query</div>
{/if}

<style>
    div {
        color: black;
    }

    .search {
        display:flex;
        justify-content: space-between;
        padding:0 24px;
        margin-top:28px;
        margin-bottom: 14px;
    }

    .search_text{
        color: #1f6a36;
        font-size: 24px;
        line-height: 35px;
        font-weight: 700;
    }

    .product-grid{
        display:grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        gap: 12px;
    }
</style>
