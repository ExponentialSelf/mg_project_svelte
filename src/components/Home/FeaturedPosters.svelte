<script lang="ts">
    import { Splide, SplideSlide } from "@splidejs/svelte-splide";
    import "@splidejs/svelte-splide/css";
    import poster_img from "../../assets/images/homepage-image-3-4.jpg";
    const posters = [
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
        {
            image: poster_img,
            alt: "text",
        },
    ];
</script>

<div class="decouvrez_container">
    <div class="decouvrez_text_container">
        <span class="decouvrez_text">
            Découvrez nos astuces pour passer vos commandes rapidement
        </span>
    </div>
    <div class="slide__container">
        <Splide
            options={{
                perPage: 4,
                rewind: true,
                padding: {
                    bottom: 24,
                },
                arrows: false,
                pagination: true,
            }}
        >
            {#each posters as poster}
                <SplideSlide>
                    <img
                        class="boutique_blocks_wrapper_image"
                        src={poster.image}
                        alt={poster.alt}
                    />
                </SplideSlide>
            {/each}
        </Splide>
    </div>
</div>
