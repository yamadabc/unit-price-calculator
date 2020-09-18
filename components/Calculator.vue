<template>
    <section>
        <v-form ref="form">
            <v-row>
                <v-col md='8'>
                    <v-text-field v-model="data.price" label="価格" @input='calculate(data.price,area)' required>
                    </v-text-field>
                </v-col>
                <v-col md='4'>
                    <p>万円</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col md='8'>
                    <v-text-field v-model="area" label="延床面積" @input='calculate(data.price,area)' required>
                    </v-text-field>
                </v-col>
                <v-col md='4'>
                    <p>㎡</p>
                </v-col>
            </v-row>
            <v-row>
                <v-col md='8'>
                    <v-text-field v-model="data.unitPrice" label="坪単価" @input='calculatePrice(area,data.unitPrice)'>
                    </v-text-field>
                </v-col>
                <v-col md='4'>
                    <p>万円</p>
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
            calculatePrice(area, unitPrice) {
                this.data.price = Math.round((area / 3.30578) * unitPrice);
            },
            clear() {
                this.$refs.form.reset()
                this.data.unitPrice = ''
                this.data.price = ''
            },
        }
    })
</script>
<style>
    .button {
        margin-top: 0.8rem;
    }
</style>