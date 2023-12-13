<script lang="ts">
    import Logo from "../../assets/images/mg-logo-02.png";
    import user_icon from "../../assets/images/user-128-128.png";
    let searchValue = "";

    const handleKeyPress = (event:any) => {
        if (event.key === "Enter") {
            handleSearch();
        }
    }

    const handleSearch = () => {
        if (searchValue) {
            window.location.href = `/search?query=${searchValue}`
        }
        
    }
</script>

<div class="nav_bar_search_wrapper">
    <div class="nav_bar_img">
        <img src={Logo} alt="mg logo" />
    </div>
    <div class="nav_bar_search_container">
        <div class="nav_bar_search_connection_container">
            <div>
                <input
                    bind:value={searchValue}
                    on:keydown={handleKeyPress}
                    class="search_bar"
                    type="text"
                    placeholder="Rechercher sur Mg"
                />
            </div>
            <div>
                <button class="connection_button_container">
                    <img
                        class="connection_button_user_icon"
                        src={user_icon}
                        alt=""
                    /> <span> Connexion </span>
                </button>
            </div>
        </div>
    </div>
</div>
