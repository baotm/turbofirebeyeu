<template>
  <div style="">
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
        >TURBOFIRE TUẦN {{infoWelcome.week}} - BUỔI TẬP : {{infoWelcome.day}}</a>

      </div>

    </nav>

    <div class="container">
      <div>
        <b-carousel
          id="carousel-no-animation"
          style="text-shadow: 0px 0px 2px #000"
          background="#ababab"
          no-animation
          indicators
          img-width="1024"
          img-height="480"
        >
          <b-carousel-slide
            :caption="info.date.slide.caption"
            :text-html="info.date.slide.text"
            img-src="img.jpg"
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
      today: moment(),
      infoWelcome: {
        week: '',
        day: '',
      },
      weekInfo: 0,
      dayInfo: '',
      startDay: moment('2021/3/29'),
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
        },
        {
          week: "5",
          intro: 'CARDIO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 5 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE5 EZ CLASS'
                },
                video: [_vr.fire45EZ]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 5 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE30 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.fire30, _vr.sculpt30]
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
                  caption: 'TUẦN 5 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - TONE 30 CLASS'
                },
                video: [_vr.fire30, _vr.tone30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 5 - BUỔI NGÀY THỨ 6',
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
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 4 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        },
        {
          week: "6",
          intro: 'CARDIO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 55 EZ CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 30 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.fire30, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - TONE 30 CLASS'
                },
                video: [_vr.fire30, _vr.tone30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE45 CLASS'
                },
                video: [_vr.fire45]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 6 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        },
        {
          week: "7",
          intro: 'CARDIO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 30 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.fire30, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 5',
                  text: 'CORE 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.core20, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 7 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.core20, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "8",
          intro: 'RECOVERY WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 5',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE 45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 8 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.core20, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "9",
          intro: 'HIIT-2 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 15 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT15, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 15 CLASS - TONE 30 CLASS'
                },
                video: [_vr.HIIT15, _vr.tone30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 20 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 9 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        }, {
          week: "10",
          intro: 'HIIT-2 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 20 CLASS - TONE 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.tone30]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 25 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT25, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 20 CLASS - TONE 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.tone30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 10 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        },
        {
          week: "11",
          intro: 'HIIT-2 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 25 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT25, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 25 CLASS - TONE 30 CLASS'
                },
                video: [_vr.HIIT25, _vr.tone30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 25 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT25, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 11 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 30 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire30, _vr.strecth10]
              }
            },
          ]
        }, {
          week: "12",
          intro: 'HIIT-2 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 2',
                  text: 'NGHĨ'
                },
                video: []
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 4',
                  text: 'FIRE 55 EZ CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 5',
                  text: 'STRETCH 40 CLASS'
                },
                video: [_vr.strecth40]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY THỨ 7',
                  text: ' STRETCH 40 CLASS'
                },
                video: [_vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 12 - BUỔI NGÀY Chủ nhật',
                  text: 'NGHĨ GIẢI LAO'
                },
                video: []
              }
            },
          ]
        }, {
          week: "13",
          intro: 'AVANCED CARDIO ',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 13 BUỔI NGÀY THỨ 2',
                  text: 'FIRE60 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire60, _vr.abs10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - LOWER 20 CLASS'
                },
                video: [_vr.fire45EZ, _vr.lower20]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.fire30, _vr.upper20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE55 EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE 60 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire60, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 13 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        }, {
          week: "14",
          intro: 'AVANCED CARDIO WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 60 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire60, _vr.abs10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - LOWER 20 CLASS'
                },
                video: [_vr.fire45EZ, _vr.lower20]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.fire30, _vr.upper20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE 60 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire60, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 14 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        }, {
          week: "15",
          intro: 'HIIT-1 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 60 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire60, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - LOWER 20 CLASS'
                },
                video: [_vr.fire45EZ, _vr.lower20]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 5',
                  text: 'FIRE 30 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.fire30, _vr.upper20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE 60 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire60, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 15 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
          ]
        }, {
          week: "16",
          intro: 'RECOVERY WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 5',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 60 CLASS - STRETCH 10'
                },
                video: [_vr.fire60, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 7',
                  text: 'FIRE 45 EZ  CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY Chủ nhật',
                  text: 'CORE 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.core20, _vr.strecth10]
              }
            },
          ]
        }, {
          week: "16",
          intro: 'HIIT-1 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 2',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 3',
                  text: 'HIIT 20 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.HIIT20, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 20 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY THỨ 7',
                  text: 'CORE 20 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.core20, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 16 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 45 CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45, _vr.strecth10]
              }
            },
          ]
        }, {
          week: "17",
          intro: 'HIIT-3 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 15 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.HIIT15, _vr.upper20]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 45 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire45, _vr.abs10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 30 CLASS - LOWER 20 CLASS'
                },
                video: [_vr.HIIT30, _vr.lower20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 20 CLASS - SCULPT 30 CLASS'
                },
                video: [_vr.HIIT20, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 17 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 45EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.abs10]
              }
            },
          ]
        }, {
          week: "18",
          intro: 'HIIT-3 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 25 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.HIIT25, _vr.upper20]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 60 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire60, _vr.abs10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 30 CLASS - LOWER 20 CLASS'
                },
                video: [_vr.HIIT30, _vr.lower20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ class - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 25 CLASS - SCUPLT 30 CLASS'
                },
                video: [_vr.HIIT25, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 18 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 45 EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.abs10]
              }
            },
          ]
        }, {
          week: "19",
          intro: 'HIIT-3 WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 2',
                  text: 'HIIT 30 CLASS - UPPER 20 CLASS'
                },
                video: [_vr.HIIT30, _vr.upper20]
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE 60 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire60, _vr.abs10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 4',
                  text: 'NGHỈ GIẢI LAO'
                },
                video: []
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 5',
                  text: 'HIIT 30 CLASS - LOWER 20 CLASS'
                },
                video: [_vr.HIIT30, _vr.lower20]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 55EZ CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire55EZ, _vr.abs10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY THỨ 7',
                  text: 'HIIT 30 CLASS - SCUPLT 30 CLASS'
                },
                video: [_vr.HIIT30, _vr.sculpt30]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 19 - BUỔI NGÀY Chủ nhật',
                  text: 'FIRE 30 CLASS - ABS 10 CLASS'
                },
                video: [_vr.fire30, _vr.abs10]
              }
            },
          ]
        }, {
          week: "20",
          intro: 'RECOVERY WEEK',
          list: [
            {
              date: {
                day: 'monday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 2',
                  text: 'NGHỈ'
                },
                video: []
              }
            },
            {
              date: {
                day: 'tueday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 3',
                  text: 'FIRE45 EZ CLASS - STRETCH 10 CLASS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'wednesday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 4',
                  text: 'FIRE 55 EZ CLASS'
                },
                video: [_vr.fire55EZ]
              }
            },
            {
              date: {
                day: 'thursday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 5',
                  text: 'ABS 10 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.abs10, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'Friday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 6',
                  text: 'FIRE 45EZ class - STRETCH 10 CLAS'
                },
                video: [_vr.fire45EZ, _vr.strecth10]
              }
            },
            {
              date: {
                day: 'saturday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY THỨ 7',
                  text: 'ABS 10 CLASS - STRETCH 40 CLASS'
                },
                video: [_vr.abs10, _vr.strecth40]
              }
            },
            {
              date: {
                day: 'sunday',
                slide: {
                  caption: 'TUẦN 20 - BUỔI NGÀY Chủ nhật',
                  text: 'HOÀN THÀNH TURBOFIRE'
                },
                video: []
              }
            },
          ]
        },
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
      let diffDay = this.today.diff(this.startDay, 'days')
      let diffWeek = this.today.diff(this.startDay, 'weeks')
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
