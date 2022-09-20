<template>
  <tr>
    <td>{{ index + 1 }}</td>
  <td>{{ task }}</td>
  <td>
    <button class="btn btn-danger btn-block" @click="removeTodo">Delete</button>
  </td>
  </tr>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class TodoItem extends Vue {
  @Prop() task!: string;
  @Prop() index!;

  removeTodo() {
    this.$emit("removeTodoparaelpadre", this.index);
  }
}
</script>
