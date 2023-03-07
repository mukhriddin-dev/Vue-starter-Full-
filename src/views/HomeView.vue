<script>
import { onMounted, computed } from 'vue';
import { useStore } from 'vuex';

export default {
  setup() {

    const store = useStore()

    return {
      addnumber: () => {
        store.commit('INCR')
      },
      count: computed(() => store.state.count.number),
      toast: computed(() => store.state.toast.message)
    }

  }
}
</script>


<template>
  <h1>{{ count }}</h1>
  <h1>{{ toast }}</h1>
  <button class="bg-green-500 p-5" @click="addnumber">
    ADD</button>
</template>


<style></style>