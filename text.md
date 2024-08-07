```html
<div>
  <style>
    /* text  */
    @keyframes fadeUp_s {
      0% {
        transform: translateY(5px);
        opacity: 0;
      }

      100% {
        transform: translateY(0);
        opacity: 1;
      }
    }

    .office_chairs_box .fadeUp_s {
      animation: fadeUp_s 0.5s forwards;
    }

    .office_chairs_box {
      width: 100%;
      padding: 30px 0 80px;
      overflow: hidden;
    }

    .office_chairs_box .hidden_text {
      position: relative;
    }

    .office_chairs_box .hidden_text::after {
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      background: linear-gradient(to bottom,
          rgba(255, 255, 255, 0),
          rgba(255, 255, 255, 1));
    }

    .office_chairs_box .hidden_text2 {
      position: relative;
      height: 45px;
      overflow: hidden;
    }

    .office_chairs_box .hidden_text2::after {
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      background: linear-gradient(to bottom,
          rgba(255, 255, 255, 0),
          rgba(255, 255, 255, 1));
    }

    .office_chairs_banner {
      max-width: 1440px;
      margin: 0 auto;
    }

    .office_chairs_box .first_h1 {
      font-family: Zen-Kaku-Gothic-New-Black;
      font-size: 18px;
      font-weight: 900;
      line-height: 24px;
      color: #26333a;
      margin-top: 11px;
      margin-bottom: 11px;
    }

    .office_chairs_box .second_h2 {
      font-family: Zen-Kaku-Gothic-New-Black;
      font-size: 16px;
      font-weight: 900;
      line-height: 24px;
      color: #26333a;
      margin-top: 40px;
      margin-bottom: 8px;
    }

    .office_chairs_box h3 {
      font-family: NotoSansJP-Bold;
      font-size: 14px;
      font-weight: 900;
      line-height: 17px;
      color: #26333a;
      margin-bottom: 8px;
    }

    .office_chairs_box p {
      font-family: NotoSansJP-Regular;
      font-size: 14px;
      font-weight: 400;
      line-height: 17px;
      color: rgba(38, 51, 58, 0.5);
      margin-bottom: 8px;
    }

    .office_chairs_box .show_more {
      display: flex;
      margin: 17px 0 0;
      cursor: pointer;
    }

    .office_chairs_box .show_more .show_more_text {
      font-family: NotoSansJP-Regular;
      font-size: 12px;
      font-weight: 400;
      line-height: 15px;
    }

    .office_chairs_box .show_more .show_more_icon {
      margin-left: 11px;
      width: 11px;
      background: url("https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_down.png") no-repeat center;
    }

    .office_chairs_box .show_more_FAQ {
      display: flex;
      margin: 17px 0 0;
      cursor: pointer;
    }

    .office_chairs_box .show_more_FAQ .show_more_text_FAQ {
      font-family: NotoSansJP-Regular;
      font-size: 12px;
      font-weight: 400;
      line-height: 15px;
    }

    .office_chairs_box .show_more_FAQ .show_more_icon_FAQ {
      margin-left: 11px;
      width: 11px;
      background: url("https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_down.png") no-repeat center;
    }

    .office_chairs_box .linkStyle {
      color: #004df2;
      text-decoration: underline;
    }

    .office_chairs_box .text_blue {
      color: #004df2;
    }

    .office_chairs_box .text_bold {
      font-weight: 700;
      color: #26333a;
      opacity: 0.8;
    }

    .office_chairs_box .is_show_box {
      display: none;
    }

    .office_chairs_box .is_show_box_FAQ {
      display: none;
    }

    @media screen and (max-width: 1440px) {
      .office_chairs_banner {
        max-width: 1200px;
      }
    }

    @media screen and (max-width: 1280px) {
      .office_chairs_banner {
        max-width: 960px;
      }
    }

    @media screen and (max-width: 1024px) {
      .office_chairs_banner {
        max-width: 768.5px;
      }

      .office_chairs_box .hidden_text {
        height: 15px;
        overflow: hidden;
      }
    }

    @media screen and (max-width: 768px) {
      .office_chairs_box {
        padding: 0 0 41px;
      }

      .office_chairs_banner {
        max-width: 351px;
        padding: 32px 0 0;
        border-top: 1px solid #26333a1a;
      }

      .office_chairs_box .hidden_text {
        margin: 0;
        height: 0px;
        overflow: hidden;
      }

      .office_chairs_box .hidden_text2 {
        height: 10px;
      }

      .office_chairs_box .hidden_text3 {
        position: relative;
        margin-bottom: 0;
        height: 25px;
        overflow: hidden;
      }

      .office_chairs_box .hidden_text3::after {
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        background: linear-gradient(to bottom,
            rgba(255, 255, 255, 0),
            rgba(255, 255, 255, 1));
      }

      .office_chairs_box .show_more {
        margin: 8px 0 0;
      }

      .office_chairs_box .second_h2 {
        margin-top: 24px;
      }

      .office_chairs_box .show_more_FAQ {
        margin: 8px 0 0;
      }
    }
  </style>
  <style>
    /* table */
    * {
      margin: 0;
      padding: 0;
    }

    .fixedClass {
      position: fixed;
      top: 104px;
      z-index: 2;
    }

    .chairs_box_banner {
      margin: 0 auto;
      width: 1420px;
    }

    .table_backgroundColor_white {
      background-color: #ffffff;
    }

    .table_backgroundColor_gray {
      background-color: #f4f4f4;
    }

    .pc_show {
      display: block;
    }

    .mobile_show {
      display: none;
    }

    .chairs_box {
      max-width: 100%;
    }

    .chairs_box .chairs_title {
      padding: 60px 0 38px;
      font-size: 28px;
      font-weight: 500;
      font-family: SupremeLLSub-Medium;
      line-height: 33.6px;
      color: #26333a;
      border-top: 1px solid #26333a1a;
    }

    .chairs_box .chairs_title_mobile {
      display: none;
    }

    .chairs_box .chairs_table .header_mask {
      display: none;
      width: 20px;
      height: 140px;
      background: #fff;
      position: fixed;
      top: 92px;
      left: 0;
      z-index: 3;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox {
      display: flex;
      justify-content: space-between;
      background: #f4f4f4;
      border-radius: 4px;
      /* padding-bottom: 2px; */
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture0 {
      width: 175px;
      margin: 10px 0 10px 24px;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 140px;
      margin: 10px 0 10px;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 img {
      height: 120px;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1:last-child {
      margin-right: 30px;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #26333a;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text0 {
      width: 175px;
      margin: 17.5px 0 17.5px 24px;
      font-size: 14px;
      font-family: Moderat-Regular;
      font-weight: 700;
      line-height: 16.8px;
      color: #ffffff;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 {
      position: relative;
      width: 140px;
      margin: 14px 0 14px;
      font-size: 16px;
      font-family: Moderat-Regular;
      font-weight: 700;
      line-height: 24px;
      text-align: center;
      color: #ffffff;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 img {
      width: 16px;
      height: 16px;
      position: absolute;
      top: 2px;
      left: 15px;
    }

    .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1:last-child {
      margin-right: 20px;
    }

    .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text0 {
      width: 175px;
      margin: 14px 0 14px 24px;
      font-family: Moderat-Regular;
      font-weight: 700;
      font-size: 14px;
      line-height: 16.8px;
      color: #26333a;
    }

    .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1 {
      width: 140px;
      margin: 14px 0 14px;
      font-family: Moderat-Regular;
      font-size: 14px;
      font-weight: 400;
      line-height: 16.8px;
      text-align: center;
      color: #26333acc;
    }

    .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1:last-child {
      margin-right: 20px;
    }

    .button_box {
      display: none;
      max-width: 100%;
      margin: 32px 20px;
    }

    .button_box .button_text {
      font-family: Moderat-Regular;
      font-weight: 400;
      font-size: 12px;
      line-height: 14.4px;
      color: #a3a3a3;
      text-align: center;
      margin-bottom: 8px;
    }

    .button_box .button_push {
      height: 32px;
      background: #26333a;
      border-radius: 40px;
    }

    .button_box .button_push .button_puhs_link {
      display: inline-block;
      width: 100%;
      height: 100%;
      text-align: center;
      line-height: 32px;
      text-decoration: none;
      color: #ffffff;
      font-family: Moderat-Regular;
      font-weight: 700;
      font-size: 14px;
      letter-spacing: 0.05em;
    }

    @media screen and (max-width: 1440px) {
      .chairs_box_banner {
        width: 1200px;
      }

      .chairs_box .chairs_title {
        padding: 50px 0 40px;
        font-size: 24px;
        line-height: 28.8px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox {
        border-radius: 0;
        /* padding-bottom: 0; */
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture0 {
        width: 100px;
        margin: 8px 0 5px 24px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 {
        width: 90px;
        margin: 8px 0 5px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 img {
        width: 90px;
        height: 90px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1:last-child {
        margin-right: 16px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text0 {
        width: 100px;
        margin: 9.5px 0 9.5px 24px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 {
        width: 90px;
        margin: 9.5px 0 9.5px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 img {
        height: 14px;
        top: -2px;
        left: 2px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1:last-child {
        margin-right: 16px;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text0 {
        width: 100px;
        margin: 13.5px 0 13.5px 24px;
        font-size: 12px;
        line-height: 14.4px;
        word-break: break-all;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1 {
        width: 90px;
        margin: 13.5px 0 13.5px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1:last-child {
        margin-right: 16px;
      }

      .pc_show {
        display: none;
      }

      .mobile_show {
        display: block;
      }
    }

    @media screen and (max-width: 1280px) {
      .chairs_box_banner {
        max-width: 960px;
      }
    }

    @media screen and (max-width: 1024px) {
      .fixedClass {
        top: 92px;
      }

      .chairs_box_banner {
        width: 768px;
      }

      .chairs_box .chairs_title {
        padding: 40px 0 40px;
        font-size: 18px;
        line-height: 21.6px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture0 {
        width: 90px;
        margin: 8px 0 6px 24px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 {
        width: 90px;
        margin: 8px 0 6px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1 img {
        height: 90px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_pictureBox .chairs_table_header_picture1:last-child {
        margin-right: 14px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text0 {
        width: 98px;
        margin: 9.5px 0 9.5px 24px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 {
        width: 90px;
        margin: 9.5px 0 9.5px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1 img {
        height: 14px;
        top: -2px;
        left: 2px;
      }

      .chairs_box .chairs_table .chairs_table_header .chairs_table_header_textBox .chairs_table_header_text1:last-child {
        margin-right: 15px;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text0 {
        width: 98px;
        margin: 13.5px 0 13.5px 24px;
        font-size: 12px;
        line-height: 14.4px;
        word-break: break-all;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1 {
        width: 90px;
        margin: 13.5px 0 13.5px;
        font-size: 12px;
        line-height: 14.4px;
      }

      .chairs_box .chairs_table .chairs_table_body .chairs_table_body_textBox .chairs_table_body_text1:last-child {
        margin-right: 16px;
      }
    }

    @media screen and (max-width: 768px) {
      .chairs_box {
        max-width: 100%;
        overflow-x: auto;
        margin-left: 20px;
        margin-bottom: 32px;
      }

      .chairs_box .chairs_title {
        display: none;
      }

      .chairs_box .chairs_title_mobile {
        display: block;
        padding: 32px 0 32px;
        font-size: 18px;
        line-height: 21.6px;
        font-weight: 500;
        font-family: SupremeLLSub-Medium;
        color: #26333a;
        border-top: 1px solid #26333a1a;
      }

      .chairs_box_banner {
        width: 623px;
      }

      .button_box {
        display: block;
      }

      .slide_block {
        margin-bottom: 5px;
      }
    }

    @media screen and (max-width: 1440px) {
      .office_chairs_banner {
        max-width: 1200px;
      }

      .office_chairs_box {
        padding: 50px 0 60px;
      }

      .office_chairs_box .second_h2 {
        margin-top: 40px;
      }
    }

    @media screen and (max-width: 1280px) {
      .office_chairs_banner {
        max-width: 960px;
      }
    }

    @media screen and (max-width: 1024px) {
      .office_chairs_banner {
        max-width: 768.5px;
      }

      .hidden_text {
        height: 15px;
        overflow: hidden;
      }

      .office_chairs_box {
        padding: 40px 0 60px;
      }
    }

    @media screen and (max-width: 767px) {
      .compare-wrapper {
        padding-bottom: 32px;
      }

      .office_chairs_box {
        padding: 0 0 60px;
      }

      .office_chairs_banner {
        max-width: 351px;
        padding: 32px 0 0;
        border-top: 1px solid #26333a1a;
      }

      .office_chairs_box .hidden_text {
        margin: 0;
        height: 0px;
        overflow: hidden;
      }

      .office_chairs_box .hidden_text2 {
        height: 65px;
      }

      .office_chairs_box .hidden_text3 {
        position: relative;
        margin-bottom: 0;
        height: 90px;
        overflow: hidden;
      }

      .office_chairs_box .hidden_text3::after {
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        background: linear-gradient(to bottom,
            rgba(255, 255, 255, 0),
            rgba(255, 255, 255, 1));
      }

      .office_chairs_box .show_more {
        margin: 17px 0 0;
      }

      .office_chairs_box .second_h2 {
        margin-top: 33px;
      }

      .office_chairs_box .show_more_FAQ {
        margin: 17px 0 0;
      }

      /* .office_chairs_box h3 {
      margin: 9px 0;
    } */
    }
  </style>

  <!-- table -->
  <div class="chairs_box">
    <div class="chairs_box_banner">
      <div class="chairs_title">FlexiSpot オフィスチェア比較表</div>
      <div class="chairs_title_mobile">FlexiSpot オフィスチェア比較表</div>
      <div class="chairs_table">
        <div class="placeholder" style="height: 136px">
          <div class="header_mask" style="display: none"></div>
          <div class="chairs_table_header">
            <div class="chairs_table_header_pictureBox">
              <div class="chairs_table_header_picture0"></div>
              <div class="chairs_table_header_picture1">
                <img src="https://s3.springbeetle.asia/asia/trantor/attachments/JP/chair-20240807-jp-4.png" alt="" />
              </div>
              <div class="chairs_table_header_picture1">
                <img src="https://s3.springbeetle.asia/asia/trantor/attachments/JP/chair-20240807-jp-5.png" alt="" />
              </div>
              <div class="chairs_table_header_picture1">
                <img src="https://s3.springbeetle.asia/asia/trantor/attachments/JP/chair-20240807-jp-1.png" alt="" />
              </div>
              <div class="chairs_table_header_picture1">
                <img src="https://s3.springbeetle.asia/asia/trantor/attachments/JP/chair-20240807-jp-2.png" alt="" />
              </div>
              <div class="chairs_table_header_picture1">
                <img src="https://s3.springbeetle.asia/asia/trantor/attachments/JP/chair-20240807-jp-3.png" alt="" />
              </div>
            </div>
            <div class="chairs_table_header_textBox">
              <div class="chairs_table_header_text0"></div>
              <div class="chairs_table_header_text1">
                <!-- <img
                  src="https://s3.springbeetle.eu/prod-eu-s3/trantor/attachments/IT/Group 10128439.png"
                  alt=""
                /> -->
                C7・C7 Air・C7 Pro
              </div>
              <div class="chairs_table_header_text1">C2</div>
              <div class="chairs_table_header_text1">OC3</div>
              <div class="chairs_table_header_text1">BS12</div>
              <div class="chairs_table_header_text1">C5</div>
            </div>
          </div>
        </div>
        <div class="chairs_table_body">
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0">定価</div>
            <div class="chairs_table_body_text1">51,800</div>
            <div class="chairs_table_body_text1">64800</div>
            <div class="chairs_table_body_text1">21800</div>
            <div class="chairs_table_body_text1">54800</div>
            <div class="chairs_table_body_text1">33980</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0">カラー</div>
            <div class="chairs_table_body_text1">ブラック、グレー</div>
            <div class="chairs_table_body_text1">ブラック</div>
            <div class="chairs_table_body_text1">ブラック、グレー</div>
            <div class="chairs_table_body_text1">ブラック、グレー</div>
            <div class="chairs_table_body_text1">ブラック、グレー</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">サイズ</div>
            <div class="chairs_table_body_text0 mobile_show">サイズ</div>
            <div class="chairs_table_body_text1">66×66×119.5<br />~134.5cm</div>
            <div class="chairs_table_body_text1">
              64cm×59.5cm× <br />112.5~126cm
            </div>
            <div class="chairs_table_body_text1">
              OC3-Mesh : <br />61×66×114-124cm OC3-Foam :
              <br />61×63.5×112-122cm
            </div>
            <div class="chairs_table_body_text1">66cm×65cm×<br />114~128cm</div>
            <div class="chairs_table_body_text1">
              72.5cm×67.5cm×<br />114.5~129.5cm
            </div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">座面高さ</div>
            <div class="chairs_table_body_text0 mobile_show">座面高さ</div>
            <div class="chairs_table_body_text1">47.5~56cm</div>
            <div class="chairs_table_body_text1">42~50.5cm</div>
            <div class="chairs_table_body_text1">
              OC3-Mesh : 47-57cm<br />
              OC3-Foam : 45.5-55.5cm
            </div>
            <div class="chairs_table_body_text1">45~53.5cm</div>
            <div class="chairs_table_body_text1">43.5~53.5cm</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">座面素材</div>
            <div class="chairs_table_body_text0 mobile_show">座面素材</div>
            <div class="chairs_table_body_text1">
              モールドウレタン、メッシュ
            </div>
            <div class="chairs_table_body_text1">モールドウレタン</div>
            <div class="chairs_table_body_text1">
              ウレタンフォーム、メッシュ
            </div>
            <div class="chairs_table_body_text1">
              メッシュ、モールドウレタン
            </div>
            <div class="chairs_table_body_text1">ウレタンフォーム</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">ロッキング機能</div>
            <div class="chairs_table_body_text0 mobile_show">
              ロッキング機能
            </div>
            <div class="chairs_table_body_text1">無段階固定可能</div>
            <div class="chairs_table_body_text1">4段階固定可能</div>
            <div class="chairs_table_body_text1">3段階固定可能</div>
            <div class="chairs_table_body_text1">3段階固定可能</div>
            <div class="chairs_table_body_text1">2段階固定可能</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">
              リクライニング角度
            </div>
            <div class="chairs_table_body_text0 mobile_show">
              リクライニング角度
            </div>
            <div class="chairs_table_body_text1">90°-128°</div>
            <div class="chairs_table_body_text1">90°-130°</div>
            <div class="chairs_table_body_text1">90°-125°</div>
            <div class="chairs_table_body_text1">90°-124°</div>
            <div class="chairs_table_body_text1">90°-116°</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">ランバーサポート</div>
            <div class="chairs_table_body_text0 mobile_show">
              ランバーサポート
            </div>
            <div class="chairs_table_body_text1">前後</div>
            <div class="chairs_table_body_text1">前後</div>
            <div class="chairs_table_body_text1">上下</div>
            <div class="chairs_table_body_text1">上下</div>
            <div class="chairs_table_body_text1">上下・前後</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">アームレスト</div>
            <div class="chairs_table_body_text0 mobile_show">アームレスト</div>
            <div class="chairs_table_body_text1">
              C7/C7Air：4D<br />
              C7Pro：3D
            </div>
            <div class="chairs_table_body_text1">4D</div>
            <div class="chairs_table_body_text1">1D</div>
            <div class="chairs_table_body_text1">3D</div>
            <div class="chairs_table_body_text1">3D</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">ヘッドレスト</div>
            <div class="chairs_table_body_text0 mobile_show">ヘッドレスト</div>
            <div class="chairs_table_body_text1">2D</div>
            <div class="chairs_table_body_text1">2D</div>
            <div class="chairs_table_body_text1">2D</div>
            <div class="chairs_table_body_text1">1D</div>
            <div class="chairs_table_body_text1">2D</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">座面奥行調節</div>
            <div class="chairs_table_body_text0 mobile_show">座面奥行調節</div>
            <div class="chairs_table_body_text1">○</div>
            <div class="chairs_table_body_text1">○</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">○</div>
            <div class="chairs_table_body_text1">×</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray slide_block">
            <div class="chairs_table_body_text0 pc_show">座面前傾角度調節</div>
            <div class="chairs_table_body_text0 mobile_show">
              座面前傾角度調節
            </div>
            <div class="chairs_table_body_text1">○</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white">
            <div class="chairs_table_body_text0 pc_show">オットマン付き</div>
            <div class="chairs_table_body_text0 mobile_show">
              オットマン付き
            </div>
            <div class="chairs_table_body_text1">
              C7/C7Air:×<br />
              C7Pro：○
            </div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">ハンガー付き</div>
            <div class="chairs_table_body_text0 mobile_show">ハンガー付き</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">○</div>
            <div class="chairs_table_body_text1">×</div>
            <div class="chairs_table_body_text1">×</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_white slide_block">
            <div class="chairs_table_body_text0 pc_show">耐荷重</div>
            <div class="chairs_table_body_text0 mobile_show">耐荷重</div>
            <div class="chairs_table_body_text1">130kg</div>
            <div class="chairs_table_body_text1">136kg</div>
            <div class="chairs_table_body_text1">136kg</div>
            <div class="chairs_table_body_text1">136kg</div>
            <div class="chairs_table_body_text1">125kg</div>
          </div>
          <div class="chairs_table_body_textBox table_backgroundColor_gray">
            <div class="chairs_table_body_text0 pc_show">保証年数</div>
            <div class="chairs_table_body_text0 mobile_show">保証年数</div>
            <div class="chairs_table_body_text1">3年</div>
            <div class="chairs_table_body_text1">5年</div>
            <div class="chairs_table_body_text1">3年</div>
            <div class="chairs_table_body_text1">3年</div>
            <div class="chairs_table_body_text1">3年</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- <div class="button_box">
    <div class="button_text">Pour en savoir plus, cliquez ici</div>
    <div class="button_push">
      <a
        class="button_puhs_link"
        target="_blank"
        href="https://www.flexispot.fr/guide-achat-chaise"
        >GUIDE D'ACHAT</a
      >
    </div>
  </div> -->
  <!-- text -->
  <div class="office_chairs_box">
    <div class="office_chairs_banner">
      <h1 class="first_h1">オフィスチェア</h1>
      <p class="hidden_text3 hidden_text">
        ランバーサポートで腰を支え、自然で理想的な姿勢を維持し、快適かつ高い生産性を叶えるオフィスチェア。通気性のある生地、エルゴノミクス（人間工学）に基づいたデザイン、多段階調整を特徴とし、作業効率を向上させ身体の不快感や痛みを防ぎます。
      </p>
      <div class="is_show_box">
        <p>
          高品質、高機能、高コスパのオフィスチェアをお探しの方にFlexiSpotは最適です。FlexiSpotのオフィスチェアシリーズは、特殊加工された生地を採用し、通気性に優れつつ柔軟性も兼ね備えています。また、FlexiSpotのワーキング
          チェアは、人間工学に基づいて設計されています。S字カーブの腰サポートや調整可能なヘッドレスト、アームレストにより、長時間の作業も快適に行えます。また、エルゴノミクスと美学を融合したFlexiSpotのデスク
          椅子は、豊富な色展開とスタイルから選べ、ユーザーの幅広い好みに対応します。在宅ワークに最適なチェアとして、FlexiSpotが優れた選択肢であることをご提案いたします。
        </p>
      </div>
      <div class="show_more">
        <div class="show_more_text">もっと見る</div>
        <div class="show_more_icon"></div>
      </div>

      <h2 class="second_h2">FAQ</h2>
      <h3>オフィスチェアの種類</h3>
      <p class="hidden_text2">
        オフィスチェアは、さまざまなニーズに合わせて設計されています。主な種類は次のとおりです：<br />
        <span class="text_bold">タスクチェア:</span>
        調整可能な高さと基本的な腰サポートを備えた一般的なデスクチェアです。主に在宅ワークや一般的なオフィス作業に適しています。<br />
        <span class="text_bold">エグゼクティブチェア:</span>
        高背もたれと高級素材（革など）を特徴とし、快適さと見た目を重視した大型のデスクチェアです。重要なビジネスミーティングで使用されることが多いワーキングチェアです。<br />
        <span class="text_bold">エルゴノミクスチェア:</span>
        人間工学に基づいて設計され、調整可能なアームレスト、ヘッドレスト、腰サポートなどの機能を備えています。身体の不快感を防ぐために設計されており、長時間の座り作業に最適のワーキングチェアです。<br />
        <span class="text_bold">メッシュチェア:</span>
        通気性のあるメッシュバックを特徴とし、快適さとモダンなデザインを兼ね備えています。長時間の座り作業に最適なパソコン作業用の椅子です。<br />
        <span class="text_bold">会議用チェア:</span>
        調整機能が少なく、移動も簡単なコンパクト設計です。主に会議室や短時間の会議で使用されます。
      </p>
      <div class="is_show_box_FAQ" style="display: none">
        <h3>ワークチェアは長期使用に適しているか？</h3>
        <p>
          適切な設計とエルゴノミクスを備えたワーク
          チェアは、長期間の使用に適しています。高品質で機能性に富んだFlexiSpotの人間工学オフィスチェアは、特に長時間の使用に特化して設計されています。パソコン作業用の椅子は、調整可能な腰サポート、アームレスト、ヘッドレストなどの機能を備えており、これにより身体の自然な姿勢に合わせて調整できます。体重を適切に分散することにより、負担を軽減し、不快感を防ぎます。
        </p>
        <h3>オフィスチェアの素材</h3>
        <p>
          オフィスチェアの主な素材には、座面や背もたれにはフォーム（発泡ウレタン）、ジェル、メッシュなどが使用され、カバーには布地、合成皮革、本革がつかわれています。フレームにはプラスチックやアルミニウムが一般的で、それぞれの特性に応じて快適性や耐久性が考慮されています。FlexiSpotのオフィスチェアは、通気性を考慮してメッシュ素材を使用し、さらにエルゴノミクスを重視して腰のサポートや高密度スポンジクッションを組み合わせています。
        </p>
        <h3>オフィスチェアの掃除方法・メンテナンスとは？</h3>
        <p>
          オフィスチェアを掃除する際には、素材に応じたメンテナンスが重要です。布製の場合は、まず掃除機でホコリを取り除き、中性洗剤を薄めたぬるま湯で汚れを拭き取ります。メッシュ製の場合は、水洗いを避けてシートクリーナーやウェットティッシュで軽く汚れを拭き取ります。合成皮革は水拭きが可能で、専用のクリーナーを使うか、乾いた布で汚れを拭きます。本革製品は水に弱いため、乾拭きが基本です。定期的な手入れでチェアの機能性と寿命を保ちましょう。
        </p>
        <h3>オフィスチェアの選び方・ポイント</h3>
        <p>
          オフィスチェアを選ぶ際は、下記を参考にしてみてください：<br />
          <span class="text_bold">エルゴノミクス（人間工学）機能:</span>
          正しい姿勢を保つために必要な要素です。体型に合わせた高さ調整、腰のサポート、ヘッドレスト、アームレストなど、人間工学に基づいた豊富な調節機能が備わったワーキングチェアを選びましょう。<br />
          <span class="text_bold">素材:</span>
          使用する素材は、求める通気性や耐久性によって選びましょう。例えば、メッシュ素材は通気性がよく、革素材は耐久性とスタイリッシュな外観を兼ね備えます。<br />
          <span class="text_bold">ベースとキャスター:</span>
          安定性と移動のしやすさを確保するために、頑丈で安定感のあるベースと、スムーズに動く高品質のキャスターを選びましょう。<br />
          <span class="text_bold">メッシュチェア:</span>
          通気性のあるメッシュバックを特徴とし、快適さとモダンなデザインを兼ね備えています。長時間の座り作業に最適なパソコン作業用の椅子です。<br />
          <span class="text_bold">サイズフィット:</span>
          自分の体格や、一緒に使用するデスクの寸法に合ったサイズのチェアを選ぶことが大切です。椅子が体にフィットし、快適に作業できるようになります。<br />
          <span class="text_bold">美観:</span>
          オフィスの装飾や使用シーンに合ったデザインのチェアを選びましょう。オフィスの雰囲気と調和し、オフィス全体の印象を良くします。
        </p>
      </div>
      <div class="show_more_FAQ">
        <div class="show_more_text_FAQ">もっと見る</div>
        <div class="show_more_icon_FAQ" style="
            background: url('https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_down.png')
              center center no-repeat;
          "></div>
      </div>
    </div>
  </div>

  <script>
    //  <!-- table -->
    var chairs_table_header = document.querySelector(".chairs_table_header")
    var chairs_table_body = document.querySelector(".chairs_table_body")
    var placeholder = document.querySelector(".placeholder")
    var chairs_box = document.querySelector(".chairs_box")
    var header_mask = document.querySelector(".header_mask")

    document.addEventListener("scroll", function () {
      if (window.pageYOffset < placeholder.offsetTop) {
        chairs_table_header.classList.remove("fixedClass")
        chairs_table_header.classList.remove("chairs_box_banner")
        // 遮罩层
        header_mask.style.display = "none"
      } else if (
        window.pageYOffset >=
        placeholder.offsetTop + chairs_table_body.offsetHeight
      ) {
        chairs_table_header.classList.remove("fixedClass")
        chairs_table_header.classList.remove("chairs_box_banner")
        // 遮罩层
        header_mask.style.display = "none"
      } else if (window.pageYOffset >= chairs_table_header.offsetTop) {
        chairs_table_header.classList.add("fixedClass")
        chairs_table_header.classList.add("chairs_box_banner")
        placeholder.style.height = chairs_table_header.offsetHeight + "px"
        // 遮罩层
        header_mask.style.display = "block"
      }
    })

    chairs_box.addEventListener("scroll", function () {
      var distance_X = chairs_box.scrollLeft
      chairs_table_header.style.left = -distance_X + 20 + "px"
    })

    //  <!-- text -->
    var show_more = document.querySelector(".office_chairs_box .show_more")
    var show_more_FAQ = document.querySelector(
      ".office_chairs_box .show_more_FAQ"
    )
    var hidden_text = document.querySelector(".office_chairs_box .hidden_text")
    var hidden_text2 = document.querySelector(
      ".office_chairs_box .hidden_text2"
    )
    var hidden_text3 = document.querySelector(
      ".office_chairs_box .hidden_text3"
    )
    var is_show_box = document.querySelector(".office_chairs_box .is_show_box")
    var is_show_box_FAQ = document.querySelector(
      ".office_chairs_box .is_show_box_FAQ"
    )
    var show_more_icon = document.querySelector(
      ".office_chairs_box .show_more_icon"
    )
    var show_more_text = document.querySelector(
      ".office_chairs_box .show_more_text"
    )
    var show_more_icon_FAQ = document.querySelector(
      ".office_chairs_box .show_more_icon_FAQ"
    )
    var show_more_text_FAQ = document.querySelector(
      ".office_chairs_box .show_more_text_FAQ"
    )

    var is_office_Show = true
    var is_FAQ_Show = true

    show_more.addEventListener("click", function () {
      if (is_office_Show) {
        is_office_Show = false
        hidden_text.classList.remove("hidden_text")
        hidden_text3.classList.remove("hidden_text3")
        is_show_box.style.display = "block"
        is_show_box.classList.add("fadeUp_s")
        show_more_icon.style.background =
          "url(https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_up.png) no-repeat center"
        show_more_text.innerHTML = "閉じる"
      } else {
        is_office_Show = true
        hidden_text.classList.add("hidden_text")
        hidden_text3.classList.add("hidden_text3")
        is_show_box.style.display = "none"
        is_show_box.classList.remove("fadeUp_s")
        show_more_icon.style.background =
          "url(https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_down.png) no-repeat center"
        show_more_text.innerHTML = "もっと見る"
      }
    })

    show_more_FAQ.addEventListener("click", function () {
      if (is_FAQ_Show) {
        is_FAQ_Show = false
        hidden_text2.classList.remove("hidden_text2")
        is_show_box_FAQ.style.display = "block"
        is_show_box_FAQ.classList.add("fadeUp_s")
        show_more_icon_FAQ.style.background =
          "url(https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_up.png) no-repeat center"
        show_more_text_FAQ.innerHTML = "閉じる"
      } else {
        is_FAQ_Show = true
        hidden_text2.classList.add("hidden_text2")
        is_show_box_FAQ.style.display = "none"
        is_show_box_FAQ.classList.remove("fadeUp_s")
        show_more_icon_FAQ.style.background =
          "url(https://s3.springbeetle.com/prod-us-bucket/trantor/attachments/CA/Vector_down.png) no-repeat center"
        show_more_text_FAQ.innerHTML = "もっと見る"
      }
    })
  </script>
</div>
```

