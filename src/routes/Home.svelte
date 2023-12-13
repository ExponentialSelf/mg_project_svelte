<script>
    import Catalogue from "../components/Home/Catalogue.svelte";
    import FeaturedCTA from "../components/Home/FeaturedCTA.svelte";
    import FeaturedOffres from "../components/Home/FeaturedOffres.svelte";
    import FeaturedPosters from "../components/Home/FeaturedPosters.svelte";
    import FeaturedProducts from "../components/Home/FeaturedProducts.svelte";
</script>

<div class="home">
    <FeaturedProducts />
    <FeaturedPosters />
    <FeaturedCTA />
    <FeaturedOffres />
    <Catalogue/>
</div>

<style>
    .home {
        display: flex;
        flex-direction: column;
    }
</style>
