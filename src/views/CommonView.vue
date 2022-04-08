<script setup>
import axios from 'axios'
import Layout from '../components/Layout.vue';
import primaryButton from '../components/mini components/primaryButton.vue';
import nutritionTable from '../components/mini components/nutritionTable.vue';
</script>

<template>
    <Layout :title="$route.params.id">
        <div class="py-10 w-full">
            <div class="w-full flex md:flex-row flex-col items-center gap-5">
                <img class="w-28" :src="data?.photo?.thumb" :alt="data?.food_name" />
                <div class="lg:w-96 mb-3 md:mb-0">
                    <div class="input-group relative flex-row flex items-stretch w-full">
                        <input
                            :value="amount"
                            @input="amount = $event.target.value"
                            type="number"
                            name="amount"
                            placeholder="amount"
                            id="amount"
                            class="form-control relative flex-auto min-w-0 block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid rounded-l border-gray-300 transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-primary focus:outline-none"
                        />
                        <select
                            name="unit"
                            class="inline-block px-2 py-2.5 bg-primary text-white font-medium text-xl leading-tight shadow-md hover:bg-secondary hover:shadow-lg rounded-r focus:shadow-lg focus:outline-none focus:ring-0 active:shadow-lg transition duration-150 ease-in-out items-center"
                            id="unit"
                        >
                            <option disabled value>serving unit</option>
                            <option value="oz">oz</option>
                            <option value="g">g</option>
                        </select>
                    </div>
                </div>
                <primaryButton title="add" class="capitalize text-xl"></primaryButton>
                <nutritionTable
                    firstNutrition="Calorie"
                    :firstAmount="(data?.nf_calories * amount).toFixed(2)"
                    firstUnit="cal"
                    secondNutrition="Carbs"
                    :secondAmount="((data?.nf_total_carbohydrate * amount).toFixed(2))"
                    secondUnit="gr"
                    thirdNutrition="Protein"
                    :thirdAmount="((data?.nf_protein * amount).toFixed(2))"
                    thirdUnit="gr"
                    fourthNutrition="Fat"
                    :fourthAmount="((data?.nf_total_fat * amount).toFixed(2))"
                    fourthUnit="gr"
                ></nutritionTable>
            </div>
        </div>
    </Layout>
</template>

<script>
export default {
    data() {
        return { data: [], amount: 0 }
    },
    mounted() {
        const params = { query: `1g ${this.$route.params.id}` };
        axios.post(`https://trackapi.nutritionix.com/v2/natural/nutrients`, params, {
            headers: {
                'x-app-id': "9ff7947b",
                'x-app-key': "50c66e23b3793fd3558d8af37c07c910",
            },
        }).then((res) => {
            this.data = res.data.foods[0]
            console.log(res.data.foods[0])
        }).catch((err) => {
            console.log(err)
        })
    }
}
</script>