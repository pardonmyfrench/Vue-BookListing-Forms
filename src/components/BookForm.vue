<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
    <label for="finishedReading">Finished Reading</label>
      <input v-model="bookData.finishedReading" type="checkbox" name="finished" id="finishedReading">
    </div>
        <input v-model="bookData.ownership" type="radio" name="ownership" value="borrowed" id="borrowed">
        <label for="bought">borrowed</label>
        <input v-model="bookData.ownership" type="radio" name="ownership" value="bought" id="bought">
       <label for="bought">bought</label>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  }
};
</script>

<style>
</style>
