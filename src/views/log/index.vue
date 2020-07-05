<template>
  <div class="person-container">
    <message-board />
    <person-list />
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import messageBoard from "./components/messageBoard.vue";
import personList from "./components/personList.vue";

export default {
  name: "Person",
  components: { messageBoard, personList },
  computed: {
    ...mapGetters(["name"])
  }
};
</script>

<style lang="scss" scoped>
.person-container {
}
</style>
