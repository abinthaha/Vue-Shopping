<template>
    <section class="shopping-container">
        <app-filter :filterData="getFilterData()" @filter-changed="filterData"></app-filter>
        <app-list :listData="listDataFiltered"></app-list>
    </section>
</template>

<script>

import ListContainer from './ListContainer.vue';
import FilterContainer from './FilterContainer';

export default {
    name: 'ShoppingWrapper',
    components: {
        'app-list': ListContainer,
        'app-filter': FilterContainer
    },
    data: function() {
        return {
            listData: [
                {
                    id: 1,
                    name: 'Saree',
                    type: 'fashion',
                    imgUrl: 'https://5.imimg.com/data5/NO/YA/MY-41451839/latest-fancy-saree-500x500.jpg',
                    isAvailable: true
                }, {
                    id: 2,
                    name: 'Shirt',
                    type: 'fashion',
                    imgUrl: 'https://rukminim1.flixcart.com/image/714/857/shirt/s/h/y/46-bfrybluesht02-being-fab-original-imaekjr8ymhnxznp.jpeg',
                    isAvailable: false
                }, {
                    id: 3,
                    name: 'iPhone',
                    type: 'electronics',
                    imgUrl: 'https://media.wired.com/photos/5b22c5c4b878a15e9ce80d92/master/pass/iphonex-TA.jpg',
                    isAvailable: true
                }, {
                    id: 4,
                    name: 'Apple',
                    type: 'food',
                    imgUrl: 'https://images.pexels.com/photos/39803/pexels-photo-39803.jpeg',
                    isAvailable: true
                }, {
                    id: 5,
                    name: 'Orange',
                    type: 'food',
                    imgUrl: 'https://soappotions.com/wp-content/uploads/2017/10/orange.jpg',
                    isAvailable: false
                }, {
                    id: 6,
                    name: 'Churidar',
                    type: 'fashion',
                    imgUrl: 'https://5.imimg.com/data5/UQ/IS/MY-47151525/untitled-1-recovered-500x500.jpg',
                    isAvailable: true
                }, {
                    id: 7,
                    name: 'Television',
                    type: 'electronics',
                    imgUrl: 'https://rukminim1.flixcart.com/image/704/704/jl41nrk0/television/h/8/t/thomson-24tm2490-original-imaf8bgdjb6zr4ck.jpeg',
                    isAvailable: true
                }, {
                    id: 8,
                    name: 'Ginger',
                    type: 'food',
                    imgUrl: 'https://www.planetorganic.com/images/products/large/10081.jpg',
                    isAvailable: true
                }, {
                    id: 9,
                    name: 'Dark',
                    type: 'movie',
                    imgUrl: 'https://fsmedia.imgix.net/53/d9/2e/48/1991/4501/a1de/48f2000cd77b/jonas-kahnwald-searches-for-answers-on-netflixs-dark.jpeg?rect=0%2C705%2C4256%2C2127&auto=format%2Ccompress&dpr=2&w=650',
                    isAvailable: true
                }, {
                    id: 10,
                    name: 'Stranger Things',
                    type: 'movie',
                    imgUrl: 'https://vignette.wikia.nocookie.net/strangerthings8338/images/c/c1/ST_Issue_1_Cover_2.jpg',
                    isAvailable: true
                }
            ],
            listDataFiltered: []
        }
    },
    created: function () {
        this.filterData(null);
    },
    methods: {
        getFilterData: function() {
            return {
                types: [...new Set(this.listData.map(item => item.type))]
            }
        },
        filterData: function(data) {
            if (data) {
                const filterData = this.listData.filter(item => {
                    return (data.typeValue === '' || item.type === data.typeValue) && 
                    (data.availabilityValue === '' || item.isAvailable === (data.availabilityValue === 'yes' ? true : false)) &&
                    (item.name.toLowerCase().indexOf(data.searchName.toLowerCase()) > -1)
                })
                this.listDataFiltered = filterData;
            } else {
                this.listDataFiltered = this.listData;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    .shopping-container {
        width: 80%;
        margin: 0 auto;
    }
</style>

