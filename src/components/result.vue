<template>
  <p>reaction time {{ score }}ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Opoor fast finger 👍👍👍👌👌👍😂🤣";
    } else if (this.score < 400) {
      this.rank = "Opoor 😝😝😝😝🤣😂";
    } else {
      this.rank = "To lazy you can't carry your hand👎👎👎👎 😂😂😂";
    }
  }
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>