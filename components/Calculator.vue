<template>
    <section>
        <p><input type="text" v-model="price" placeholder="価格" />万円</p>
        <p><input type="text" v-model="area" placeholder="延床面積" />㎡</p>
        <button @click='calculate(price,area)'>go!</button>
        <p>坪単価：{{ data.unitPrice }}万円</p>
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
        }
    })
</script>