<template>
  <section class="catalog">
    <p class="catalog__title">Ты сегодня покормил кота?</p>
    <div class="catalog__wrapper">
      <div class="item__wrapper">
        <div ref="selectedItem" class="item" @click="hoverTest">
          <div class="item__inner">
            <div class="item__content">
              <p class="item__lead">Сказочное заморское яство</p>
              <h3 class="item__title">Нямушка</h3>
              <p class="item__title-caption">с фуа-гра</p>
              <ul class="item__list">
                <li class="item__list-item">
                  <b>10</b> порций
                </li>
                <li class="item__list-item">Мышь в подарок</li>
              </ul>
            </div>
            <div class="item__img-wrapper">
              <div class="item__img"></div>
            </div>
          </div>
          <div class="item-option" ref="selectedOption">
            <span class="item-option__value item-option__value--large">0,5</span>
            <span class="item-option__value item-option__value">кг</span>
          </div>
        </div>
        <span class="item__caption">
          Чего сидишь? Порадуй котэ,
          <a href class="item__caption-link">купи</a>
        </span>
      </div>
    </div>
  </section>
</template>


<script>
export default {
  name: "TheItem",

  data: function() {
    return {
      activeHover: true
    };
  }
};
</script>

<style lang="scss">
@import "../assets/scss/common.scss";
@import "../assets/scss/palette.scss";
.catalog {
  max-width: 1200px;
  margin: 0 auto;
  padding-left: 40px;
  padding-right: 40px;
  padding-bottom: 69px;
  padding-top: 45px;
  &__title {
    @include margin-reset;
    color: #fff;
    text-align: center;
    font-family: "Exo 2.0 Thin";
    font-size: 36px;
    margin-bottom: 30px;
  }
  &__wrapper {
    display: flex;
    justify-content: space-between;
    width: 100%;
    flex-wrap: wrap;
  }
}
.item {
  &__wrapper {
    max-width: 320px;
    margin: 0 auto;
  }
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 9px;
  position: relative;
  margin-bottom: 15px;

  background-color: $default;
  padding: 4px;

  &:before {
    content: "";
    position: absolute;
    width: 0;
    height: 0;
    border-top: 45px solid #fff;
    border-right: 45px solid transparent;
    z-index: 1;
    top: 0px;
    left: 0px;
    transform: rotate(180deg);
  }
  &:after {
    content: "";
    position: absolute;
    width: 45px;
    height: 45px;
    top: 0;
    left: 0;
    background-image: url("../assets/Pattern.jpg");
    background-repeat: no-repeat;
  }

  &__inner {
    width: 100%;
    max-height: 480px;
    background-color: white;
    display: flex;
    flex-direction: column;
    border-radius: 9px;
    position: relative;
    padding-top: 25px;
    cursor: pointer;
    // border: 4px solid $default;

    // &:hover {
    //   border: 4px solid $default-hover;
    // }

    &:before {
      content: "";
      position: absolute;
      width: 64px;
      height: 2px;
      background-color: $default;
      border-top: 1px solid $default;
      border-bottom: 1px solid $default;
      top: 18px;
      left: -12px;
      z-index: 2;
      transform: rotate(-45deg);
      &:hover {
        background-color: $default-hover;
      }
    }
  }

  &__content {
    padding-left: 50px;
    padding-right: 15px;
  }
  &__lead {
    @include margin-reset;
    font-weight: lighter;
    font-size: 16px;
    color: #666666;
    margin-bottom: 20px;
  }
  &__title {
    @include margin-reset;
    font-size: 48px;
    margin-bottom: 15px;
  }
  &__title-caption {
    @include margin-reset;
    font-size: 24px;
    margin-bottom: 15px;
  }
  &__list {
    @include margin-reset;
    list-style: none;
  }
  &__list-item {
    font-size: 14px;
    color: #666666;
  }
  &__img-wrapper {
    overflow: hidden;
    margin-top: 20px;
    border-radius: 5px;
  }
  &__img {
    position: relative;
    display: block;
    width: 290px;
    height: 260px;
    margin: 0 auto;
    content: "";
    background-image: url("../..//src/assets/paws.png");
    left: -40px;
    border-radius: 5px;
  }

  &__caption {
    @include margin-reset;
    color: #fff;
    font-size: 13px;
    display: block;
    text-align: center;
  }
  &__caption-link {
    color: $default;
    font-weight: bold;
    text-decoration: none;
    border-bottom: 1px dashed $default;
  }
}

.item-option {
  color: #fff;
  position: absolute;
  width: 65px;
  height: 65px;
  background-color: $default;
  border-radius: 100px;
  bottom: 18px;
  right: 18px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 16px;
  cursor: pointer;
  &__value {
    font-size: 21px;
    &--large {
      font-size: 42px;
    }
  }
}

@media (max-width: 768px) {
  .catalog {
    padding-left: 0px;
    padding-right: 0px;
  }
}

@media (max-width: 1024px) {
  .catalog {
    flex-wrap: wrap;
  }

  .item {
    justify-content: center;
    margin: 0 auto;
    margin-bottom: 15px;
  }
  .item__wrapper {
    margin-bottom: 35px;
  }
}

// Состояния

.activateHover {
  background-color: $default-hover;
}
</style>
