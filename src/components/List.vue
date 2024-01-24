<template>
  <h3 class="mb-4 text-2xl">{{ header }}</h3>
  <div class="mb-4">
        <h3 class="mb-2 text-lg">{{ id }}. {{ title }}</h3>
        <LikertScale />
    </div>
</template>

<script>
export default {
    props: {
        header: String,
        title: String,
    }
};
</script>