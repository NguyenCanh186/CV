<template>
  <div
    class="py-4 p-st"
    :class="{
      'bg-light': !nightMode,
      'bg-dark2': nightMode,
      'text-light': nightMode,
    }"
  >
    <div class="container">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >About Me.</span
        >
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <div>

      </div>
      <div class="row">
        <div class="col-xl-4 col-bg-4 col-md-4 col-sm-12">
          <div class="col-xl-12 col-bg-12 col-md-12 col-sm-12">
            <p
                class="title1"
                data-aos="fade"
                data-aos-once="true"
                data-aos-easing="ease-in-out"
                data-aos-mirror="true"
                data-aos-duration="1000"
            >
              Thông tin
            </p>
            <ul
                class="timeline m-0 pt-1"
                :style="{ 'transition-delay': 1 / 4.2 + 's' }"
                data-aos="fade-up"
                data-offset="10"
                data-aos-once="true"
                data-aos-easing="ease-in-out"
                data-aos-mirror="true"
                data-aos-duration="500"
            >
              <li class="m-0 pb-2">
                <div>
                  <div class="px-2 title2">Nguyễn Thế Cảnh</div>
                  <div class="px-2 title3">
                    Sinh nhật: 01/08/1996 <br>
                    Nơi ở hiện tại: <br> Nam Từ Liêm - Hà Nội <br>
                    Số điện thoại: 0984228578
                    Email: canh.nguyen3306@gmail.com
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div class="col-xl-4 col-bg-4 col-md-4 col-sm-12">
          <Timeline :data="education" :nightMode="nightMode" />
        </div>
        <div class="col-xl-4 col-bg-4 col-md-4 col-sm-12">
          <Timeline :data="experience" :nightMode="nightMode" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Timeline from "./helpers/Timeline";
import info from "../../info";

export default {
  name: "About",
  components: {
    Timeline,
  },
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      education1: {
        title: "Thông tin",
        data: info.education1,
      },
      education: {
        title: "Học vấn",
        data: info.education,
      },
      experience: {
        title: "Kinh nghiệm",
        data: info.experience,
      },
    };
  },
};
</script>

<style scoped>
.title {
  font-size: 30px;
  font-weight: 500;
}
.title1 {
  font-size: 24px;
  font-weight: 500;
}

.title2 {
  font-size: 20px;
  font-weight: 400;
}

.title3 {
  font-size: 16px;
  font-weight: 400;
}

.badge {
  background-color: #bbd4dd;
  transition: all 0.5s;
  font-weight: 500;
}

.date {
  font-size: 14px;
  font-weight: 300;
}

ul.timeline {
  list-style-type: none;
  position: relative;
}
ul.timeline:before {
  content: " ";
  background: #d4d9df;
  display: inline-block;
  position: absolute;
  left: 29px;
  width: 2px;
  height: 93%;
  margin-top: 20px;
  z-index: 400;
}
ul.timeline > li {
  margin: 20px 0;
  padding-left: 20px;
}
ul.timeline > li:before {
  content: " ";
  background: #8585ad;
  display: inline-block;
  position: absolute;
  border-radius: 50%;
  border: 2px solid #8585ad;
  left: 20px;
  width: 25px;
  height: 25px;
  z-index: 400;
}

.bg-dark2 {
  background-color: #3c4148 !important;
}
</style>
