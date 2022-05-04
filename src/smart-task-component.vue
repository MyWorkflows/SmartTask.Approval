<script lang="ts">
import { defineComponent } from "vue";


export default /*#__PURE__*/ defineComponent({
  name: "SmartTaskComponent", // vue component name
  props: ['componentState', 'componentStatus'],
  data() {
    return { model: {} };
  },
  computed: {},
  methods: {
    async submitForm() {
      this.$emit("execute-smart-task", this.model);
    },
  },
  created() {
    if (this.componentState) {
      this.model = this.componentState;
    }
  },
  setup() {},
});
</script>

<template>
  <div class="mb-3">
    <label class="form-label">Short Comment</label
    ><textarea type="text" class="form-control" rows="5"></textarea>
  </div>
  <div class="my-5 float-end">
    <button type="submit" class="btn btn-danger mx-2">Reject</button>
    <button type="submit" class="btn btn-success">Approve</button>
  </div>
</template>

