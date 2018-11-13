<template>
    <div class="math">
        <div class="berekening">
            <h3>Kwadraat</h3>
            {{ getal * getal }}
        </div>
        <div class="berekening">
            <h3>Wortel</h3>
            {{ Math.sqrt(getal).toFixed(2) }}
        </div>
        <div class="berekening">
            <h3>Logaritme</h3>
            {{ Math.log(getal).toFixed(2) }}
        </div>
        <div class="berekening">
            <h3>Priemgetal?</h3>
            {{ isPriemgetal ? "Ja" : "Nee" }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    props: {
        getal: Number
    },
    computed: {
        isPriemgetal() {
            for(var i = 2; i < this.getal; i++) {
                if(this.getal % i === 0) {
                    return false;
                }
            }
            return this.getal > 1;
        }
    }
}
</script>

<style scoped>
    .math {
        width: 150px;
        height: 150px;
        background-color: gold;
        box-shadow: 1px 1px 3px black;
        display: grid;
        grid-template-rows: 50% 50%;
        grid-template-columns: 50% 50%;
    }
    .berekening {
        border: 1px solid black;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column wrap;
    }

    .berekening h3 {
        font-size: 10px;
        text-align: center;
    }
</style>
