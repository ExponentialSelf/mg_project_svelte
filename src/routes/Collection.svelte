<script lang="ts">
    import { onMount } from "svelte";
    import type { DataStructre } from "../dto";
    import { Secrets } from "../secrets";
    import ProductCard from "../components/ProductCard.svelte";

    export let id: string;
    $: {
        console.log(id);
    }

    let data: DataStructre[] = [];

    onMount(async () => {
        if (id) {
            try {
                const response = await fetch(
                    `http://${Secrets.DOMAIN_LINK}/db/collection`,
                    {
                        method: "POST",
                        headers: {
                            "Content-Type": "application/json",
                        },
                        body: JSON.stringify({ queryValue: id }),
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

{#if id}
    <ul class="product-grid">
        {#each data as product}
            <ProductCard {product} />
        {:else}
            <div>There is no products found</div>
        {/each}
    </ul>
{:else}
    <div>No products</div>
{/if}

<style>
    div {
        color: black;
    }

    .product-grid{
        display:grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        gap: 12px;
    }
</style>
