<template>
    <div class="wrapper">
      <div
        @click="toggleCardBody"
        :class="shouldExpand ? '' : 'dropdown-toggle'"
        class="card-header"
        bg='white'
        >
        Pages
      </div>
      <div
        class="card-body"
        :class="shouldExpand ? 'visible-cardbody' : 'hidden-cardbody'"
      >
        <ul class="list-group">
          <li class="list-group-item">
            <router-link class="text-dark" :to="{name: 'profileAbout'}">About</router-link>
          </li>
          <li class="list-group-item">Notification</li>
          <li class="list-group-item">
            <router-link class="text-dark" :to="{name: 'orderHistory'}">Order History</router-link>
          </li>
          <li class="list-group-item">
            <router-link class="text-dark" :to="{name: 'restaurantMeals'}">Meals</router-link>
          </li>
          <li class="list-group-item">
            <router-link class="text-dark" :to="{name: 'myRestaurants'}">My Restaurants</router-link>
          </li>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
  name: 'ProfileNav',
  data () {
    return {
      shouldExpand: this.isExpanded || false
    }
  },
  props: {
    isExpanded: Boolean
  },
  methods: {
    toggleCardBody () {
      this.shouldExpand = !this.shouldExpand
    }
  }
}
</script>
<style lang="scss" scoped>
@import '@/assets/scss/index.scss';
.wrapper {
  width: 150px;
  margin: 5%;
  @include desktop(){
    margin: 0;
    width: 300px;
  }
  .visibl-cardbody{
    display: block;
  }
  .hidden-cardbody {
    display: none;
  }
  .card-header {
    background: $light-color;
    height: 40px;
  }
}
</style>
