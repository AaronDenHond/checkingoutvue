<template>
  <div id="app"></div>
  Hello {{ person.firstName }} {{ person.lastName }}<br />
  hello {{ fullName }} <br />
  Number of articles: {{ articleCount }}
   <!-- eventlistener -->
  <button @click="addArticle">Add Article</button>
</template>

<script>
export default {
  name: "App",
  data() {
    //these 2 vars articlecount and person can be used as vars in our templates
    return {
      articleCount: 0,
      person: {
        firstName: "Aaron",
        lastName: "Doggo",
      },
    };
  },
  //everything we have as computed can be used as a var in our template sections
  computed: {
    fullName() {
      return `${this.person.firstName} ${this.person.lastName}`;
    },
  },
  methods: {
    addArticle() {
      this.articleCount++;
    },
  },
  watch: {
    articleCount(newArticleCount,oldArticleCount) {
    if(newArticleCount !== oldArticleCount) {
      console.log("An article was added");
    }
  }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
