<template>
  <div>
    <nav
      class="navbar navbar-expand-lg  static-top"
      variant=""
    >
      <div class="container">
        <a
          class="navbar-brand"
          href="#"
        >TURBO FIRE SCHEDULE</a>

        <a
          class="nav-item"
          href="#"
        >TURBOFIRE TUẦN : - NGÀY : {{info.date.day}}</a>

      </div>

    </nav>

    <div class="container">
      <div>
        <b-carousel
          id="carousel-no-animation"
          style="text-shadow: 0px 0px 2px #000"
          no-animation
          indicators
          img-width="1024"
          img-height="480"
        >
          <b-carousel-slide
            :caption="info.date.slide.caption"
            :text-html="info.date.slide.text"
            img-src="https://picsum.photos/1024/480/?image=52"
          ></b-carousel-slide>
        </b-carousel>

      </div>
      <br />
      <div v-if="info">
        <div>
          <h3 class="alert-heading"></h3>

          <b-embed
            aspect="16by9"
            allowfullscreen
            :src="info.date.video[0]"
          ></b-embed>
        </div>
      </div>
      <br />

      <b-embed
        v-if="info"
        type="iframe"
        :src="info.date.video[1]"
        aspect="16by9"
        allowfullscreen
      ></b-embed>
    </div>
  </div>

</template>

<script>
import moment from 'moment'
const _vr = {
  abs10: 'https://www.youtube.com/watch?v=sqf20uwhWZ4',
  core20: '',
  fire30: 'https://streamtape.com/e/7XRwmWpymdCA1bj/',
  fire45: '',
  fire45EZ: '',
  fire55EZ: '',
  fire60: '',
  getFireUp: '',
  HIIT15: '',
  HIIT20: '',
  HIT25: '',
  HIT30: '',
  lower20: '',
  sculpt30: '',
  strecth10: 'https://www.youtube.com/watch?v=sqf20uwhWZ4',
  strecth40: '',
  tone30: '',
  upper20: '',
}
export default {
  data () {
    return {
      info: {},
      weekInfo: 0,
      dayInfo: '',
      startDay: moment('2020/11/2'),
      toDay: moment().format("DD-MM-YYYY"),
      lichtap: [
        {
          week: "1",
          intro: 'INTRO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 1 - LỊCH MONDAY',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 3',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 4',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 5',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 7',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 1 - Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "2",
          intro: 'INTRO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 2',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 3',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 4',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 5',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 7',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 1 - Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "3",
          intro: 'INTRO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 2',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 3',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 4',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 5',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 7',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 1 - Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "4",
          intro: 'INTRO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 2',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 3',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 4',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 5',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 1 - THỨ 7',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 1 - Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        }
      ],
    }
  },
  created () {
    this.calcToday();
  },
  computed: {

  },
  methods: {
    calcToday () {
      let today = moment('2020/11/2');
      let diffDay = today.diff(this.startDay, 'days')
      let moduloWeek = diffDay % 4;
      let moduloDays = diffDay % 7;
      this.info = { ...this.lichtap[moduloWeek].list[moduloDays] }
    }
  }
}
</script>
<style>
</style>
