<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,300&display=swap" rel="stylesheet">
</svelte:head>

<script>
    import DialogueBoxBotw from "$lib/components/DialogueBoxBotw.svelte";
	import CharacterImgBox from "$lib/components/CharacterImgBox.svelte";
	import OptionsBotw from "$lib/components/OptionsBotw.svelte";
	import GameLoader from "$lib/components/GameLoader.svelte";

    let windowHeight, windowWidth, height, width, clientWidth, clientHeight;
    let aspectRatio = 16/9;
    
    if (aspectRatio >= 1) {
        width = aspectRatio*720;
        height = 720;
    } else {
        width = 720;
        height = aspectRatio*720;
    }

    $: scale = Math.min( 
        0.9*windowWidth / clientWidth, 
        0.9*windowHeight / clientHeight 
    );


    let chapter = {
        title: "Revali's Flap",
        nodes: [
            {
                id: 0,
                dialogue: "",
                charName: "",
                charImg: "",
                options: [],
                nextId: 1
            },
            {
                id: 1,
                dialogue: "Lorem ipsum dolor sit amet.",
                charName: "",
                charImg: "",
                options: [],
                nextId: 2
            },
            {
                id: 2,
                dialogue: `Greetings! I'm Mark, <span style="color: #3de2c8;">a Software Engineer</span>.`,
                charName: "Someone",
                charImg: "/revali_smiling.png",
                options: [],
                nextId: 3
            },
            {
                id: 3,
                dialogue: "Can I help you with anything?",
                charName: "Someone",
                charImg: "/revali_smiling.png",
                options: [
                    {
                        id: 1,
                        text: "yes",
                        nextId: 4
                    },
                    {
                        id: 2,
                        text: "no",
                        nextId: 5
                    },
                    {
                        id: 3,
                        text: "maybe",
                        nextId: 6
                    },
                ]
            },
            {
                id: 4,
                dialogue: "You chose 'yes'.",
                charName: "",
                charImg: "",
                options: [],
                nextId: 1
            },
            {
                id: 5,
                dialogue: "You chose 'no'.",
                charName: "",
                charImg: "",
                options: [],
                nextId: 1
            },
            {
                id: 6,
                dialogue: "You chose 'maybe'.",
                charName: "",
                charImg: "",
                options: [],
                nextId: 1
            }
        ]
    }



    let dialogue = "", charName = "", charImg = "", options = [];

    let currentId = 0;
    let currentNode = chapter.nodes.find((node) => node.id == currentId);
    
    $: {
        dialogue = currentNode.dialogue;
        charName = currentNode.charName;
        charImg = currentNode.charImg;
        options = currentNode.options;
    }
    

    function handleNext(event) {
        if(event.type === "click"){
            if(!dialogue && (currentNode.options.length == 0 || !currentNode.options)){
                currentNode = chapter.nodes.find((node) => node.id == currentNode.nextId);
            }
        }
        else if(event.detail.isOption) {
            currentNode = chapter.nodes.find((node) => node.id == event.detail.nextId);
        } else {
            if(currentNode.options.length == 0 || !currentNode.options) {
                currentNode = chapter.nodes.find((node) => node.id == currentNode.nextId);
            }
        }
    }

</script>

<div id="game-border" class="unreset"
    bind:clientHeight={windowHeight}
    bind:clientWidth={windowWidth}>
    <div id="game-container"
        style:width="{width}px"
        style:height="{height}px"
        bind:clientWidth={clientWidth}
        bind:clientHeight={clientHeight}
        style:transform="translate(-50%, -50%) scale({scale})"
        on:click={handleNext}
    >

        <!-- <CharacterImgBox {charImg} /> -->

        <DialogueBoxBotw on:next={handleNext} {charName} {dialogue}/>

        <OptionsBotw on:next={handleNext} {options}/>

    </div>
</div>

<!-- <GameLoader /> -->



<style>

* {
    /* all: initial; */
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

.unreset {
    all: initial;
}

#game-border {
    padding: 0;
    margin: 0;
    position: fixed;
    width: 100vw;
    height: 100%;
    background-color: white;
    animation: fadeIn 2s;
}

@keyframes fadeIn {
        0% { opacity: 0; }
        50% {opacity: 0;}
        100% { opacity: 1; }
    }

#game-container {
    cursor: pointer;
    border-radius: 40px;
    width: 1280px;
    height: 720px;
    position: relative;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    box-shadow: 0 4px 8px 0 rgba(0, 12, 82, 0.2), 0 6px 20px 0 rgba(0, 12, 80, 0.19);
    background-color: black;
    background-repeat: no-repeat;
    background-size: cover;
    background-image: url("/officebg.jpg");

}


</style>
