<template>
  <div class="flex mt-2 space-x-4">
    <CheckButton v-for="item in label" :key="item.value" :label="item.label" />
  </div>
</template>

<script>
export default {
    data() {
    return {
      label: [
        { value: '1', label: '總是' },
        { value: '2', label: '常常' },
        { value: '3', label: '有時候' },
        { value: '4', label: '不常' },
        { value: '5', label: '從未或幾乎從未' },
      ],
    };
  },
};
</script>