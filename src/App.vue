<template>
  <div id="app">
    <div class="col">
      <editor
        ref="ace"
        v-model="crip"
        @init="editorInit"
        lang="text"
        theme="dracula"
        width="100%"
        height="100%"
      />
      <button @click="criptografar()">Criptografar</button>
    </div>
    <div class="col">
      <editor
        ref="ace2"
        v-model="desCrip"
        @init="editorInit"
        lang="text"
        theme="dracula"
        width="100%"
        height="100%"
      />
      <button>Des Criptografar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({ crip: "", desCrip: "" }),
  methods: {
    editorInit() {
      require("brace/ext/textarea"); //language extension prerequsite...
      require("brace/mode/text");
      require("brace/theme/dracula");
    },
    criptografar() {
      // this.desCrip = this.crip;
    },
  },

  components: {
    editor: require("vue2-ace-editor"),
  },

  mounted() {
    const editor = this.$refs.ace.editor;
    const editor2 = this.$refs.ace2.editor;
    const conf = {
      fontSize: "18pt",
    };
    editor.setOptions(conf);
    editor2.setOptions(conf);
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  width: 100vw;
  height: 100vh;
  display: flex;
}
.col {
  width: 50%;
  display: flex;
  height: 100%;
  flex-direction: column;
}

.col button {
  height: 50px;
  font-size: 20px;
}
</style>
