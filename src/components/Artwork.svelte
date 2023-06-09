<script>
    export let artwork
</script>

<div class="artwork">
    <div class="header">
        <div class="number">{artwork.number}</div>
        <div class="title">{artwork.title}</div>
    </div>
    <div class="name">{artwork.name}</div>
    <div class={artwork.number === "08" ? `ascii description` :`description`}>
        {artwork.description}
    </div>
    <div class="footer">
        <div class="bio">{artwork.bio}</div>
    </div>
</div>

<style>
    .ascii{
        font-family: mono;
    }
    .description{
        white-space: pre-wrap;

    }
    .artwork {
        width: 45%;
    }
    @media (min-width:320px) {
        .artwork{
            width: 95vw;
        }
    }
    .artwork{
        display: flex;
        flex-direction: column;
        gap: 1vh;
    }
    .header{
        display: flex;
        gap: 10px;
    }
    .header, .name{
        font-size: 1.2em;
    }
    .title{
        font-weight: bolder;
    }
    .bio{
        color: #666
    }
</style>