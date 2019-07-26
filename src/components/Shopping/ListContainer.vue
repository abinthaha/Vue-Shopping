<template>
    <section class="list-wrapper">
        <ul class="item-list">
            <li class="list-item" v-for="(item, index) in listData" v-bind:key="index">
                <figure v-bind:class="{ available: item.isAvailable }">
                    <img v-bind:src="item.imgUrl" alt="">
                    <figcaption>
                        <span class="name">{{ item.name }}</span>
                        <span class="type">{{ item.type }}</span>
                    </figcaption>
                </figure>
                
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    name: 'ListContainer',
    props: ['listData']
}
</script>

<style lang="scss" scoped>
    .list-wrapper {
        .item-list {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;

            .list-item {
                border: 1px solid #ddd;
                border-radius: 5px;
                margin: 10px;

                figure {
                    position: relative;
                    &:after {
                        content: '';
                        position: absolute;
                        right: 0;
                        top: 0;
                        display: inline-block;
                        width: 30px;
                        height: 30px;
                        background-image: url('https://cdn0.iconfinder.com/data/icons/large-glossy-icons/512/No.png');
                        background-repeat: no-repeat;
                        background-position: center;
                        background-size: contain;
                    }
                    &.available {
                        &:after {
                            background-image: url('https://www.clearlakearea.com/wp-content/uploads/2019/02/available-now-png-6.png')
                        }
                    }

                    img {
                        display: inline-block;
                        width: 300px;
                        height: 300px;
                    }

                    figcaption {
                        display: flex;
                        text-transform: capitalize;
                        align-items: center;
                        margin-top: 10px;
                        border-top: 1px solid #ddd;
                        padding-top: 10px;

                        .name {
                            font-size: 20px;
                            font-weight: bold;
                            flex: 1;
                        }
                    }
                }
            }
        }
    }
</style>

