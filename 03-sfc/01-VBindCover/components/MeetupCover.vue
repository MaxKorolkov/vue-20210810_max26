<template>
  <div class="meetup-cover">
    <h1 v-if="title" class="meetup-cover__title">{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: 'MeetupCover',
  props: {
    title: {
      type: String,
    },
    image: {
      type: String,
    },
  },
  computed: {
    checkImage() {
      return this.image ? `url(${this.image})` : 'var(--default-cover)';
    },
  },
};
</script>

<style scoped>
:root {
  --default-cover: url('https://course-vue.javascript.ru/api/images/2');
}

.meetup-cover {
  background-size: cover;
  background-position: center;
  background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), v-bind('checkImage');
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 410px;
  max-width: 1216px;
  margin: 0 auto;
}

.meetup-cover__title {
  color: var(--white);
  font-family: Roboto, sans-serif;
  font-weight: 700;
  font-size: 36px;
  line-height: 48px;
  padding: 0 16px;
  text-align: center;
}

@media all and (min-width: 992px) {
  .meetup-cover__title {
    font-size: 72px;
    line-height: 84px;
  }
}
</style>
