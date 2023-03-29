<template>
    <div class="conversor">
        <h2>{{ moedaA }} para {{ moedaB }}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: "ConversorDeMoeda",
    props: ["moedaA", "moedaB"],
        data(){
            return{

                moedaA_value : "",
                moedaB_value : 0,

            };
            
        },
    methods: {
        converter() {            

            let de_para = this.moedaA + "-" + this.moedaB;
            let depara = this.moedaA + this.moedaB;

            let url = "http://economia.awesomeapi.com.br/json/last/" +
                de_para
                

            fetch(url).then(res => {
                return res.json();
            })
                .then(json => {
                    let cotacao = json[depara]["bid"];
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                })
        }
    }
};
</script>

<style scoped>
.conversor {
    border-radius: 5px;
    border: solid 3px;
    margin-bottom: 10px;
    padding: 10px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
</style>