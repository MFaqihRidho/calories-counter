<template>
    <div class="md:ml-20 px-5 md:px-10 py-5 mb-10 md:py-10 text-gray-700 dark:text-gray-300">
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