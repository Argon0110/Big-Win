<script setup>
import { computed, ref } from 'vue';

const Step = ref(0);

const SpamTonMsg = computed(() => {
    switch (Step.value) {
        case 0: return "YOU ACTUALLY CLICKED THE [HYPERLINK BLOCKED]??O.0 HOW BRAVE OF YOU MY MAIN MAN [it was pretty stupid ngl].";
        case 1: return "WELL DON'T YOU THINK YOU GOT SCAMMED [my little twinkle star], CAUSE I HAVE THE PERFECT [kromer value 0.%>1000] FOR YOUOuU!!!";
        case 2: return "YOUR WONDEFRUL [pR#AIz33] PRIZE IS A FULLY COVERED, NO GIFT TAX, NO RECEIT, MONEY BACK GUARANTEED [no insurance coverage], FUNfunFuNFUn...";
        case 3: return "TRIP TO ###[a lovely village in Uganda]###[HYPERLINK BLOCKED]";
        case 4: return "THE CERN!! [INSERT APPLAUSE SFX AND CONFETTI GIF PNG]";
        case 5: return "THANK YOU KIND [idiot] FOR CHOOSING [prude and edo] YOUR GOOD OL' PAL SPAMTONIO [HYPERLINK BLOCKED] [CHEER CHEER APPLAUSE] FOR YOUR BUSINESS [no refound and change appliable]";
    }
})
</script>

<template>
    <main>
        <img class="ImageHero" v-if="Step < 4" src="/src/assets/Shop.png" />
        <img class="ImageHero" v-else-if="Step === 4" src="/src/assets/CERN.jpg" />
        <img class="ImageHero gif" v-else src="/src/assets/BYE.gif"/>
        <p id="SpamTonText" :class="Step >= 5 ? 'lastStep' : ''">
            {{ SpamTonMsg }}
        </p>
        <button v-if="Step < 5" @click="Step++" id="nextBtn">{{ Step === 2 ? "REDEEM!!!" : "PROCEED"}}</button>
    </main>
</template>

<style scoped>
@font-face {
    font-family: SPAMTON;
    src: url('/src/assets/big-shot.ttf');
}

main {
    font-family: SPAMTON;
    position: relative;
    background-color: black;
    color: white;
}

.ImageHero {
    width: 100%;
    height: 235px;
    object-fit: cover;
}

.ImageHero.gif {
    object-fit: contain;
    height: 300px;
}

#SpamTonText {
    display: flex;
    align-items: center;
    height: calc(100% - 300px);
    padding: 0 15px;
}

#SpamTonText.lastStep {
    height: calc(100% - 300px);
}

button {
    all: unset;
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
    padding: 10px 25px 8px;
    font-size: 20px;
    background-color: black;
    color: white;
    border: 3px solid white;
    border-radius: 25px;
    cursor: pointer;
}
</style>
