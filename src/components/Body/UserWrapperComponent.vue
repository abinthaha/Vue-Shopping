<template>
    <section class="content-wrapper">
        <app-user-details type="Name" :value="userName" @resetValue="userName = $event"></app-user-details>
        <app-user-details type="Age" :value="age" @resetValue="userName = $event"></app-user-details>
        <button @click="changeName">Click</button>
    </section>
</template>

<script>

import UserDetails from './UserDetailsComponent';

export default {
    name: 'UserWrapper',
    data: function() {
        return {
            userName: 'Abin Thaha',
            age: 26
        }
    },
    methods: {
        changeName: function() {
            this.userName = 'Abin Thaha Azeez';
            this.age = 20
        },
        updateValue: function() {
            this.userName = 'Something'
        }
    },
    components: {
        'app-user-details': UserDetails
    }
}
</script>

<style lang="scss" scoped>
    .content-wrapper {
        padding: 15px;
    }
</style>


