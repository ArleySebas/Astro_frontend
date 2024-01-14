<script lang="ts">
    // export let parametro; así inicializo una variable que importé

    export function showing(cover, img, paragraph, direction) {
        const coverConst = document.querySelector(cover);
        const imgConst = document.querySelector(img);
        const paragraphConst = document.querySelector(paragraph);
        const directionValue = direction.value;
        const directionCardinal = direction.cardinal;

        imgConst.style.opacity = 0.1;
        paragraphConst.style.opacity = 0.1;
        coverConst.style.opacity = 1;
        coverConst.style[directionCardinal] = directionValue;
    }
    export function hidding(hide, img, paragraph, direction) {
        const coverConst = document.querySelector(hide);
        const imgConst = document.querySelector(img);
        const paragraphConst = document.querySelector(paragraph);
        const directionValue = direction.value;
        const directionCardinal = direction.cardinal;

        coverConst.style.opacity = 0;
        coverConst.style[directionCardinal] = directionValue;
        imgConst.style.opacity = 1;
        paragraphConst.style.opacity = 1;
    }
</script>

<section
    class="leftblock"
    role="presentation"
    on:mouseover={() =>
        showing(".leftblock_cover", ".leftblock_img", ".leftblock_p", {
            cardinal: "top",
            value: "0",
        })}
    on:mouseout={() =>
        hidding(".leftblock_cover", ".leftblock_img", ".leftblock_p", {
            cardinal: "top",
            value: "-100%",
        })}
    on:focus={() =>
        showing(".leftblock_cover", ".leftblock_img", ".leftblock_p", {
            cardinal: "top",
            value: "0",
        })}
    on:blur={() =>
        hidding(".leftblock_cover", ".leftblock_img", ".leftblock_p", {
            cardinal: "top",
            value: "-100%",
        })}
>
    <p class="leftblock_p">Perfil</p>
    <img
        class="leftblock_img"
        src="caricaruta_objeto_inteligente.png"
        alt="Hoja de vida"
        
    />
    <div class="leftblock_cover">
        <img
            class="leftblock_cover_img"
            src="favicon.svg"
            alt="logo de astro"
        />
    </div>
</section>

<style>
    .leftblock {
        grid-area: leftblock;

        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 1fr 1fr;
        place-items: center;
        place-content: center;

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
    .leftblock_p {
        grid-column: 1 / -1;
        grid-row: 1 / 2;
        align-self: center;
        text-align: center;

        font-weight: 900;
        font-size: clamp(1rem, 5vw + 0.5rem, 5rem);
        color: #effcfb;

        transition: opacity 0.3s ease;
        z-index: 998;
    }
    .leftblock_img {
        grid-column: 1 / -1;
        grid-row: 2 / 3;
        align-self: end;

        width: clamp(15rem, 25vw + 0.5rem, 90rem);
        height: clamp(15rem, 25vw + 0.5rem, 90rem);
        object-fit: cover;

        border-radius: 8%;
        padding: 1%;

        z-index: 1000;
        transition: all 0.3s ease;
        transition-delay: 0.3s;
    }

    .leftblock:hover .leftblock_img {
        grid-column: 1 / 2;
        grid-row: 1 / 2;
        animation: change 1s normal forwards;
    }

    .leftblock_cover {
        position: absolute;
        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: flex;
        justify-content: center;
        align-items: center;

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
    .leftblock_cover_img {
        height: 100%;
        width: 100%;
        object-fit: fill;
        z-index: 999;
    }

    @keyframes change {
        0% {
            opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }

    @media (max-width: 800px) {
        .leftblock {
            grid-area: leftblock;
  
            grid-template-columns: 1fr 1fr;
            grid-template-rows: 1fr;
        }
        .leftblock_p {
            grid-column: 1 / 2;
            grid-row: 1 / -1;
        }
        .leftblock_img {
            grid-column: 2 / 3;
            grid-row: 1 / -1;
            align-self: center;
        }
    }
</style>
