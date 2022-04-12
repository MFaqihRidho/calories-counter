<script setup>
import Layout from "../components/Layout.vue";
import meal from "../components/mini components/meal.vue";
import primaryButton from "../components/mini components/primaryButton.vue";
import nutritionTable from "../components/mini components/nutritionTable.vue";
</script>

<template>
  <Layout title="Dashborad">
    <div class="w-full md:py-10 py-5 h-full">
      <div
        class="flex flex-col md:flex-row w-full h-full gap-10 justify-between"
      >
        <div class="w-full flex flex-col gap-5">
          <h1 class="text-xl font-semibold">Your Calories</h1>
          <div class="flex lg:flex-row flex-col items-center">
            <div class="w-1/2 h-64 rotate-180 relative">
              <div
                class="
                  w-full
                  h-[10%]
                  absolute
                  md:rounded-r
                  rounded-b
                  bg-primary
                "
              ></div>
              <div
                class="
                  py-10
                  rotate-180
                  flex flex-col
                  items-center
                  justify-center
                "
              >
                <p>Goal 1000 Cal</p>
                <p>
                  <span class="text-4xl font-bold">{{}}</span>
                  Cal
                </p>
              </div>
            </div>
            <nutritionTable
              firstNutrition="Proteins"
              firstAmount="10"
              firstUnit="gr"
              secondNutrition="Carbs"
              secondAmount="10"
              secondUnit="gr"
              thirdNutrition="Fat"
              thirdAmount="10"
              thirdUnit="gr"
              fourthNutrition="Fat"
              fourthAmount="10"
              fourthUnit="gr"
            ></nutritionTable>
          </div>
        </div>

        <div class="w-full flex flex-col gap-5">
          <h1 class="text-xl font-semibold">Your Meals</h1>
          <div class="flex w-full flex-col gap-3">
            <meal
              v-for="item in data"
              :key="item.name"
              :title="item.name"
              :image="item.photo"
              :portion="`${item.serving} ${item.servingUnit}`"
              :calorie="parseInt(item.calorie)"
              :haveDelete="true"
              :idMeal="item.id"
              @deleteMeal="deleteMeal"
            ></meal>
          </div>
          <primaryButton title="clear"></primaryButton>
        </div>
      </div></div
  ></Layout>
</template>

<script>
export default {
  data() {
    return {
      data: JSON.parse(localStorage.getItem("common meals")),
    };
  },
  methods: {
    deleteMeal(id) {
      // const lastData = JSON.parse(localStorage.getItem("common meals"));
      // const dataALl = lastData.filter((data) => data.id !== id);
      // localStorage.setItem("common meals", JSON.stringify(dataALl));
      console.log(this.data.map((a) => a.calorie.reduce((a, b) => a + b)));
    },
  },
};
</script>
