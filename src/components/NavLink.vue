<template>
  <li class="list-none">
    <a
      class="block px-4 py-2"
      :class="{
        'text-white  ': !isActive,
        'text-blue-600 font-semibold ': isActive,
        'text-gray-100 pointer-events-none opacity-50': isDisabled,
      }"
      aria-current="page"
      :href="url"
      :disabled="isDisabled"
      :aria-disabled="isDisabled"
    >
      {{ text }}
    </a>
  </li>
</template>

<script setup>
defineProps({
  url: {
    type: String,
    required: false,
    default: "",
  },
  text: {
    type: String,
    required: true,
  },
  isActive: {
    type: Boolean,
    required: false,
    default: false,
  },
  isDisabled: {
    type: Boolean,
    required: false,
    default: false,
  },
});
</script>
