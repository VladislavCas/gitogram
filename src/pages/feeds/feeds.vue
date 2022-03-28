<template>
    <div class="topline">
        <topline>
          <template #headline>
            <div class="header">
              <div class="logo">
                <svg class="logo__svg">
                  <use xlink:href="../../assets/logo/logo.svg#logo"></use>
                </svg>
              </div>
              <div class="menu">
                <div class="icon">
                  <icon name="home" />
                </div>
                <div class="icon__profile">
                  <icon name="profile" />
                </div>
                <div class="icon">
                  <icon name="door" />
                </div>
              </div>
            </div>
          </template>
          <template #content>
            <div class="stories">
              <li class="stories-item" v-for="story in stories" :key="story.id">
                <story-user-item
                    :avatar="story.avatar"
                    :username="story.username"
                    @onPress="hadlePress(story.id)"
                />
              </li>
            </div>
          </template>
        </topline>
    </div>
    <div class="feed">
      <feed>
        <template #feed>
           <div class="post">
             <post
                :avatar="story.avatar"
                :username="story.username"
                 @onPress="hadlePress(story.id)"
             />
           </div>
        </template>
      </feed>
    </div>
</template>

<script>
import { topline } from '../../components/topline'
import { storyUserItem } from '../../components/storyUserItem'
import { icon } from '../../icons'
import stories from './data.json'
import { feed } from '../../components/feed'
import { post } from '../../components/post'
import { postContent } from '../../components/postContent'

export default {
  name: 'feeds',
  components: {
    topline,
    icon,
    storyUserItem,
    feed,
    post,
    postContent
  },
  data () {
    return {
      stories
    }
  }
}
</script>

<style lang="scss" scoped src="./feeds.scss"></style>
