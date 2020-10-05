<template>
  <div class="editor">
    <h1>New Memo</h1>
    <textarea name="memo" v-model="memoBody"></textarea>
    <button @click="save">保存</button>
  </div>
</template>

<script>
export default {
  neme: "new",
  data: function() {
    return {
      memoBody: ""
    }
  },
  methods: {
    save: function() {
      this.$store.commit("save", {
      body: this.memoBody
      });
      this.$router.push("/");
    }
  }
}
</script>