<script>
    import Logo from "$lib/images/svelte-logo.svg";
</script>

<header>
    <img width="64" height="64" src={Logo} alt="logo" class="logo" />
    <ul>
        <li>Home</li>
        <li>About Us</li>
    </ul>
</header>

<style>
    header {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        background-color: #e29531;
        color: black;
        min-height: 64px;
        padding: 1em;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
    }

    img {
        position: fixed;
        top: 6px;
        left: 6px;
    }

    ul {
        display: flex;
        align-items: center;
        justify-content: space-between;
        justify-self: center;
        margin-left: auto;
        margin-right: auto;
        gap: 1em;
        padding: 1em;
    }

    ul li {
        font-family: sans-serif;
        font-weight: bold;
    }
</style>
