<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
      default: '@username'
    },
    link: {
      type: String,
      required: false,
    },
  },
}
</script>

<template>
  <div class="flex justify-center items-center ml-4">
    <span class="flex justify-center item-center">
      <slot />
    </span>
    <span class="ml-0.5">
      <div v-if="link">
        <a v-bind:href="link" style="border: none;" target="_blank">
          {{text}}
        </a>
      </div>
      <div v-else>
        {{text}}
      </div>
    </span>
  </div>
</template>
