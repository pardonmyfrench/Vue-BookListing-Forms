<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
    <label for="finishedReading">Finished Reading
      <input v-model="bookData.finishedReading" type="checkbox" name="finished" id="finished" placeholder="Finished Reading">
    </label>
    </div>
    <label for="borrowed">
        <input v-model="bookData.ownership" type="radio" name="ownership" value="borrowed" id="borrowed">borrowed</label>
      </label>
    <label for="bought">
        <input v-model="bookData.ownership" type="radio" name="ownership" value="bought" id="bought">bought</label>
      </label>
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
