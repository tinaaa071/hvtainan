<template>
    <div class="relative flex items-center">
          <div class="flex items-center h-6">
            <input id="comments" aria-describedby="comments-description" name="comments" type="checkbox" class="w-4 h-4 text-indigo-600 border-gray-300 rounded focus:ring-indigo-600" />
          </div>
          <div class="ml-3 text-sm leading-6">
            <label for="comments" class="font-medium text-gray-900 md:text-lg">{{ label }}</label>
          </div>
        </div>
</template>  

<script>
export default {
  props: {
    label: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      checked: false,
    };
  },
  methods: {
    handleCheckboxChange() {
      this.$emit('checkbox-change', { label: this.label, checked: this.checked });
    },
  },
};
</script>