<script setup lang="ts">
import { nouns, actions } from '@/assets/words/words';
import { ref } from 'vue';

const svgRef = ref<HTMLElement | null>(null);
let noun = ref();
let action = ref();

function setNewCombi(event?: Event) {
    noun.value = nouns[Math.round(Math.random() * (nouns.length -1))];
    action.value = actions[Math.round(Math.random() * (actions.length - 1))];
    if (event && svgRef.value !== null) {
        svgRef.value.classList.add("turnAnimation");
        //@ts-expect-error compiler is unsure if svgRef.value is still null when this is called
        setTimeout( () => svgRef.value.classList.remove("turnAnimation"), 500);
    }
}

setNewCombi();

</script>

<template>
    <div class="content">
        <h1>Imagine:</h1>
        <h1><span class="gold">{{ noun }}</span>  <span>{{ action }}</span></h1>
        <button id="refreshButton" :onClick="setNewCombi">
            <svg ref="svgRef" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="49" height="30"><path d="M5.46257 4.43262C7.21556 2.91688 9.5007 2 12 2C17.5228 2 22 6.47715 22 12C22 14.1361 21.3302 16.1158 20.1892 17.7406L17 12H20C20 7.58172 16.4183 4 12 4C9.84982 4 7.89777 4.84827 6.46023 6.22842L5.46257 4.43262ZM18.5374 19.5674C16.7844 21.0831 14.4993 22 12 22C6.47715 22 2 17.5228 2 12C2 9.86386 2.66979 7.88416 3.8108 6.25944L7 12H4C4 16.4183 7.58172 20 12 20C14.1502 20 16.1022 19.1517 17.5398 17.7716L18.5374 19.5674Z" fill="rgba(248,248,248,1)"></path></svg>
        </button>
    </div>
</template>

<style scoped>
h1 {
    font-weight: 500;
    font-size: 2.6rem;
    top: -10px;
    margin: 1.5rem;
    text-align: center;
}

h3 {
    font-size: 1.2rem;
}

#refreshButton{
    margin-top: 3rem;
}

#refreshButton:hover svg{
    fill: var(--green);
}

.turnAnimation {
    animation: refreshAnimatinon .5s 1 linear;
}

@keyframes refreshAnimatinon {
    0% {
        transform: rotateZ(0deg);
    }
    100% {
        transform: rotateZ(180deg);
    }
}

</style>
