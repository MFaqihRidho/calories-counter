<script setup>
import Layout from '../components/Layout.vue';
import meal from '../components/mini components/meal.vue';
</script>

<template>
  <Layout title="Dashborad">
    <div class="w-full md:py-10 py-5 h-full">
      <div class="flex flex-col md:flex-row w-full h-full gap-10 justify-between">
        <div class="w-full flex flex-col gap-5">
          <h1 class="text-xl font-semibold">Your Calories Today</h1>
          <div class="flex lg:flex-row flex-col items-center">
            <div class="w-1/2 text-gray-800 h-64 rotate-180 relative">
              <div class="w-full h-[10%] absolute rounded bg-primary"></div>
              <div class="py-10 rotate-180 flex flex-col items-center justify-center">
                <p>Goal 1000 Cal</p>
                <p>
                  <span class="text-4xl font-bold">100</span> Cal
                </p>
              </div>
            </div>
            <div
              class="w-full rounded h-[80%] px-10 text-gray-200 justify-center justify-items-center items-center bg-secondary grid grid-cols-2"
            >
              <div>
                <p class="text-xl text-gray-200">Proteins</p>
                <p class="text-xl text-gray-100">
                  <span class="text-4xl font-bold">10</span>
                  gr
                </p>
              </div>
              <div>
                <p class="text-xl text-gray-200">Carbs</p>
                <p class="text-xl text-gray-100">
                  <span class="text-4xl font-bold">10</span>
                  gr
                </p>
              </div>
              <div>
                <p class="text-xl text-gray-200">Fat</p>
                <p class="text-xl text-gray-100">
                  <span class="text-4xl font-bold">10</span>
                  gr
                </p>
              </div>
              <div>
                <p class="text-xl text-gray-200">Sugar</p>
                <p class="text-xl text-gray-100">
                  <span class="text-4xl font-bold">10</span>
                  gr
                </p>
              </div>
            </div>
          </div>
        </div>

        <div class="w-full flex flex-col gap-5">
          <h1 class="text-xl font-semibold">Your Meals</h1>
          <div class="flex w-full flex-col gap-3">
            <meal
              title="tempeh"
              portion="100gr"
              calorie="20"
              haveDelete="true"
              :onclick="deleteMeal"
            ></meal>
            <meal
              title="tempeh"
              portion="100gr"
              calorie="20"
              haveDelete="true"
              :deleteMeal="deleteMeal"
            ></meal>
          </div>
          <button
            class="bg-primary px-5 py-1 rounded font-semibold text-2xl text-white self-center"
          >Clear</button>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  methods: {
    deleteMeal() {
      console.log("meals")
    }
  }
}
</script>