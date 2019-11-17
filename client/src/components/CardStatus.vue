<template>
  <div>
    <b-card-group deck>
      <b-card
        :header="title"
        header-text-variant="white"
        :header-bg-variant="variant"
      >
        <draggable class="list-group" :list="list" group="people">
          <div v-for="task in list" :key="task.title">
            <Card :task="task" @delete="delTask" />
          </div>
        </draggable>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import Card from "@/components/Card";

export default {
  name: "Cardstatus",
  components: {
    draggable,
    Card
  },
  props: ["title", "list", "variant"],
  methods: {
    delTask(id) {
      this.$emit("delete", id);
    }
  }
};
</script>

<style></style>
