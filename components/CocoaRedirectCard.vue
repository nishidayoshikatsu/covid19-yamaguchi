<template>
  <div>
    <client-only>
      <div class="AppInstall">
        <div class="AppInstall-heading">
          <h3 class="AppInstall-title">
            {{ $t('新型コロナウイルス接触確認アプリ') }}
          </h3>
          <h4 class="AppInstall-subtitle">( {{ $t('厚生労働省') }} )</h4>
        </div>
        <div class="AppInstall-content">
          <div class="AppInstall-block AppInstall-block-description">
            <p>
              {{
                $t(
                  '厚生労働省が公式提供する、新型コロナウイルス陽性登録した人との接触をお知らせするアプリです。'
                )
              }}
            </p>
            <p>
              {{
                $t(
                  'このアプリを設定した人どうしの接触（1m以内、15分以上）が記録されます。新型コロナウイルスに陽性と判定されましたら本アプリに匿名で登録することができます。最近接触した人の中に陽性登録した人がいましたら、通知と適切な行動をお知らせします。'
                )
              }}
            </p>
          </div>
          <div class="AppInstall-block AppInstall-buttons">
            <a
              href="https://apps.apple.com/jp/app/%E6%96%B0%E5%9E%8B%E3%82%B3%E3%83%AD%E3%83%8A%E3%82%A6%E3%82%A4%E3%83%AB%E3%82%B9%E6%8E%A5%E8%A7%A6%E7%A2%BA%E8%AA%8D%E3%82%A2%E3%83%97%E3%83%AA/id1516764458?mt=8"
              class="AppStore"
              target="_blank"
              rel="noopener noreferrer"
            />
            <a
              href="https://play.google.com/store/apps/details?id=jp.go.mhlw.covid19radar"
              class="GooglePlay"
              target="_blank"
              rel="noopener noreferrer"
              ><img
                alt="Google Play で手に入れよう"
                src="/ja_badge_web_generic.png"
            /></a>
          </div>
        </div>
      </div>
    </client-only>
  </div>
</template>

<style lang="scss">
$mediumLarge: 900;
@function px2vw($px, $vw: $mediumLarge) {
  @return $px / $vw * 100vw;
}
.AppInstall {
  @include card-container();
  padding: 10px;
  margin-bottom: 20px;
  .AppInstall-heading {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 12px;
    picture {
      width: 52px;
      height: 52px;
      margin-right: 10px;
    }
    .AppInstall-title {
      display: flex;
      align-items: center;
      padding: 12px;
      color: $gray-2;
      @include card-h2();
      &-icon {
        margin: 3px;
      }
    }
    .AppInstall-subtitle {
      color: $gray-2;
      @include card-h2();
    }
  }
  .AppInstall-buttons {
    position: relative;
    z-index: 3;
    display: block;
    padding: px2vw(5) px2vw(10) px2vw(5) px2vw(25);
    margin-left: px2vw(16);
    font-size: px2vw(14);
    text-align: center;
    .AppStore {
      display: inline-block;
      width: 135px;
      height: 40px;
      overflow: hidden;
      background: url('/badge-lrg.svg') no-repeat;
    }
    .GooglePlay {
      display: inline-block;
      width: auto;
      height: 40px;
      overflow: hidden;
      img {
        width: auto;
        height: 58px;
        object-fit: cover;
        object-position: 0 -9px;
      }
    }
  }
  .AppInstall-content {
    @include font-size(14);
    display: flex;
    flex-wrap: wrap;
    .AppInstall-block {
      flex: 1 1 100%;
      padding: 12px;
      @include largerThan($large) {
        &-description {
          flex-basis: 40%;
        }
      }
    }
  }
}
</style>
