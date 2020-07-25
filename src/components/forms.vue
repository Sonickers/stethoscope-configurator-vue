<template>
    <div class="pt-2">
        <brand :brands="brands"/>
        <model :models="models"/>
        <color :colors="colors"/>
    </div>
</template>

<script>
import brand from './forms/brand'
import model from './forms/model'
import color from './forms/color'

export default {
    components: {
        brand,
        model,
        color
    },
    data() {
        return {
            brands: [
                { id: 1, name: "Littmann", cost: 150 },
                { id: 2, name: "Spirit Medical", cost: 130 },
                { id: 3, name: "NaturFarm", cost: 95 },
                { id: 4, name: "Luxamed", cost: 75 }
            ],
            models: [
                { id: 1, name: "Intern", cost: 40 },
                { id: 2, name: "Cardio", cost: 60 },
                { id: 3, name: "Pediatric", cost: 30 },
                { id: 4, name: "Anesthesia", cost: 25 }
            ],
            colors: [
                { id: 1, name: "Summer Sun", color: "is-warning" },
                { id: 2, name: "Neon Pink", color: "is-danger" },
                { id: 3, name: "Blueberry Blue", color: "is-link" },
                { id: 4, name: "Deep Black", color: "is-black" },
                { id: 5, name: "Cactus Green", color: "is-success" }
            ]
        }
    }
}
</script>