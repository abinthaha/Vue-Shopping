<template>
    <div class="user-detail-row">
        <label for="">{{type}}</label>
        <span>{{value}}</span>
        <button @click="resetValue">Reset</button>
    </div>
</template>

<script>
export default {
    name: 'UserDetails',
    props: {
        value: {
            // type: Number,
            default: 20
        },
        type: {
            type: String,
            default: 'Abin'
        }
    },
    methods: {
        resetValue() {
            this.value = 'New name'
            this.$emit('resetValue', this.value)
        }
    }
}
</script>

<style lang="scss" scoped>
    .user-detail-row {
        label {
            display: inline-block;
            width: 30%;
            max-width: 200px;
        }
    }
</style>
