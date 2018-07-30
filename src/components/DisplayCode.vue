<template>
  <div class="display-code">
    <slot></slot>
    <slot name="titleSlot" :title="title">
      <h3 class="title">{{ title }}</h3>
    </slot>
    <slot name="codeSlot" :code="code">
      <div v-if="type == 'html'">
        <div v-html="code"></div>
      </div>
      <div v-if="type == 'rawhtml'" :code="code">
        <pre>{{ code }}</pre>
      </div>
      <div v-if="type == 'php'" :code="code">
        <pre>{{ code }}</pre>
      </div>
      <div v-if="type == 'js'" :code="code">
        <pre>{{ code }}</pre>
      </div>
    </slot>
  </div>
</template>

<script>
export default {
  name: 'DisplayCode',
  props: {
    type: {
      type: String,
      require: true
    },
    title: String,
    code: String
  }
};
</script>

<style scoped>
.display-code {
  margin: 0 0 30px 0;
}
.display-code h3.title {
  margin: 0 0 15px 0;
}
.display-code pre {
  border: 1px solid #ccc;
  padding: 15px;
  background: #ededed;
}
</style>
