<template>
  <div class="vtv">

    <button @click="playVideo" class="nutan" v-if="hidDen===false">
      <div class="nut-content">
        <img :src=hinhAnh alt="" width="100px" height="100px"/>
        <p v-if="hienThiTieude===true">{{ tenKenh }}</p>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'VTV',
  props: {
    tenKenh: String,
    videoUrl: String,
    hinhAnh : String,
    hidDen : Boolean,
    hienThiTieude : Boolean
  },
  methods: {
    playVideo() {
      this.$emit('playVideo', this.videoUrl);
    }
  }
}
</script>

<style scoped>
vtv {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

.nutan {
  width: 170px;
  margin: 10px;
  font-size: 20px;
  border-radius: 17px;
}
.nut-content{
  display: flex;
  align-items: center;
  gap: 10px;
}
</style>
