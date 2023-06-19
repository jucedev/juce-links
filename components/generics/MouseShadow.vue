<script setup lang="ts">
import {useMouse, useWindowSize } from '@vueuse/core';

const { x, y } = useMouse();
const { width, height } = useWindowSize();

const dx = computed(() => Math.abs(x.value - width.value / 2));
const dy = computed(() => Math.abs(y.value - height.value / 2));

const distance = computed(() => Math.sqrt(dx.value ** 2 + dy.value ** 2));

const size = computed(() => Math.max(300 - distance.value / 3, 200));

const opacity = computed(() => Math.min(Math.max(size.value / 300, 0.7), 1)
);
</script>

<template>
    <div
        class="absolute overflow-hidden bg-cyan-600/30 rounded-full -translate-x-1/2 -translate-y-1/2
            pointer-events-none blur-3xl"
        :style="{
            left: `${x}px`,
            top: `${y}px`,
            width: `${size}px`,
            height: `${size}px`,
        }"
    />
</template>