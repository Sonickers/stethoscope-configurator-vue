<template>
    <div class="container">
        <div class="notification">
            <header-title/>
            <nav class="level">
                <div class="level-left">
                    <div class="level-item">
                        <forms/>
                    </div>
                </div>

                <div class="level-right">
                    <result-product/>
                </div>
            </nav>
        </div>
    </div>
</template>

<script>
import headerTitle from './header-title'
import forms from './forms'
import resultProduct from './result-product'

export default {
    components: {
        headerTitle,
        forms,
        resultProduct
  }
}
</script>