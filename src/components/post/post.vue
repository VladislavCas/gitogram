<template>
   <div class="c-post-container" @click="$emit('onPress')>
     <div>
        <img :src="avatar" class="img" alt="username avatar" />
     </div>
     <div class="username">{{ username }}</div>
     <div class="post__content">
     </div>
   </div>
</template>

<script>
export default {
  props: {
    avatar: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    }
  }
}
</script>


<style lang="scss" scoped src="./post.scss"></style>
