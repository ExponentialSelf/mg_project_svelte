<script>
    import bien_manger from '../../assets/images/bien-manger-cat.jpg'
    import bien_etre from '../../assets/images/bien-etre.jpg'
    import bien_soi from '../../assets/images/bien-chez-soi-cat.jpg'
    import financer from '../../assets/images/financer.jpg'
    import plaisir from '../../assets/images/plaisir.jpg'
    import consomer_responsable from '../../assets/images/consommer-responsable.jpg'
    const catalogues = [
        {
            image_url:bien_manger,
            link:''
        },
        {
            image_url:bien_etre,
            link:''
        },
        {
            image_url:bien_soi,
            link:''
        },
        {
            image_url:financer,
            link:''
        },
        {
            image_url:plaisir,
            link:''
        },
        {
            image_url:consomer_responsable,
            link:''
        },
        
    ]

</script>

<div class="catalogue_grid_container">
    {#each catalogues as catalogue}
        <a href={catalogue.link}
        ><img
            class="catalogue_grid_container_img"
            src={catalogue.image_url}
            alt=""
        /></a
    >
    {/each}
</div>
