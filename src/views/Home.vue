<template>
  <div class="container mt-5">
    <div v-for="post in posts" :key="post.id">
      <UserPost :post="post" />
    </div>
  </div>
</template>

<script>
import UserPost from "@/components/UserPost";

export default {
  name: "Home",
  components: { UserPost },
  data: () => ({
    posts: [
      {
        id: "1234",
        comments: [],
        username: "mertturkmenoglu",
        userImage: "https://github.com/mertturkmenoglu.png",
        date: new Date().toLocaleDateString(),
        imageUrl:
          "https://upload.wikimedia.org/wikipedia/commons/d/d7/Squirrel_in_Seurasaari_autumn.JPG",
        content:
          "Empire State Building. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam in eleifend lectus, quis commodo nibh. Nunc id condimentum dolor. Praesent tempor rutrum elit pulvinar lobortis. Cras elementum ac nibh ut.",
        likeCount: 5,
        liked: true,
      },
      {
        id: "4321",
        comments: [],
        username: "SerkanKaanBahsi",
        userImage: "https://github.com/SerkanKaanBahsi.png",
        date: new Date().toLocaleDateString(),
        imageUrl:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Kotlin-logo.svg/1200px-Kotlin-logo.svg.png",
        content: "Kotlin",
        likeCount: 25,
        liked: false,
      },
    ],
  }),
};
</script>

<style scoped>
h2 {
  margin-top: 2vh;
  text-align: center;
}
</style>
