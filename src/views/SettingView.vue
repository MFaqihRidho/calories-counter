<script setup>
import Layout from "../components/Layout.vue";
</script>

<template>
  <Layout title="Settings">
    <div className="flex items-center w-full gap-3">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        className="w-8 h-8"
        viewBox="0 0 24 24"
        stroke="currentColor"
        strokeWidth="{2}"
        fill="none"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"
        />
      </svg>
      <div className="relative w-full">
        <p className="text-lg font-semibold">Select Theme</p>
        <select
          v-on:change="changeTheme($event.target.value)"
          className="w-full h-10 px-5 text-center bg-white border-2 border-gray-400 rounded-lg outline-none appearance-none focus:border-main dark:bg-bg_dark focus:outline-none active:outline-none"
          name=""
          id=""
          value="{theme}"
        >
          <option value="dark">dark</option>
          <option value="light">light</option>
        </select>
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  methods: {
    changeTheme(e) {
      console.log(e);
    },
  },
};
</script>