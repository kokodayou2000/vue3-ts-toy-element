<script setup lang="ts">
import type {IconProps} from "./types.ts";
import { omit } from 'lodash-es'
import {computed} from 'vue'

defineOptions({
  name: "ErIcon",
  inheritAttrs: false,
})
const props = defineProps<IconProps>()
const filterProps = computed(()=> omit(props,['type','color']));
const customStyles = computed(() => ({color: props.color ? props.color : void 0}))
</script>

<template>
  <i
      class="er-icon"
      :class="[`er-icon--${props.type}`]"
      :style="customStyles"
      v-bind:"$attrs"
  >

  </i>
</template>

<style scoped>
@import "style.css";
</style>