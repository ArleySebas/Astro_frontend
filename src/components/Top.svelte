<script context="module">
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
    class="top"
    role="presentation"
    on:mouseover={() =>
        showing(".top_cover", ".top_img", ".top_p", {
            cardinal: "left",
            value: "0",
        })}
    on:mouseout={() =>
        hidding(".top_cover", ".top_img", ".top_p", {
            cardinal: "left",
            value: "-100%",
        })}
    on:focus={() =>
        showing(".top_cover", ".top_img", ".top_p", {
            cardinal: "left",
            value: "0",
        })}
    on:blur={() =>
        hidding(".top_cover", ".top_img", ".top_p", {
            cardinal: "left",
            value: "-100%",
        })}
>
    <img
        class="top_img"
        src="hat.png"
        alt="Sombrero de grado"
    />
    <img class="top_img" src="birrete.png" alt="Birrete">
    <div class="top_cover">
        <ul class="top_cover_ul">
            <li>Ingeniero biomédico con grados próximos</li>
            <li>Certificación en análisis de datos con Python</li>
            <li>Bachiller</li>
        </ul>
    </div>
    <p class="top_p">Estudios</p>
</section>

<style>
    .top {
        grid-area: top;

        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 1fr 1fr;
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

    .top_img {
        grid-column: 1 / -1;
        grid-row: 1 / 2;

        filter: drop-shadow(0 0 0.3rem white);

        border-radius: 8%;
        padding: 1%;
        width: clamp(4rem, 15vw + 0.5rem, 20rem);

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    .top_img:nth-child(2) {
        z-index: 997;

        animation: grade_animation 0.5s linear infinite alternate;
    }

    .top_cover {
        position: absolute;
        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: flex;
        justify-content: center;
        align-items: center;

        opacity: 0;

        width: 100%;
        height: 100%;
        left: -100%;

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
            left 0.3s ease;
        z-index: 999;
    }

    .top_cover_ul {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-direction: column;

        padding: 7%;

        font-size: x-large;
    }

    .top_p {
        grid-column: 1 / -1;
        grid-row: 2 / 3;

        text-align: left;

        font-weight: 900;
        font-size: clamp(1rem, 5vw + 0.5rem, 5rem);
        color: #effcfb;

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    @keyframes grade_animation {
        0% {
            transform: translateX(-2%);
        }
        100% {
            transform: translate(2%);
        }
    }

    @media (max-width: 800px) {
        .top {
            grid-area: top;

            display: grid;
            grid-template-columns: 1fr 1fr;
            grid-template-rows: 1fr;
        }
        .top_img {
            grid-column: 1 / 2;
            grid-row: 1 / -1;
        }
        .top_p {
            grid-column: 2 / 3;
            grid-row: 1 / -1;
        }
    }
</style>
