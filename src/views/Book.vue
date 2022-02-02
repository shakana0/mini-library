<template>
  <div class="book-wrapper">
    <button class="go-back-btn" @click="$emit('changePage')"></button>
    <main class="book-content">
      <article class="book-img" :class="book.color">
       <BookInList />
      </article>

      <section class="bookinfos">
        <div book-info>
          <h1>{{ book.title }}</h1>
          <h3>{{ book.author }}</h3>
        </div>
        <article class="plot-text">
          <p>{{ book.plot }}</p>
        </article>
        <section class="more-info">
          <div>
            <p>Audience:{{ book.audience }}</p>
            <p>First published:{{ book.year }}</p>
          </div>
          <div>
            <p>Pages:{{ book.pages }}</p>
            <p>Publisher: {{ book.publisher }}</p>
          </div>
        </section>
        <button class="add-to-cart">Oh, i wanna read it!</button>
      </section>
    </main>
  </div>
</template>

<script>
import BookInList from '../components/BookInList.vue'
export default {
  props: { book: Object },
  comments:{BookInList}
};
</script>

<style scoped>
.book-content {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-gap: 4rem;
}
.book-img {
  grid-area: 2 / 2 / 5 / 4;
  background-color: pink;
}
.book-wrapper {
  background-color: rgb(54, 54, 54);
  /* padding-left: 20rem;
  padding-top: 10rem; */
}
.go-back-btn {
  border-radius: 50%;
  background-color: white;
  color: white;
  height: 30px;
}
.book-info {
  width: 75vw;
}
.add-to-cart {
  background-color: white;
  color: rgb(54, 54, 54);
  padding: 12px 10px;
  margin-top: 1rem;
  border-radius: 6px;
  border: none;
}
.add-to-cart:hover {
  background-color: rgb(128, 125, 125);
  cursor: pointer;
}
.bookinfos {
  grid-area: 2 / 4 / 5 / 6;
  /* display: grid;
  grid-template-columns: repeat(2, 1fr); */
}
h1 {
  color: white;
  font-size: 48px;
  margin: 0;
}
h3 {
  color: rgb(173, 167, 167);
  margin-top: 0;
  /* font-size: 38px;
  font-weight: 100; */
}
.plot-text {
  margin-top: 2.5rem;
}
p {
  color: white;
}
.more-info {
  background-color: rgb(80, 78, 78);
  padding: 1rem;
}
.more-info div {
  display: flex;
  justify-content: space-between;
}
</style>
