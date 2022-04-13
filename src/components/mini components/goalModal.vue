<template>
  <div
    class="
      fixed
      top-0
      bottom-0
      left-0
      right-0
      z-50
      flex-col
      items-center
      justify-center
      w-screen
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
        items-center
        justify-start
        w-[80%]
        gap-4
        px-5
        pt-5
        pb-10
        shadow-xl
        rounded-xl
        h-fit
        dark:bg-black
        bg-white
        relative
        dark:shadow-gray-200 dark:shadow-md
      "
    >
      <button
        v-on:click="closeModal"
        class="absolute pr-10 top-2 w-10 h-10 right-2 border-primary border-2"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-10 w-10 dark:fill-gray-200 fill-black"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fillRule="evenodd"
            d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
            clipRule="evenodd"
          />
        </svg>
      </button>
      <h1 class="text-2xl font-semibold self-center">Set Your Goal</h1>
      <div class="flex flex-col max-w-full gap-1">
        <label class="text-xl dark:text-gray-200 text-gray-800" for="Age"
          >Your Age</label
        >
        <input
          v-on:change="age = $event.target.value"
          :value="age"
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
      <div class="flex max-w-full flex-col gap-1">
        <label class="text-xl dark:text-gray-200 text-gray-800" for="Weight"
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
      <div class="flex max-w-full flex-col gap-1">
        <label class="text-xl dark:text-gray-200 text-gray-800" for="Height"
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
      <div class="flex max-w-full flex-col gap-1">
        <label class="text-xl dark:text-gray-200 text-gray-800" for="activity"
          >Your Activity</label
        >
        <select
          class="
            w-full
            h-10
            px-5
            dark:bg-black
            bg-white
            outline-none
            appearance-none
            focus:border-primary
            dark:bg-bg_dark
            focus:outline-none
            active:outline-none
            border-2 border-primary
            text-xl
            py-1
            rounded
            bg-transparent
            text-gray-800
            dark:text-gray-200
          "
          name="activity"
          id=""
        >
          <option class="text-sm md:text-lg" value="Sedentary">
            Sedentary(Office Job)
          </option>
          <option class="text-sm md:text-lg" value="Lightly">
            Lightly Exercise (1-2 days/week)
          </option>
          <option class="text-sm md:text-lg" value="Moderate">
            Moderate Exercise (3-5 days/week)
          </option>
          <option class="text-sm md:text-lg" value="Heavy">
            Heavy Exercise (6-7 days/week)
          </option>
          <option class="text-sm md:text-lg" value="Athlete">
            Athlete 2x per day
          </option>
        </select>
      </div>
      <div class="flex max-w-full flex-col gap-1">
        <label class="text-xl dark:text-gray-200 text-gray-800" for="Goal"
          >Your Goal</label
        >
        <select
          class="
            w-full
            h-10
            px-5
            dark:bg-black
            bg-white
            outline-none
            appearance-none
            focus:border-primary
            dark:bg-bg_dark
            focus:outline-none
            active:outline-none
            border-2 border-primary
            text-xl
            py-1
            rounded
            bg-transparent
            text-gray-800
            dark:text-gray-200
          "
          name="Goal"
          id=""
        >
          <option class="text-sm md:text-lg" value="Cutting">Cutting</option>
          <option class="text-sm md:text-lg" value="Bulking">Bulking</option>
          <option class="text-sm md:text-lg" value="Maintain">Maintain</option>
        </select>
      </div>
      <button
        v-on:click="submitGoal"
        class="
          text-gray-800
          px-5
          py-1
          rounded
          bg-primary
          text-2xl
          font-semibold
        "
      >
        Set Goal
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { age: 0 };
  },
  props: ["showModal", "closeModal"],
  methods: {
    submitGoal() {
      console.log(this.age);
    },
  },
};
</script>