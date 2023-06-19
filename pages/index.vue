<template>
    <div class="w-auto select-none
        flex items-center justify-center relative text-center">
        <div>
            <img src="../assets/images/juce.png"
                 ref="logo"
                 class="pointer-events-none mx-4 mt-32 h-32 xl:h-40 2xl:h-48"
                 :style="{
                maskImage: logoGradient,
            }"
                 alt="helloo image is a fuck"/>
            <div class="grid grid-cols-3 content-evenly pt-16"
                 :style="{
            maskImage: logoGradient,
            }">
                <a href="https://github.com/jucedev">
                    <Icon name="line-md:github-loop" class="w-16 h-16 xl:w-20 xl:h-20 2xl:w-24 2xl:h-24 m-4 box-content place-content-center text-zinc-300"/>
                </a>
                <a href="https://discordapp.com/users/184704561175330826">
                    <Icon name="line-md:discord" class="w-16 h-16 xl:w-20 xl:h-20 2xl:w-24 2xl:h-24 m-4 box-content place-content-center text-zinc-300"/>
                </a>
                <a href="http://twitter.com/jucedev">
                    <Icon name="line-md:twitter" class="w-16 h-16 xl:w-20 xl:h-20 2xl:w-24 2xl:h-24 m-4 box-content place-content-center text-zinc-300"/>
                </a>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import {useMouse} from "@vueuse/core";

const {x, y} = useMouse();
const logo = ref<HTMLElement>();
const logoGradient = computed(() => {
    let rect = logo.value?.getBoundingClientRect();
    const xPos = x.value - (rect?.left ?? 0);
    const yPos = y.value - (rect?.top ?? 0);

    return `radial-gradient(circle at ${xPos}px ${yPos}px, black 25%, transparent 100%)`
})
</script>