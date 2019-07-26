<template>
    <main>
        <app-header></app-header>
        <div class="content-wrapper">
            <!-- <app-user-wrapper></app-user-wrapper> -->
            <app-shopping-wrapper></app-shopping-wrapper>
        </div>
        <app-footer></app-footer>
    </main>
</template>

<script>

import Header from './Header/HeaderComponent.vue';
import Footer from './Footer/FooterComponent.vue';
// import UserWrapper from './Body/UserWrapperComponent.vue';
import ShoppingWrapper from './Shopping/ShoppingWrapper';

export default {
    name: 'Landing',
    components: {
        'app-header': Header,
        'app-footer': Footer,
        // 'app-user-wrapper': UserWrapper,
        'app-shopping-wrapper': ShoppingWrapper
    }
}
</script>

<style scoped>
    main {
        display: flex;
        flex-direction: column;
        height: 100%;
    }
    .content-wrapper {
        flex: 1;
    }
</style>

