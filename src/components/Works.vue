<template>
  <div class="works">
    <div class="main">
      <h1 class="main__title">{{ works[workIndex].title }}</h1>
      <p class="main__description">{{ works[workIndex].description }}</p>
      <ul class="main__skillList">
        <li v-for="skill in works[workIndex].skills" class="main__skillItem">
          <img :src="require(`@/assets/${skill}`)">
        </li>
      </ul>
    </div>
    <ul class="works__list">
      <li v-for="(work, i) in works" class="works__item" @click="changeWork(i)">
        <h2>{{ work.title }}</h2>
        <!-- <p>{{ work.skills[0] }}</p> -->
        <!-- <img :src="require(`@/assets/work.skils[0]`)"> -->
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data () {
    return {
      workIndex: 0,
      works: [
        {
          title: 'My Favorite Music',
          description: '好きな音楽を紹介できるプロフィールサービス。ログイン、投稿、編集、削除、セッションを切ったシェアページ等',
          skills: ['mfm_1.png', 'mfm_2.png']
        },
        {
          title: 'シェアパレ',
          description: '一人一人が別々の一パーツしか見えない状態で着色し、一枚の塗り絵を完成させるサービス。',
          skills: ['share1.png', 'share2.png']
        },
        {
          title: 'ラーメン君の修行',
          description: '南大沢地区のラーメン屋紹介をノベルゲーム風に',
          skills: ['ramen1.png', 'ramen2.png']
        }
      ]
    }
  },
  methods: {
    changeWork (i){
      this.workIndex = i
    }
  }
}
</script>
<style lang="scss" scoped>
.main {
  padding-bottom: 100px;
  border-bottom: 1px solid #ddd;
  margin-bottom: 30px;
  &__title {
    text-align: center;
    margin-top: 100px;
  }
  &__description {
    margin: 0 auto 20px;
    width: 500px;
    text-align: center;
  }
  &__skill {
    &List {
      display: flex;
      justify-content: center;
    }
    &Item {
      margin: 0 5px;
      img {
        width: 250px;
        height: 150px;
      }
    }
  }
}
.works {
  &__list {
    margin: 0 auto;
    width: 1200px;
    display: flex;
    justify-content: center;
  }
  &__item {
    border: 1px solid #ddd;
    text-align: center;
    margin: 0 10px;
    width: 400px;
    height: 300px;
    line-height: 100px;
    vertical-align: middle;
    float: left;
    cursor: pointer;
    &:hover {
      background-color: #eee;
    }
  }
}
</style>
