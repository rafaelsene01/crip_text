<template>
  <div id="app">
    <div class="col">
      <editor
        ref="ace"
        v-model="desCrip"
        @init="editorInit"
        lang="text"
        theme="dracula"
        width="100%"
        height="100%"
      />
      <button @click="criptografar()">Criptografar</button>
      <h4>Criptografado</h4>
      <p>{{ crip }}</p>
    </div>
    <div class="col">
      <editor
        ref="ace2"
        v-model="crip"
        @init="editorInit"
        lang="text"
        theme="dracula"
        width="100%"
        height="100%"
      />
      <button @click="descriptografar()">Descriptografar</button>
      <h4>Descriptografado</h4>
      <p class="desCrip">{{ crip }}</p>
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
      for (const key in this.desCrip) {
        switch (this.desCrip[key]) {
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
          case "B":
            newArray.push("F");
            break;
          case "D":
            newArray.push("N");
            break;
          case "F":
            newArray.push("Z");
            break;
          case "G":
            newArray.push("Y");
            break;
          case "H":
            newArray.push("W");
            break;
          case "J":
            newArray.push("Q");
            break;
          case "K":
            newArray.push("L");
            break;
          case "L":
            newArray.push("B");
            break;
          case "M":
            newArray.push("K");
            break;
          case "N":
            newArray.push("H");
            break;
          case "P":
            newArray.push("X");
            break;
          case "Q":
            newArray.push("M");
            break;
          case "R":
            newArray.push("J");
            break;
          case "S":
            newArray.push("P");
            break;
          case "T":
            newArray.push("V");
            break;
          case "V":
            newArray.push("D");
            break;
          case "W":
            newArray.push("T");
            break;
          case "X":
            newArray.push("R");
            break;
          case "Y":
            newArray.push("S");
            break;
          case "Z":
            newArray.push("G");
            break;
          default:
            newArray.push(this.desCrip[key]);
            break;
        }
      }
      this.crip = newArray.join("");
    },
    descriptografar() {
      let newArray = [];
      for (const key in this.crip) {
        switch (this.crip[key]) {
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
          case "F":
            newArray.push("B");
            break;
          case "N":
            newArray.push("D");
            break;
          case "Z":
            newArray.push("F");
            break;
          case "Y":
            newArray.push("G");
            break;
          case "W":
            newArray.push("H");
            break;
          case "Q":
            newArray.push("J");
            break;
          case "L":
            newArray.push("K");
            break;
          case "B":
            newArray.push("L");
            break;
          case "K":
            newArray.push("M");
            break;
          case "H":
            newArray.push("N");
            break;
          case "X":
            newArray.push("P");
            break;
          case "M":
            newArray.push("Q");
            break;
          case "J":
            newArray.push("R");
            break;
          case "P":
            newArray.push("S");
            break;
          case "V":
            newArray.push("T");
            break;
          case "D":
            newArray.push("V");
            break;
          case "T":
            newArray.push("W");
            break;
          case "R":
            newArray.push("X");
            break;
          case "S":
            newArray.push("Y");
            break;
          case "G":
            newArray.push("Z");
            break;
          default:
            newArray.push(this.crip[key]);
            break;
        }
      }
      this.desCrip = newArray.join("");
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
.desCrip {
  font-weight: 600;
  font-style: italic;
}
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

.col + .col {
  border-left: 4px solid red;
}
</style>
