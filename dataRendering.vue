<template>
<!-- App.vue -->
  <div id="app">
    <img alt="Vue logo" src="./assets/KBO.png" width="100%" />
    <component1 msg="This Part is Component1" />
    <component2 msg="This Part is Component2" />
    <button v-on:click="fetchData">get Data</button>
    <child></child>
  </div>
</template>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script>
import Component1 from "./components/Component1";
import Component2 from "./components/Component2";
import Child from "./components/Child";

export default {
  el: "App",
  components: {
    component1: Component1,
    component2: Component2,
    child: Child,
  },
  data: function () {
    return {
      rootData: 10,
    };
  },
  methods: {
    fetchData: function () {
      axios
        .get("https://jsonplaceholder.typicode.com/users/")
        .then(function (response) {
          console.log(response);
        })
        .catch(function (err) {
          console.log(err);
        });
    },
  },
};
</script>



<template>
  <!-- Child.vue -->
  <div>
    Child
    <child-child></child-child>
  </div>
</template>

<script>
import ChildAndChild from "./ChildAndChild";

export default {
  name: "Child",
  data: function () {
    return {
      childData: 20,
    };
  },
  components: {
    "child-child": ChildAndChild,
  },
};
</script>



<template>
  <!-- ChildAndChild.vue -->
  <div>
    Child And Child
    <button @click="showRootLog">Root 데이터 조회</button>
    <button @click="showParentLog">Parent 데이터 조회</button>
  </div>
</template>

<script>
export default {
  name: "ChildAndChild",
  methods: {
    showRootLog: function () {
      console.log("rootData", this.$root.rootData);
    },
    showParentLog: function () {
      console.log("childData", this.$parent.childData);
    },
  },
};
</script>

