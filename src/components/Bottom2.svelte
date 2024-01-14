<script context="module">
    import { showing, hidding } from "./Top.svelte";

    export function redirectionIframe(redirectionPage) {
        window.location.href = redirectionPage;
    }
</script>

<section
    class="bottom2"
    role="presentation"
    on:mouseover={() =>
        showing(".bottom2_cover", ".bottom2_img_div", ".bottom2_p_div", {
            cardinal: "bottom",
            value: "0",
        })}
    on:mouseout={() =>
        hidding(".bottom2_cover", ".bottom2_img_div", ".bottom2_p_div", {
            cardinal: "bottom",
            value: "-100%",
        })}
    on:focus={() =>
        showing(".bottom2_cover", ".bottom2_img_div", ".bottom2_p_div", {
            direction: "bottom",
            value: "0",
        })}
    on:blur={() =>
        hidding(".bottom2_cover", ".bottom2_img_div", ".bottom2_p_div", {
            direction: "bottom",
            value: "-100%",
        })}
>
    <div class="bottom2_img_div">
        <img
            class="bottom2_img"
            src="whatsapp_logo_color.svg"
            alt="Logo de whatsapp que indica contacto"
        />
    </div>
    <div class="bottom2_cover">
        <img
            class="bottom2_cover_img"
            src="formulario_pagina.png"
            alt="logo de astro"
        />
    </div>
    <div class="bottom2_p_div">
        <p class="bottom2_p">Analista de datos</p>
    </div>
</section>

<style>
    .bottom2 {
        grid-area: bottom2;

        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 2fr 1fr;
        place-items: center;

        width: 100%;
        height: 100%;

        border-radius: 1rem;

        background-color: linear-gradient(180deg, skyblue), white;
        -webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
        border: 0.1rem;
        -webkit-box-shadow: 0rem 0rem 1rem 0.1rem rgba(0, 0, 0, 0.52);
        -moz-box-shadow: 0rem 0rem 1rem 0.1rem rgba(0, 0, 0, 0.52);
        box-shadow: 0rem 0rem 1rem 0.1rem rgba(0, 0, 0, 0.52);

        overflow: hidden;
        position: relative;
        z-index: 998;
    }

    .bottom2_img_div {
        grid-column: 1 / -1;
        grid-row: 1 / 2;
    }
    .bottom2_img {
        padding: 1%;
        width: clamp(15rem, 25vw + 0.5rem, 30rem);

        transition: opacity 0.3s ease;
        z-index: 998;
    }
    .bottom2_cover {
        position: absolute;
        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: flex;
        justify-content: center;
        align-items: center;

        opacity: 0;

        width: 100%;
        height: 100%;
        bottom: -100%;

        border-radius: 1rem;

        background-color: linear-gradient(180deg, skyblue), white;
        -webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
        border: 0.1rem;
        border-radius: 1rem;
        border-radius: 1rem solid rgba(255, 255, 255, 0.1);
        box-shadow: 0 0.8rem 3.2rem 0 rgba(0, 0, 0, 0.37);

        transition:
            opacity 0.4s ease,
            bottom 0.4s ease;
        z-index: 999;
    }

    .bottom2_cover_img {
        height: 100%;
        width: 100%;
        object-fit: fill;
        z-index: 999;
    }
    .bottom2_p_div {
        grid-column: 1 / -1;
        grid-row: 2 / 3;
    }
    .bottom2_p {
        text-align: center;

        font-weight: 900;
        font-size: clamp(1rem, 5vw + 0.5rem, 5rem);
        color: #effcfb;

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    @media (max-width: 800px) {
        .bottom2 {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: 1fr;
        }
        .bottom2_img_div {
            grid-column: 1 / 2;
            grid-row: 1 / -1;
        }
        .bottom2_p_div {
            grid-column: 2 / 3;
            grid-row: 1 / -1;
        }
    }
</style>
