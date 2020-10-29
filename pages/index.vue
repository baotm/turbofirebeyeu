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
        >NACY NGUYỄN ĐANG TRONG CHƯƠNG TRÌNH TURBOFIRE TUẦN {{infoWelcome.week}} - BUỔI TẬP : {{infoWelcome.day}}</a>

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
            img-src="https://picsum.photos/1024/480/?grayscale"
          ></b-carousel-slide>
        </b-carousel>

      </div>
      <br />
      <div
        v-for="(item,index) in info.date.video"
        :key="index"
      >

        <div>
          <h3 class="alert-heading">{{item.name}}</h3>
          <b-embed
            aspect="16by9"
            allowfullscreen
            :src="item.src"
          ></b-embed>
        </div>
      </div>
      <br />

    </div>
  </div>

</template>

<script>
import moment from 'moment'
const _vr = {
  abs10: { name: 'ABS Class Video', src: 'https://rumble.com/embed/v89hhj/?pub=38fvd' },
  core20: { name: 'Core20 Class Video', src: 'https://rumble.com/embed/v89ho7/?pub=38fvd' },
  fire30: { name: 'Fire30 Class Video', src: 'https://rumble.com/embed/v89hoh/?pub=38fvd' },
  fire45: { name: 'Fire45 Class Video', src: 'https://rumble.com/embed/v89hr9/?pub=38fvd' },
  fire45EZ: { name: 'Fire45EZ Class Video', src: 'https://rumble.com/embed/v89hrt/?pub=38fvd' },
  fire55EZ: { name: 'Fire55EZ Class Video', src: 'https://rumble.com/embed/v89hs3/?pub=38fvd' },
  fire60: { name: 'Fire60 Class Video', src: 'https://rumble.com/embed/v89hsd/?pub=38fvd' },
  getFireUp: { name: 'GETFIREUP Class Video', src: 'https://rumble.com/embed/v89hpv/?pub=38fvd' },
  HIIT15: { name: 'HIIT15 Class Video', src: 'https://rumble.com/embed/v89hpl/?pub=38fvd' },
  HIIT20: { name: 'HIIT20 Class Video', src: 'https://rumble.com/embed/v89izf/?pub=38fvd' },
  HIIT25: { name: 'HIIT25 Class Video', src: 'https://rumble.com/embed/v89i3h/?pub=38fvd' },
  HIIT30: { name: 'HIIT30 Class Video', src: 'https://rumble.com/embed/v89ie1/?pub=38fvd' },
  lower20: { name: 'LOWER20 Class Video', src: 'https://rumble.com/embed/v89iev/?pub=38fvd' },
  sculpt30: { name: 'SCULPT30 Class Video', src: 'https://rumble.com/embed/v89ikf/?pub=38fvd' },
  strecth10: { name: 'STRECTH10 Class Video', src: 'https://rumble.com/embed/v89iff/?pub=38fvd' },
  strecth40: { name: 'STRECTH40 Class Video', src: 'https://rumble.com/embed/v89ilj/?pub=38fvd' },
  tone30: { name: 'TONE30 Class Video', src: 'https://rumble.com/embed/v89ikp/?pub=38fvd' },
  upper20: { name: 'UPPER20 Class Video', src: 'https://rumble.com/embed/v89ig9/?pub=38fvd' },
}
export default {
  data () {
    return {
      info: {},
      infoWelcome: {
        week: '',
        day: '',
      },
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
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 3',
                  text: 'HIIT 15 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.HIIT15, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 4',
                  text: 'REST - REST - REST - REST '
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 1 - BUỔI NGÀY THỨ 7',
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
                  text: 'CORE20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        },
        {
          week: "2",
          intro: 'TUẦN HIIT-1',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 3',
                  text: 'HIIT20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.HIIT20, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT15 CLASS - SCULPT30 CLASS'
                },
                video: [_vr.HIIT15, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE55 EZ CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI NGÀY THỨ 7',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 2 - BUỔI CHỦ NHẬT',
                  text: 'FIRE 45 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.fire45, _vr.strecth40]
              }
            },
          ]
        },
        {
          week: "3",
          intro: 'WEEK HIIT-1',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 3',
                  text: 'HIIT 25 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.HIIT25, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 15 CLASS - TONE 30 CLASS'
                },
                video: [_vr.HIIT15, _vr.tone30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY THỨ 7',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 3 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 55EZ CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
          ]
        },
        {
          week: "4",
          intro: 'HIIT-1 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 3',
                  text: 'HIIT 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.HIIT20, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 20 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY THỨ 7',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
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
      let today = moment('2020/11/2 ');
      let diffDay = today.diff(this.startDay, 'days')
      let diffWeek = today.diff(this.startDay, 'weeks')
      let moduloWeek = diffWeek % 20;
      let moduloDays = diffDay % 7;
      this.info = { ...this.lichtap[moduloWeek].list[moduloDays] }
      this.infoWelcome.week = (moduloWeek + 1);
      this.infoWelcome.day = this.info.date.day.toUpperCase();

    }
  }
}
</script>
<style>
</style>
