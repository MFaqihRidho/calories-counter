<template>
  <div
    class="
      container
      fixed
      top-0
      bottom-0
      left-0
      right-0
      z-50
      flex-col
      items-center
      justify-center
      w-full
      max-w-[800px]
      h-screen
      py-10
      mx-auto
      bg-black/40
      flex
    "
    v-bind:class="{ flex: showModal, hidden: !showModal }"
  >
    <div
      class="
        flex flex-col
        items-start
        justify-start
        w-[50%]
        gap-4
        px-10
        py-5
        shadow-xl
        rounded-xl
        h-[75%]
        dark:bg-black
        bg-white
      "
    >
      <h1 class="text-2xl font-semibold self-center">Set Your Goal</h1>
      <div>
        <label class="text-xl mb-3 dark:text-gray-200 text-gray-800" for="Age"
          >Your Age</label
        >
        <input
          class="
            border-2 border-primary
            text-xl
            px-4
            py-1
            rounded
            bg-transparent
            focus:outline-none
            text-gray-800
            dark:text-gray-200
          "
          type="number"
          name="Age"
          placeholder="Your Age"
        />
      </div>
      <div>
        <label
          class="text-xl mb-3 dark:text-gray-200 text-gray-800"
          for="Weight"
          >Your Weight</label
        >
        <input
          class="
            border-2 border-primary
            text-xl
            px-4
            py-1
            rounded
            bg-transparent
            focus:outline-none
            text-gray-800
            dark:text-gray-200
          "
          type="number"
          name="Weight"
          placeholder="Your Weight"
        />
      </div>
      <div>
        <label
          class="text-xl mb-3 dark:text-gray-200 text-gray-800"
          for="Height"
          >Your Height</label
        >
        <input
          class="
            border-2 border-primary
            text-xl
            px-4
            py-1
            rounded
            bg-transparent
            focus:outline-none
            text-gray-800
            dark:text-gray-200
          "
          type="number"
          name="Height"
          placeholder="your Height"
        />
      </div>
      <div>
        <label for="activity">Your Activity</label>
        <select name="activity" id="">
          <option value="Sedentary">Sedentary</option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["showModal"],
  methods: {
    submitGoal() {
      console.log(goal);
    },
  },
};
</script>