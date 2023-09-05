<script setup>
import { ref } from "vue";
import { useMouse } from "../reusables/mouse.js";

const { x, y } = useMouse();

const vFocus = {
  mounted: (el) => el.focus(),
};

import MyModal from "../components/icons/MyModel.vue";

const show = ref(true);
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h1>Mouse Tracker</h1>
    The mouse position is at :
    <h1>{{ x }}, {{ y }}</h1>

    <h1>Custom Directive Example</h1>

    <input type="text" v-focus />

    <div>
      <h1>Transition</h1>

      <button @click="show = !show">Toggle</button>
      <Transition>
        <p v-if="show">hello</p>
      </Transition>
    </div>

    <div>
      <h1>Teleport Concept</h1>

      <div>
        <MyModal />
      </div>
    </div>
  </div>
</template>

<style>
/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
