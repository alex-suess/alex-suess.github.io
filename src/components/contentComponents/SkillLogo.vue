<script setup>
const props = defineProps({
  logoFileName: String,
  altText: String,
  imageLink: String,
});


</script>

<template>
  <a :href="props.imageLink"><img :alt="props.altText" class="transition-all ease-in-out h-4 ml-2 saturate-0 hover:saturate-100 cursor-pointer"
                                            :src="'../../../' + props.logoFileName + '.png'"/></a>
</template>