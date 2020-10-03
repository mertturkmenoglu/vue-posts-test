<template>
  <div class="container card-container mb-5">
    <div class="card shadow-lg custom-card-border px-3 py-2">
      <div class="card-body">
        <div class="card-title d-flex">
          <span class="mr-2">
            <img :src="post.userImage" class="card-user-img rounded-circle" />
          </span>
          <span class="ml-2">
            <div>
              <span class="lead">{{ post.username }}</span>
            </div>
            <div class="card-subtitle text-muted">{{ post.date }}</div>
          </span>
        </div>
        <div class="card-text my-3 text-center">
          <img :src="post.imageUrl" class="card-image card-post-img" />
        </div>
        <div>
          <div
            class="fa-heart"
            :class="[
              'fa-heart',
              { far: !favStatus, fas: favStatus, liked: favStatus },
            ]"
            @click="favToggle"
          />
          <span class="ml-2">{{ likeCount }} Favorites</span>
          <i class="far fa-comment-alt ml-5" />
          <span class="ml-2">{{ post.comments.length }} Comments</span>
        </div>
        <div class="card-text mt-3 text-justify">{{ post.content }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserPost",
  props: ["post"],
  data() {
    return {
      favStatus: this.post.liked,
      likeCount: this.post.likeCount,
    };
  },
  methods: {
    favToggle() {
      if (this.favStatus) {
        this.likeCount--;
      } else {
        this.likeCount++;
      }

      this.favStatus = !this.favStatus;
    },
  },
};
</script>

<style scoped>
h2 {
  margin-top: 2vh;
  text-align: center;
}

.card-user-img {
  max-height: 48px;
  width: auto;
}

.card-post-img {
  max-width: 40vw;
  height: auto;
}

.custom-card-border {
  border-color: #dd2c00;
}

.card-container {
  max-width: 50vw;
}

.liked {
  color: #dd2c00;
}
</style>