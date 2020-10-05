<template>
  <div class="editor">
    <h1>Edit Memo</h1>
    <textarea name="memo" v-model="memoBody"></textarea>
    <button @click="save">保存</button>  
  </div>
</template>

<script>
export default {
  name: 'edit',
  data: function() {
    return {
      memoBody: ''
    }
  },
  mounted: function() {
    let id = this.$route.params["id"];
    let memo =  this.$store.state.memos.find(memo => memo.id == id);
    this.memoBody = memo.body;
  },
  save: function() {
    this.$store.commit("update", {
      id: this.$route.params["id"],
      body: this.memoBody
    });
    this.$router.push('/');
  }
}
</script>