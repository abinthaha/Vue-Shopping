<template>
  <section class="filter-wrapper">
    <span>
      <input
        type="text"
        @input="onChange($event, 'searchName')"
        placeholder="Search Name"
        v-model="filterValues.searchName"
      />
    </span>

    <select
      @change="onChange($event, 'typeValue')"
      name="TypeFilter"
      id
      v-model="filterValues.typeValue"
    >
      <option value selected="true" disabled="disabled">Choose Type</option>
      <option
        v-for="(item, index) in filterData.types"
        v-bind:key="index"
        v-bind:value="item"
      >{{item}}</option>
    </select>
    <select
      @change="onChange($event, 'availabilityValue')"
      name="AvailabilityFilter"
      id
      v-model="filterValues.availabilityValue"
    >
      <option value selected="true" disabled="disabled">Choose Availability</option>
      <option value="yes">Available</option>
      <option value="no">Not Available</option>
    </select>
    <button @click="clearFilter()">Clear Filter</button>
  </section>
</template>

<script>
export default {
  name: "FilterContainer",
  props: ["filterData"],
  data: function() {
    return {
      filterValues: {
        searchName: "",
        typeValue: "",
        availabilityValue: ""
      }
    };
  },
  methods: {
    onChange(event, type) {
      this.filterValues[type] = event.target.value;
      this.$emit("filter-changed", this.filterValues);
    },
    clearFilter() {
      Object.keys(this.filterValues).forEach(type => {
        this.filterValues[type] = "";
      });
      this.$emit("filter-changed", this.filterValues);
    }
  }
};
</script>

<style lang='scss' scoped>
.filter-wrapper {
  display: flex;
  justify-content: center;
  select,
  input,
  button {
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0px;
    outline: none;
    border: 1px solid #ddd;
    background-color: #fff;
    margin: 10px;
    transition: all 0.3s ease;
  }
  input {
    width: 30%;
    min-width: 200px;
  }
  button {
    cursor: pointer;
    &:hover {
      background-color: #ddd;
    }
  }
  select,
  option {
    text-transform: capitalize;
  }
}
</style>
