<template>
  <div id="App" :class="{ move : display }" >
    <notifications position="bottom right" group="default" />
    <notifications position="top right" group="TR" />
    <notifications position="top left" group="TL" />
    <notifications position="bottom left" group="BR" />
    <side-bar></side-bar>
    <div class="panel" >
      <top-nav-bar :display="display" @click="sideBarDisplay"></top-nav-bar>
      <dashboard-content></dashboard-content>
      <dashboard-content-footer></dashboard-content-footer>
    </div>
  </div>
</template>

<script>
import SideBar from './SideBar'
import TopNavBar from './TopNavbar'
import DashboardContent from './Content'
import DashboardContentFooter from './ContentFooter'

export default {
  name: 'dashboard',
  components: { SideBar, TopNavBar, DashboardContent, DashboardContentFooter },
  data () {
    return {
      display: false
    }
  },
  methods: {
    sideBarDisplay (status) {
      this.display = status
    }
  }
}
</script>