<template>
  <div id="app">
    <display-code :type="'rawhtml'" :title="'Raw HTML code'" :code="htmlcode"></display-code>
    <display-code :type="'html'" :title="'HTML code'" :code="htmlcode"></display-code>
    <display-code :type="'js'" :title="'JavaScript code'" :code="jscode"></display-code>
    <display-code :type="'php'" :title="'PHP code'" :code="phpcode"></display-code>
 
    <hr />
    <br />

    <display-code :title="'Raw HTML code'" :type="'rawhtml'" :code="htmlcode">
      <template slot="titleSlot" slot-scope="props">
        <h3 class="title">{{ props.title }}</h3>
      </template>
      <template slot="codeSlot" slot-scope="props">
        <pre>{{ props.code }}</pre>        
      </template>
    </display-code>
  </div>
</template>

<script>
import DisplayCode from './components/DisplayCode'

export default {
  name: 'App',
  components: {
    DisplayCode
  },
  data: function () {
    return {
      htmlcode: `<!-- My comment -->
<div style="color: green; font-size: 16px;">
  <div><strong>Hello World!</strong></div>
  <button onclick="alert('Good morning!');">Greeting!</button>
</div>
`,
      phpcode: `<?php
  function greeting () {
    return 'Hello World!';  
  };
?>`,
      jscode: `<!-- My comment -->
<script>
  alert('hi');
<\/script>
`
    }
  }
};
</script>

<style>

</style>
