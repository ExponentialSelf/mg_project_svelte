<script lang="ts">
    import { Router, Link, Route } from "svelte-routing";
    const navigations = [
        {
            name: "MG Promotion",
            link: "mg-promotion",
        },
        {
            name: "Produits Frais",
            link: "produits-frais",
        },
        {
            name: "Epicerie & Boissons",
            link: "epicerie-boissons",
        },
        {
            name: "Patisserie et Traiteur",
            link: "patisserie-traiteur",
        },
        {
            name: "Nettoyage et entretien",
            link: "nettoyage-entretien",
        },
    ];
</script>

<nav>
    <div class="nav_bar_container">
        <svg
            width="22px"
            height="22px"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
        >
            <path
                d="M20 7L4 7"
                stroke="#1C274C"
                stroke-width="1.5"
                stroke-linecap="round"
            />
            <path
                d="M20 12L4 12"
                stroke="#1C274C"
                stroke-width="1.5"
                stroke-linecap="round"
            />
            <path
                d="M20 17L4 17"
                stroke="#1C274C"
                stroke-width="1.5"
                stroke-linecap="round"
            />
        </svg>

        <ul class="navigation_list">
            {#each navigations as nav}
                <li class="nav_bar_elemnt">
                    <a href="/collection/{nav.link}" class="nav_bar_link" > {nav.name} </a>
                </li>
            {/each}
        </ul>
    </div>
</nav>

<style>
    .nav_bar_container {
        border-top: 1px solid black;
    }
    .navigation_list {
        list-style-type: none;
        display: flex;
    }

    .navigation_list li {
        border-right: 1px solid black;
        padding: 0 8px;
    }

    .navigation_list li:last-of-type {
        border: none;
    }
</style>
