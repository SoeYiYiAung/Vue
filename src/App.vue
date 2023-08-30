<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <ConditionComponentVue></ConditionComponentVue> -->
  <ProductComponentVue></ProductComponentVue>
  <!-- <EmployeeComponentVue></EmployeeComponentVue> -->
  <!-- <FormComponentVue></FormComponentVue> -->
  <!-- <CrudComponentVue></CrudComponentVue> -->
  <!-- <ComputedComponentVue></ComputedComponentVue> -->
  <!-- <WatcherComponentVue></WatcherComponentVue> -->
  <ParentComponentVue></ParentComponentVue>
  
</template>

<script>
// import ConditionComponentVue from './components/ConditionComponent.vue';
import ProductComponentVue from './components/ProductComponent.vue';
// import EmployeeComponentVue from './components/EmployeeComponent.vue';
// import FormComponentVue from './components/FormComponent.vue';
// import CrudComponentVue from './components/CrudComponent.vue';
// import ComputedComponentVue from './components/ComputedComponent.vue';
// import WatcherComponentVue from './components/WatcherComponent.vue';
// import ParentComponentVue from './components/ParentComponent.vue';



import 'bootstrap/dist/css/bootstrap.min.css';


export default {
  name: 'App',
  components: {
    // ConditionComponentVue,
    ProductComponentVue,
    // EmployeeComponentVue,
    // FormComponentVue,
    // CrudComponentVue,
    // ComputedComponentVue,
    // WatcherComponentVue,
    // ParentComponentVue

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
