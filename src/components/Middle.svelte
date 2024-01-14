<script>
	import { showing, hidding } from './Top.svelte';
</script>

<section
    class="middle"
    role="presentation"
    on:mouseover={() => showing(".middle_cover", ".middle_img", ".middle_p",{cardinal:"right",value:"0"})}
    on:mouseout={() => hidding(".middle_cover", ".middle_img", ".middle_p",{cardinal:"right",value:"-100%"})}
    on:focus={() => showing(".middle_cover", ".middle_img", ".middle_p",{direction:"right",value:"0"})}
    on:blur={() => hidding(".middle_cover", ".middle_img", ".middle_p",{direction:"right",value:"-100%"})}
>
    <img
        class="middle_img"
        src="computadora.png"
        alt="Computadora creado por phatplus en Flaticon"
    />
    <div class="middle_cover">
        <div class="middle_cover_container">
            <ul class="middle_cover_ul">
                <li>Reconocimiento de patrones, tendencias y extraer información significativa.</li>
                <li>Conocimiento de técnicas de estadística y modelos predictivos.</li>
                <li>Habilidad para traducir hallazgos técnicos en términos comprensibles para personas no técnicas.</li>
                <li>Capacidad para crear informes y visualizaciones efectivas para presentar los resultados.</li>
                <li>Proactivo y curioso para explorar nuevos enfoques y técnicas de análisis de datos.</li>
                <li>Disposición para mantenerme actualizado en las últimas tendencias del campo.</li>
            </ul>
        </div>
    </div>
    <p class="middle_p">Analista <br /> de datos</p>

</section>


<style>
	.middle {
        grid-area: middle;

        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr;
        place-items: center;

        width: 100%;
        height: 100%;

        border-radius: 1rem;

        background-color: linear-gradient(180deg,skyblue), white;
		-webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
		border: 0.1rem ;
        -webkit-box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);
        -moz-box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);
        box-shadow: 0px 0px 1rem 0.1rem rgba(0, 0, 0, 0.52);

        overflow: hidden;
        position: relative;
        z-index: 998;
    }

    .middle_img {
        grid-column: 1 / 2;
        grid-row: 1 / -1;

        background-color: white;
        border-radius: 8%;
        padding: 1%;
        width: clamp(4rem, 15vw + 0.5rem, 20rem);

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    .middle_cover {
        position: absolute;
        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr;
        place-items: center;

        opacity: 0;

        width: 100%;
        height: 100%;
        right: -100%;

        border-radius: 1rem;

		background-color: linear-gradient(180deg,#d6f6f7), #42c8d1;
		-webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
		border: 0.1rem ;
		border-radius: 1rem;
        border-radius: 1rem solid rgba(255,255,255,0.1);
		box-shadow: 0 0.8rem 3.2rem 0 rgba(0,0,0,0.37);	

        transition:
            opacity 0.3s ease,
            right 0.3s ease;
        z-index: 999;
    }
    .middle_cover_container {
        grid-column: 1 / -1;
        grid-row: 1 / -1;

        display: flex;
        justify-content: center;
        align-items: center;

        width: 80%;
        height: 80%;
        
        background-color: linear-gradient(80deg,#d6f6f7), #42c8d1;
		-webkit-backdrop-filter: blur(0.1rem);
        backdrop-filter: blur(0.1rem);
		border: 0.1rem ;
		border-radius: 1rem;
        border-radius: 1rem solid rgba(255,255,255,0.1);
		box-shadow: 0 0.8rem 3.2rem 0 rgba(0,0,0,0.37);
    }
    /* .middle_cover_img {
        grid-row: 1 / -1;
        grid-column: 1 / -1;

        height: calc(50% + 1vh);
        width: calc(20% + 1vw);
        object-fit: fill;
        z-index: 999;
    } */
    .middle_cover_ul {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-direction: column;

        max-width: 90%;
        max-height: 90%;

        text-align: left;

        font-size: calc(50% + 1vw);
    }
    .middle_p {
        grid-column: 2 / 3;
        grid-row: 1 / -1;
        text-align: left;

        font-weight: 900;
        font-size: clamp(1rem, 5vw + 0.5rem, 5rem);
        color: #effcfb;

        transition: opacity 0.3s ease;
        z-index: 998;
    }

    @media (max-width: 800px){
        .middle {
            grid-area: middle;
        }
    }
</style>