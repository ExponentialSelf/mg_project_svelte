<script lang="ts">
    import type { DataStructre } from "../dto";

    export let product: DataStructre;
    const featured_image = product?.featured_image;
</script>

<li class="product-card">
    <img src={featured_image} alt="product {product.title}" />
    <div class="card_content">
        <div class="card_title">
            {product?.title}
        </div>
        <div class="card_weight">
            {product?.weight ? product.weight : "No weight"}
        </div>
        <div class="card_price">
            {product?.price} TND
        </div>
    </div>
</li>

<style>
    .product-card {
        display: flex;
        flex-direction: column;
        gap: 12px;
        border: 1px solid #ccc;
        padding: 10px;
        border-radius: 8px;
    }

    .product-card img {
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
    }

    .card_content {
        display: flex;
        flex-direction: column;
        gap: 8px;
    }

    .card_title {
        width: 100%;
        font-weight: bold;
        font-size: 15px;
        text-align: center;
        text-transform: inherit;
        height: 55px;
        position: relative;
        padding-top: 10px;
        color: #222 !important;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
    }

    .card_weight {
        width: 100%;
        font-size: 13px;
        text-align: center;
        text-transform: inherit;
        height: 20px;
        position: relative;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
    }

    .card_price {
        color: #1f6a36 !important;
        font-size: 17px !important;
        font-weight: bold !important;
        text-align: center;
    }

    div {
        color: black;
    }
</style>
