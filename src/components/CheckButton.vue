<template>
    <div class="relative flex items-center">
          <div class="flex items-center h-6">
            <input id="comments" aria-describedby="comments-description" name="comments" type="checkbox" class="w-4 h-4 text-indigo-600 border-gray-300 rounded focus:ring-indigo-600" />
          </div>
          <div class="ml-3 text-sm leading-6">
            <label for="comments" class="flex font-medium text-gray-900 md:text-lg whitespace-nowrap">{{ label }}</label>
          </div>
          <div class="ml-3">
            <input 
            v-if="showInput"
            class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" :placeholder="placeholder" />
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
    showInput: {
        type: Boolean,
        default: false
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