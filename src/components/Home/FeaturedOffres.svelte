<script>
    import { Splide, SplideSlide } from "@splidejs/svelte-splide";
    import foutas from '../../assets/images/foutas.jpg'
    import summer from '../../assets/images/summer.png'
    import "@splidejs/svelte-splide/css";
    const offres = [
        {
            image:foutas,
            title:'Voir les offres',
        },
        {
            image:foutas,
            title:'Voir les offres'
        },
        {
            image:foutas,
            title:'Voir les offres'
        },
        {
            image:foutas,
            title:'Voir les offres'
        },
        {
            image:foutas,
            title:'Voir les offres'
        },
        
    ]
</script>

<div class="summer__section">
    <div class="summer__banner">
        <img src={summer} alt="summer">
    </div>
    <div class="summer__section__bg">
        <div class="summer__section__content">
            <div class="product__slider__container">
                <Splide
                options={{
                    perPage: 4,
                    rewind: true,
                    padding: {
                        bottom: 24,
                    },
                    arrows: false,
                    pagination: false,
                }}
            >
                {#each offres as offre}
                    <SplideSlide>
                        <div class="product__wrapper">
                            <img src={offre.image} alt="">
                            <div class="product__link">{offre.title}</div>
                        </div>
                    </SplideSlide>
                {/each}
            </Splide>
            </div>
        </div>
    </div>
</div>