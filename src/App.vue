<template>
  <div>
    <!--    <the-header></the-header>-->
    <TheHeader/>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <!--    <active-goals></active-goals>-->
    <!--    <ManageGoals/>-->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
    <!--keep avoid to avoid losing info that user adds in components-->
  </div>
</template>

<script>
//Local component
import TheHeader from './components/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from "./components/CourseGoals";
import ActiveGoals from "./components/ActiveGoals";
import ManageGoals from "./components/ManageGoals";

export default {
  components:{
    // 'the-header': TheHeader,
    TheHeader,
    // BadgeList,
    // UserInfo,
    // CourseGoals,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      selectedComponent: null,
    };
  },
  methods:{
    setSelectedComponent(cmp){
      this.selectedComponent = cmp;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>