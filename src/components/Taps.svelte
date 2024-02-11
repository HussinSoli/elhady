<script>
     import { createEventDispatcher } from 'svelte'
    export let taps;
    export let activeTap;

    let dispatch = createEventDispatcher()
</script>



<div class="taps">
    <ul>
        {#each taps as tap, i }
            <li on:click={() => {dispatch('tapChange', tap)}}>
                <div class:active={activeTap === tap}>{tap}</div>
            </li>
        {/each}
    </ul>
</div>


<style>
    .taps {
        border-radius: 1rem;
        padding: 2rem;
        margin-top: 1rem;
        background-color: #FFFFFF;
        width: 90%;
        margin: 0 auto;
        margin-top: 2rem;
    }

    .active {
        color: #29ab87;
        border-bottom: 2px solid #29ab87;
    }

    ul {
        display: grid;
        grid-template-columns: repeat(2, minmax(0,1fr));
        place-content: center;
        gap: 2rem;
        list-style: none;
        font-size: 1.5rem;
        font-weight: bold;
        cursor: pointer;
    }
    @media (min-width: 768px) {
        ul {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        gap: 0;
        }
    }
</style>