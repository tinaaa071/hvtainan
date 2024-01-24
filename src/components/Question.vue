<template>
    <div class="mb-6">
        <h3 class="mb-2 md:text-lg">{{ id }}. {{ title }}</h3>
        <LikertScale v-if="showLikertScale" />
        <slot name="other"></slot>
    </div>
</template>

<script>
export default {
    props: {
        id: Number,
        title: String,
        showLikertScale: Boolean,
  }
};
</script>