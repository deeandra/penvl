<script>
	import GameScreen from "$lib/components/GameScreen.svelte";

</script>


<div class="container">
    <div class="preview">
        <GameScreen/>
    </div>
    <div class="editor">
        <textarea name="story-json" id="story-json" cols="30" rows="10">
            asdfghjkjhtre
        </textarea>
    </div>
</div>


<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    .container {
        display: flex;
        position: relative;
        height: 100vh;
        width: 100vw;
        flex-wrap: wrap;
    }

    @media (orientation: portrait) {
        .preview, .editor {
            width: 100%;
            height: 50%;
            max-height: 50%;
            /* flex-direction: column; */
        }
    }

    @media (orientation: landscape) {
        .preview, .editor {
            width: 50%;
            max-width: 50%;
            height: 100%;
            /* flex-direction: row; */
        }
    }

   
</style>