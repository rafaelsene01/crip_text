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
      <button @click="descriptografar()">Descriptografar</button>
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
      let newArray = [];
      for (const key in this.crip) {
        switch (this.crip[key]) {
          case "b":
            newArray.push("f");
            break;
          case "d":
            newArray.push("n");
            break;
          case "f":
            newArray.push("z");
            break;
          case "g":
            newArray.push("y");
            break;
          case "h":
            newArray.push("w");
            break;
          case "j":
            newArray.push("q");
            break;
          case "k":
            newArray.push("l");
            break;
          case "l":
            newArray.push("b");
            break;
          case "m":
            newArray.push("k");
            break;
          case "n":
            newArray.push("h");
            break;
          case "p":
            newArray.push("x");
            break;
          case "q":
            newArray.push("m");
            break;
          case "r":
            newArray.push("j");
            break;
          case "s":
            newArray.push("p");
            break;
          case "t":
            newArray.push("v");
            break;
          case "v":
            newArray.push("d");
            break;
          case "w":
            newArray.push("t");
            break;
          case "x":
            newArray.push("r");
            break;
          case "y":
            newArray.push("s");
            break;
          case "z":
            newArray.push("g");
            break;
          default:
            newArray.push(this.crip[key]);
            break;
        }
      }
      this.desCrip = newArray.join("");
    },
    descriptografar() {
      let newArray = [];
      for (const key in this.desCrip) {
        switch (this.desCrip[key]) {
          case "f":
            newArray.push("b");
            break;
          case "n":
            newArray.push("d");
            break;
          case "z":
            newArray.push("f");
            break;
          case "y":
            newArray.push("g");
            break;
          case "w":
            newArray.push("h");
            break;
          case "q":
            newArray.push("j");
            break;
          case "l":
            newArray.push("k");
            break;
          case "b":
            newArray.push("l");
            break;
          case "k":
            newArray.push("m");
            break;
          case "h":
            newArray.push("n");
            break;
          case "x":
            newArray.push("p");
            break;
          case "m":
            newArray.push("q");
            break;
          case "j":
            newArray.push("r");
            break;
          case "p":
            newArray.push("s");
            break;
          case "v":
            newArray.push("t");
            break;
          case "d":
            newArray.push("v");
            break;
          case "t":
            newArray.push("w");
            break;
          case "r":
            newArray.push("x");
            break;
          case "s":
            newArray.push("y");
            break;
          case "g":
            newArray.push("z");
            break;
          default:
            newArray.push(this.crip[key]);
            break;
        }
      }
      this.crip = newArray.join("");
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
