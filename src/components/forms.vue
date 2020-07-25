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
                { id: 1, name: "Littmann" },
                { id: 2, name: "Spirit Medical" },
                { id: 3, name: "NaturFarm" },
                { id: 4, name: "Luxamed" }
            ],
            models: [
                { id: 1, name: "Intern" },
                { id: 2, name: "Cardio" },
                { id: 3, name: "Pediatric" },
                { id: 4, name: "Anesthesia" }
            ],
            colors: [
                { id: 1, name: "Deep Black", color: "is-black" },
                { id: 2, name: "Raspberry Pink", color: "is-danger" },
                { id: 3, name: "Sky Blue", color: "is-info" },
                { id: 4, name: "Cactus Green", color: "is-success" }
            ]
        }
    }
}
</script>