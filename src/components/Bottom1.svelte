<script context="module">
    import { showing, hidding } from "./Top.svelte";
</script>

<section
    class="bottom1"
    role="presentation"
    on:mouseover={() =>
        showing(".bottom1_cover", ".bottom1_img", ".bottom1_p", {
            cardinal: "top",
            value: "0",
        })}
    on:mouseout={() =>
        hidding(".bottom1_cover", ".bottom1_img", ".bottom1_p", {
            cardinal: "top",
            value: "-100%",
        })}
    on:focus={() =>
        showing(".bottom1_cover", ".bottom1_img", ".bottom1_p", {
            direction: "top",
            value: "0",
        })}
    on:blur={() =>
        hidding(".bottom1_cover", ".bottom1_img", ".bottom1_p", {
            direction: "top",
            value: "-100%",
        })}
>
    <img class="bottom1_img" src="app.png" alt="Logo de app" />
    <img class="bottom1_img" src="app_numero.png" alt="Logo de app" />
    <div class="bottom1_cover">
        <img
            src="Python_logo.png"
            alt="Python logo"
            class="bottom1_cover_img"
        />
        <img
            src="Power_BI_logo.png"
            alt="Power BI logo"
            class="bottom1_cover_img"
        />
        <img src="Excel_logo.png" alt="Excel logo" class="bottom1_cover_img" />
        <img src="Numpy_logo.png" alt="Numpy logo" class="bottom1_cover_img" />
        <img
            src="Pandas_logo.png"
            alt="Pandas logo"
            class="bottom1_cover_img"
        />
        <img
            src="Scikit_learn_logo.png"
            alt="Scikit learn logo"
            class="bottom1_cover_img"
        />
        <img
            src="Matplotlib_logo.png"
            alt="Matplotlib logo"
            class="bottom1_cover_img"
        />
        <img
            src="Postgresql_logo.png"
            alt="Postgresql logo"
            class="bottom1_cover_img"
        />
    </div>
    <p class="bottom1_p">Aplicaciones</p>
</section>

<style>
    .bottom1 {
        container-type: inline-size;
        grid-area: bottom1;

        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr;
        place-items: center;

        width: 100%;
        height: 100%;

        border-radius: 1rem;

        background-color: linear-gradient(180deg, skyblue), white;
        -webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
        border: 0.1rem;
        -webkit-box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);
        -moz-box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);
        box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);

        overflow: hidden;
        position: relative;
        z-index: 998;
    }

    .bottom1_img {
        grid-column: 1 / 2;
        grid-row: 1 / -1;

        border-radius: 8%;
        padding: 1%;
        width: clamp(4rem, 15vw + 0.5rem, 20rem);

        transition: opacity 0.3s ease;
        z-index: 998;
    }
    .bottom1_img:nth-child(2) {
        animation: app_animation 0.5s infinite alternate;
    }

    .bottom1_cover {
        position: absolute;

        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        place-items: center;
        place-content: center;

        opacity: 0;

        width: 100%;
        height: 100%;
        top: -100%;

        border-radius: 1rem;

        background-color: linear-gradient(180deg, skyblue), white;
        -webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
        border: 0.1rem;
        border-radius: 1rem;
        border-radius: 1rem solid rgba(255, 255, 255, 0.1);
        box-shadow: 0 0.8rem 3.2rem 0 rgba(0, 0, 0, 0.37);

        transition:
            opacity 0.3s ease,
            top 0.3s ease;
        z-index: 999;
    }

    .bottom1_cover_img {
        height: calc(80% + 1vw);
        width: max(70%, calc(30% + 1vw));
        object-fit: scale-down;
        z-index: 999;

        filter: drop-shadow(0 0 2rem white);
    }

    .bottom1_p {
        grid-column: 2 / 3;
        grid-row: 1 / -1;

        text-align: center;

        font-weight: 900;
        font-size: clamp(1rem, 5vw + 0.5rem, 5rem);

        color: #effcfb;
        -webkit-text-stroke: 0.1rem black; 

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    @keyframes app_animation {
        0% {
            transform: scale(1);
        }
        100% {
            transform: scale(1.1);
        }
    }

    @media (max-width: 800px) {
        .bottom1 {
            grid-area: bottom1;
        }
    }
</style>
