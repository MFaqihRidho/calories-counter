<template>
    <div class="ml-20 px-5 py-10 text-gray-700 dark:text-gray-300">
        <h1 class="text-3xl font-semibold">{{ title }}</h1>
        <slot />
    </div>
</template>

<script>
export default {
    props: {
        title: String
    }
}
</script>