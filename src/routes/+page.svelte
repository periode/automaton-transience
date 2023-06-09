<script>
    import Artwork from "../components/Artwork.svelte";

    /** @type {import('./$types').PageData} */
    export let data;
    const artworks = data.data
    artworks.sort((a, b) => a.number > b.number)
    console.log(data.data.length);
</script>

<svelte:head>
    <title>Transience | Automaton Lab</title>
</svelte:head>

<main>
    <h1>Transience</h1>
    <div>
        <div class="incipit">
            <div class="text">
            <p>
                In the spirit of education, experiment and process, students from
                HfK Bremen, HfG Karlsruhe, Bauhaus-Weimar Universität, and joined by
                NYU Berlin will present a collaborative show around the themes of
                passing by, ephemeral media, and temporary spaces.
            </p>
            <p>
                Over the course of the weekend, the public will be able to see the
                result of students discovering and exchanging about each other’s
                works and practices, creating a momentary synergetic flow in the
                Wasserspeicher.
            </p>
            <p>
                A group student exhibition at the Große Wasserspeicher in
                Berlin-Prenzlauer Berg, from 09.06 until 12.06, supported by <a
                href="http://automatonlab.xyz"
                target="_blank"
                rel="noopener noreferrer">Automaton Lab</a
                >.
            </p>
        </div>
            <img src="/poster.png" alt="a charcoal drawing representing the große wasserspeicher"/>
        </div>

    </div>
    <div class="floorplan">
        <a href="/Transience_Grundriss.pdf" download>DOWNLOAD FLOORPLAN</a>
    </div>
    <h2>Artworks</h2>
    <div class="artworks">
        {#each artworks as artwork}
            <Artwork {artwork} />
        {/each}
    </div>
</main>

<style>
    @font-face{
        font-family: 'Neue Haas Grotesk';
        src: url("/NHaasGroteskTXPro-55Rg.ttf");
        font-weight: normal;
    }

    @font-face{
        font-family: 'Neue Haas Grotesk';
        src: url("/NHaasGroteskTXPro-65Md.ttf");
        font-weight: 500;
    }

    @font-face{
        font-family: 'Neue Haas Grotesk';
        src: url("/NHaasGroteskTXPro-75Bd.ttf");
        font-weight: bold;
    }

    a, a:visited{
        color: black;
    }

    main{
        font-family: 'Neue Haas Grotesk';
        width: 50vw;
        margin: auto;
    }

    @media (max-width: 950px){
        main{
            width: 95vw;
        }
    }

    h1{
        font-size: 3em;
    }

    .incipit {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    .text, .incipit img {
        width: 45%;
    }

    @media (max-width: 950px){
        .incipit{
            flex-direction: column-reverse;
            gap: 10px
        }

        .text, .incipit img {
        width: 100%;
    }
    }

    .floorplan{
        font-weight: 500;
        font-size: 1.6em;
        text-align: center;
        margin-top: 5vh;
        margin-bottom: 10vh;
        padding-top: 2vh;
        padding-bottom: 2vh;
        border: 1px solid black;
    }

    .artworks{
        display: flex;
        gap: 5vh;
        flex-wrap: wrap;
        margin-top: 5vh;
        margin-bottom: 5vh;
    }
</style>