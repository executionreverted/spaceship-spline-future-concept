<script>
    import Header from "./Header.svelte";
    import "./styles.css";
</script>

<div class="app">
    <Header />
    <main>
        <slot />
    </main>
    <footer>
        <p>FUTURE &copy;</p>
    </footer>
</div>

<style>
    .app {
        background-color: #343434;
    }

    footer {
        z-index: -2;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: flex-start;
        background-color: #e29531;
        color: black;
        padding: 1em;
        gap: 1em;
        font-family: sans-serif;
        height: 48px;
        max-height: 48px;
    }
</style>
