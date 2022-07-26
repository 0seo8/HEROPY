<template>
  <section>
    <div class="box">
      <h2>강사님과 함께하는 러브 액츄얼리!!!!!😍</h2>
      <video
        autoplay
        loop
        muted
        src="/assets/heropy_vedio.mp4"
        controls>
      </video>
      <h2>🪄😊 감동의 장면 다시 보기!!! 😭✨</h2>
    </div>
  </section>
</template>

<style scoped lang="scss">
section {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  video {
    display: inline-block;
    width: 90%;
    padding-left: 5%;
  }
  .box {
    padding-top: 16px;
    border: 2px solid #ffdd79;
    box-sizing: border-box;
    background-color: #fff;
    position: relative;
    border-radius: 10px;
    padding-bottom: 5%;
    box-shadow: 5px 5px 5px #decd9b;

    h2 {
      margin: 10px 0 10px;
      text-align: center;
      color: #fd9023;
      font-weight: 700;
    }
  }
}
</style>
