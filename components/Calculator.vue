<template>
    <section>
        <v-form ref="form">
            <v-row>
                <v-col cols='12' md='8'>
                    <v-text-field type="text" v-model="price" label="価格" @input='calculate(price,area)' required>
                    </v-text-field>
                </v-col>
                <v-col cols=' 12' md='4'>
                    <p>万円</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col cols='12' md='8'>
                    <v-text-field type="text" v-model="area" label="延床面積" @input='calculate(price,area)' required>
                    </v-text-field>
                </v-col>
                <v-col cols='12' md='4'>
                    <p>㎡</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col cols='12' md='6'>
                    <p class='headline'>坪単価：{{ data.unitPrice }}万円</p>
                </v-col>
                <v-col cols='12' md='6'>
                    <v-btn class='button' color="light-blue lighten-5" @click='clear'>reset</v-btn>
                </v-col>
            </v-row>
        </v-form>
    </section>
</template>

<script>
    import Vue from 'vue'
    export default Vue.extend({
        data: function () {
            return {
                data: {
                    price: '',
                    area: '',
                    unitPrice: '',
                },
            }
        },
        methods: {
            calculate(price, area) {
                this.data.unitPrice = Math.round(price / (area / 3.30578));
            },
            clear() {
                this.$refs.form.reset()
                this.data.unitPrice = ''
            },
        }
    })
</script>
<style>
    .button {
        margin-top: 0.8rem;
    }
</style>