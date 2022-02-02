<template>
  <div class="book-wrapper">
    <article
      class="book"
      v-for="(book, index) in bookList"
      :key="index"
      :class="book.color"
      @click="$emit('getBookInfo', book)"
    >
      <section>
        <h3>{{ book.title }}</h3>
        <p>{{ book.author }}</p>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  props: {
    bookList: Array,
    bookstyle: { type: Object },
  },

  data() {
    return {};
  },
};
</script>

<style scoped>
.book-wrapper {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: repeat(2, 1fr);
  grid-gap: 1rem;
}
.book {
  height: 220px;
  width: 190px;
}
.red {
  background: linear-gradient(
    40deg,
    rgba(195, 34, 34, 0.8813900560224089) 0%,
    rgba(201, 101, 122, 0.9346113445378151) 74%
  );
  grid-area: 1 / 2 / 2 / 3;
}
.green {
  background: linear-gradient(
    40deg,
    rgba(34, 163, 195, 0.8813900560224089) 33%,
    rgba(132, 201, 101, 0.9346113445378151) 80%,
    rgba(132, 201, 101, 0.9346113445378151) 88%
  );
  grid-area: 1 / 3 / 2 / 4;
}
.yellow {
  background: yellow;
  grid-area: 1 / 5 / 2 / 6;
}
.orange {
  background: orange;
  grid-area: 1 / 4 / 2 / 5;
}
.purple {
  background: rgb(204, 70, 204);
  grid-area: 2 / 5 / 3 / 6;
}
.light-blue {
  background: lightblue;
  grid-area: 2 / 3 / 3 / 4;
}
.blue {
  background: rgb(55, 55, 228);
  grid-area: 2 / 2 / 3 / 3;
}
.light-green {
  background: lightgreen;
  grid-area: 2 / 4 / 3 / 5;
}
h3{
 font-weight: 800;
 color: white;
 margin-bottom: 5px;
}
section p {
  margin: 0;
  color: white;
}
section{
  display: flex;
  flex-direction: column;
  margin-top: 65%;
  padding: 0 1rem;
}
</style>
