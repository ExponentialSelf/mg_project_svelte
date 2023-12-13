<script lang="ts">
  import svelteLogo from "./assets/svelte.svg";
  import viteLogo from "/vite.svg";
  import Counter from "./lib/Counter.svelte";
  import { Router, Link, Route } from "svelte-routing";
    import Search from "./routes/Search.svelte";
    import Home from "./routes/Home.svelte";
    import Navbar from "./components/Navbar.svelte";
    import Footer from "./components/Footer.svelte";
    import Collection from "./routes/Collection.svelte";
</script>

<Router>
  <Navbar/>
  <div>
    <Route path="/search" >
      <Search/>
    </Route>
    <Route path="/">
      <Home />  
    </Route>
    <Route path="/collection/:id" let:params>
      <Collection id={params.id} />
    </Route>
  </div>
  <Footer />
</Router>
