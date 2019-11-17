<template>
  <div>
    <div class="p-2">
      <b-card-group deck>
        <b-card :header="task.title">
          <p>Description: {{ task.description }}</p>
          <p>Assigned To: {{ task.assign }}</p>
          <b-button variant="danger" @click="delTask" size="sm"
            >Delete</b-button
          >
        </b-card>
      </b-card-group>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: ["task"],
  methods: {
    delTask() {
      this.$emit("delete", this.task.id);
    }
  }
};
</script>

<style scoped>
.card-header {
  background-color: white;
}
.card p {
  font-size: 14px;
}
</style>
