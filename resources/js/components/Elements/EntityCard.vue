<template>
  <li class="relative cursor-pointer">
    <div
      :class="`group hover:shadow-md aspect-w-1 aspect-h-1 block w-full overflow-hidden rounded-lg  ${
        checked && 'ring-1 ring-blue-500'
      }`"
    >
      <slot />
    </div>
    <p
      class="pointer-events-none mt-2 block truncate text-sm font-medium text-gray-900 dark:text-gray-50"
    >
      {{ file.name }}
    </p>
    <p class="pointer-events-none block text-sm font-medium text-gray-500">{{ file.size }}</p>
    <CheckCircleIcon
      :class="[!checked ? 'invisible' : '', 'absolute h-5 w-5 text-blue-500 top-1 right-1']"
      aria-hidden="true"
    />
  </li>
</template>

<script>
import { CheckCircleIcon } from '@heroicons/vue/solid'
import { DocumentIcon } from '@heroicons/vue/outline'
import Sidebar from '@/components/Sidebar'

export default {
  name: 'EntityCard',
  components: {
    CheckCircleIcon,
    DocumentIcon,
    Sidebar,
  },
  props: ['file', 'checked'],
}
</script>

<style scoped></style>
