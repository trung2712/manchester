<template>
  <div class="khung">
    <h1>{{ ten }}</h1>
    <div class="video-container">
      <iframe class="hinh"  :src="onVideoURL"
              title="YouTube video player" frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>

      </iframe>

      <div class="cacnut">
        <VTV v-for="(video, index) in danhSachVideo"
             :key="index"
             :tenKenh="video.tenKenh"
             :videoUrl="video.url"
             @playVideo="onVideo"
             :hinhAnh="video.img"
             :hidDen="video.hidDen"
             :hienThiTieude="video.hienThiTieuDe"
        ></VTV>
      </div>
    </div>
  </div>
</template>

<script>
import VTV from "@/components/VTV.vue";

export default {
  name: 'TiVi',
  components: { VTV },
  props: {
    ten: String
  },
  data() {
    return {
      onVideoURL: '',
      danhSachVideo: [
        {
          url: "https://www.youtube.com/embed/PfA4-PxuuvQ?si=h9-JJB6mF5l7EAZ0",
          tenKenh: "VTV1",
          img: 'https://images.pexels.com/photos/47730/the-ball-stadion-football-the-pitch-47730.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500',
          hidDen : false,
          hienThiTieuDe : true
        },
        {
          url: "https://www.youtube.com/embed/Md4XleE7y48?si=b79K_zvEoljf5XRp",
          tenKenh: "VTV2",
          img: "https://toigingiuvedep.vn/wp-content/uploads/2021/05/hinh-nen-bong-da.jpg",
          hidDen : false,
          hienThiTieuDe : true
        },
        {
          url: "https://www.youtube.com/embed/Arq4XORS1ic?si=3Fsmoh5bwlV5UMTq",
          tenKenh: "VTV3",
          img: 'https://toigingiuvedep.vn/wp-content/uploads/2021/05/hinh-nen-bong-da.jpg',
          hidDen : false,
          hienThiTieuDe : true
        }
      ]
    }
  },
  methods: {
    onVideo(videoUrl) {
      this.onVideoURL = videoUrl;
    }
  }
}
</script>

<style scoped>
.khung {
  width: 70%;
  margin: 0 auto;
  background-color: tomato;
  padding: 70px;
  box-sizing: border-box;
}
.hinh{
  width: 700px;
  height: 600px;
  background-color:floralwhite;
  border-radius: 10px;
}
.video-container {
  display: flex;
  justify-content: center; /* Canh giữa ngang */
  align-items: center; /* Canh giữa dọc */
}

.cacnut {
  display: flex;
  flex-direction: column;
  margin-right: 20px;
}


</style>
