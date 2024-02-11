<script>
    export let arr;
    export let name;
</script>

<div class="container">
    <div class="img-c flex place-content-center">
        <div class="x grid grid-cols-2 md:grid-cols-3 gap-4">
            {#each arr as _, i }
                <div>
                <img src="{`/assets/${name}/${name} (${i + 1}).jpg`}" alt='garden' />
                 </div>
            {/each}
            
        </div>
    </div>
</div>
<style>
    .img-c {
        margin: 0 auto;
    }
    img {
        border-radius: 1rem;
        max-width: 95%;
    }
    
    .x {
        display: grid;
        grid-template-columns: repeat(1, minmax(250px,1fr));
        place-content: center;
        padding-right: 1rem;
        padding-top: 1rem;
        transition: all .3s ease;
        gap: 1rem;
    }
    .x div:hover {
        opacity: 80%;
    }

    @media (min-width: 768px) {
        .x {
            grid-template-columns: repeat(3, minmax(250px,1fr));
        }
        .x div img {
            width: 1000px;
        }
    }
</style>