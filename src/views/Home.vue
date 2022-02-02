<template>
  <div class="home">
    <router-link to="/readinglist"><button>Reading List</button></router-link>
    <h1>8 classic children’s books</h1>
    <Book
      v-if="currentView === 'SingleBook'"
      :book="choosenBook"
      @changePage="changePage"
    />
    <BookInList
      :bookList="bookList"
      bookstyle:bookstyle
      @getBookInfo="getBookInfo"
      v-if="currentView === 'BookList'"
    />
  </div>
</template>
<script>
import BookInList from "../components/BookInList.vue";
import Book from "./Book.vue";
export default {
  components: { BookInList, Book },
  methods: {
    getBookInfo(book) {
      this.currentView = "SingleBook";
      this.$emit("setBookInfo", book);
      this.choosenBook = book;
    },
    changePage() {
      this.currentView = "BookList";
    },
  },
  data() {
    return {
      choosenBook: {},
      currentView: "BookList",
      bookList: [
        {
          title: "Charlotte's web",
          author: "Margaret Wise",
          publisher: "Brown	Harper Festival",
          year: 1947,
          pages: 30,
          plot: "In a soothing, repetitive tone, a young rabbit says goodnight to all the things in the room. Instead of plot, Goodnight Moon looks at the world from the eyes of a very young child, calming children with the ritual of naming each object around them. Lulling babies to sleep since 1947, this classic still ranks on bestseller lists, with some estimates of all-time copies sold worldwide topping 48 million. Find out more of the best books to help your child fall asleep.",
          audience: "1 - 4 years",
          color: "red",
        },

        {
          title: "The very hungry caterpillar",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes. ,The Very Hungry Caterpillar",
          audience: "8 - 12 years",
          color: "green",
        },

        {
          title: "The tale of Peter rabbit",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "orange",
        },
        {
          title: "Madeline",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "yellow",
        },
        {
          title: "Goodnight moon",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "blue",
        },
        {
          title: "Where the wild things are",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "light-blue",
        },
        {
          title: "A wrinkle in time ",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "light-green",
        },
        {
          title: "Harold and the purple Crayon",
          author: "E. B. White",
          publisher: "Harper Collins",
          year: "1952",
          pages: "192",
          plot: "Number one on the National Education Association‘s list of the best children’s books, this 1952 classic tells a tale of friendship featuring a spider named Charlotte,a pig named Wilbur, and a girl named Fern. But the cycle of life in this pastoral farm setting doesn’t just make for a sweet story—death does occur, although in a peaceful way. Caregivers should be aware of questions that may arise as children make the transition to reading literature with deeper themes, like this one. Find out the special joy of reading children’s books through grown-up eyes.",
          audience: "8 - 12 years",
          color: "purple",
        },
      ],
    };
  },
};
</script>

<style lang="sass">
.home a button
  padding: 6px 30px
  background-color: #252525
  color: lightgrey
  border: none
  border-radius: 4px
  transition: background-color 0.5s ease, color 0.5s ease
.home a button:hover
  color: #252525
  background-color: lightgrey
</style>
