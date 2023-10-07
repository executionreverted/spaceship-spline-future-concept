<script>
    import { onMount } from "svelte";
    import { Application } from "@splinetool/runtime";
    let loading = true;
    let model;
    let app;
    export let setLoading = () => {};

    let url = "https://prod.spline.design/j-kom7YLENbO9BwZ/scene.splinecode";
    // import spline scene
    const onClick = async (e) => {
        const x = e.x;
        const y = e.y;
        const centerX = window.innerWidth / 2;
        const centerY = window.innerHeight / 2;
        const mousePosX = x - centerX;
        const mousePosY = centerY - y;
        // I couldn't get it work as expected, without setTimeout.
        // I think its about spline, doing something in background and async variable updates cause spawn objects on old points.
    };

    onMount(() => {
        const canvas = document.getElementById("canvas3d");
        if (!canvas) return;
        app = new Application(canvas);
        if (!app) return;
        app.load(url).then((splineScene) => {
            model = splineScene;
            setTimeout(() => {
                loading = false;
                setLoading();
            }, 100);
        });

        document.addEventListener("click", onClick);
        return () => {
            document.removeEventListener("click", onClick);
        };
    });
</script>

<canvas class={loading ? `hidden` : ""} id="canvas3d" />

<style>
    #canvas3d {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        z-index: 10;
    }

    .hidden {
        opacity: 0;
    }

    p {
        min-height: 14px;
        color: darkslateblue;
        text-align: center;
    }
</style>
