<script>
export default {
  props: {
    cardName: String,
    cardStatus: String,
    cardGender: String,
    cardSpecies: String,
    cardImage: String,
    cardLocation: String,
  },
};
</script>

<template>
  <div class="container">
    <div class="card">
      <div class="imgBx">
        <img :src="cardImage" :alt="cardName" />
      </div>
      <div class="name">
        <h2>{{ cardName }}</h2>
        <div class="status">
          <h3>{{ cardStatus }}</h3>
        </div>
        <div class="gender">
          <h3>{{ cardGender }}</h3>
        </div>
        <div class="gender">
          <h3>{{ cardLocation }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  position: relative;

  .card {
    position: relative;
    width: 350px;
    height: 450px;
    background: #232323;
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 1px 1px 10px 13px rgb(255, 255, 255);

    &:before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #d5d5d5;
      clip-path: circle(450px at 50% 80%);
      transition: 0.3s ease;
    }

    &:hover:before {
      clip-path: circle(100px at 50% -20%);
    }

    &:after {
      content: url("https://pendragongamestudio.com/it/wp-content/uploads/sites/2/2019/05/0wzY6AgU.png");
      position: absolute;
      top: 30%;
      left: -40%;
      transform: scale(0.4);
    }
    &hover:after {
      transform: translateY(20px);
    }

    .imgBx {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      z-index: 9999;
      width: 100%;
      height: 220px;
      transition: 0.3s;
      border-radius: 10px;

      img {
        position: absolute;
        top: 55%;
        left: 50%;
        transform: translate(-50%, -50%) rotate(-0deg);
        width: 280px;
        border-radius: 10px;
      }
    }

    .name {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 350px;
      text-align: center;
      transition: 0.6s;
      z-index: 10;

      h2 {
        position: relative;
        font-weight: 600;
        font-size: 2rem;
        color: #ffffff;
        margin-bottom: 10px;
      }

      .status,
      .gender {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 8px 20px;
        transition: 0.5s;
        opacity: 0;
        visibility: hidden;
        padding-top: 0;
        padding-bottom: 0;

        h3 {
          color: #b0b0b0;
          font-weight: 600;
          font-size: 18px;
          text-transform: uppercase;

          margin-right: 10px;
        }
      }

      .gender span {
        width: 20px;
        height: 20px;
        background: rgb(255, 255, 255);
        border-radius: 50%;
        margin: 0 5px;
      }
    }

    &:hover .imgBx {
      top: 1%;
      transform: translateY(0%);
      transform: scale(90%);
    }

    &:hover .name {
      height: 180px;
      .status {
        opacity: 1;
        visibility: visible;
        transition-delay: 0.3s;
      }

      .gender {
        opacity: 1;
        visibility: visible;
        transition-delay: 0.6s;
      }
    }
  }
}
</style>./card.vue