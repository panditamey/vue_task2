<template>
  <div>
    <h1>Parent Component</h1>
    <h2>Message from parent to child : {{ parentMessage }}</h2>

    <ChildComponent
      :message="parentMessage"
      @update-message="handleMessageUpdates"
    />
    <h4>Message from child to parent : {{ childMessage }}</h4>
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";
export default {
  name: "ParentComponent",

  components: {
    ChildComponent,
  },

  data() {
    return {
      parentMessage: "Hello from parent",
      childMessage: "",
    };
  },

  methods: {
    handleMessageUpdates(newMessage) {
      this.childMessage = newMessage;
    },
  },
};
</script>
