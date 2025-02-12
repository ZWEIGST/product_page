<template>
  <div class="product-header">
    <div class="product-header__logo">
      <img
        src="https://i.postimg.cc/kXcBHFLw/Screenshot-2022-11-15-at-13-25-2.png"
        alt="logo stik"
      />
    </div>
    <div class="product-header__nav">
      <div class="product-header__nav-search">
        <a href="">
          <svg
            width="14"
            height="14"
            viewBox="0 0 14 14"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M5.39368 0C8.37252 0 10.7874 2.41483 10.7874 5.39368C10.7874 6.94385 10.1334 8.34128 9.08631 9.32514L13.1591 13.5L12.4857 14L8.4371 9.84731C7.57085 10.4404 6.52278 10.7874 5.39368 10.7874C2.41483 10.7874 0 8.37252 0 5.39368C0 2.41483 2.41483 0 5.39368 0ZM5.39368 9.95756C7.91424 9.95756 9.95756 7.91424 9.95756 5.39368C9.95756 2.87311 7.91424 0.829796 5.39368 0.829796C2.87311 0.829796 0.829796 2.87311 0.829796 5.39368C0.829796 7.91424 2.87311 9.95756 5.39368 9.95756Z"
              fill="black"
            />
          </svg>
        </a>
      </div>
      <div class="product-header__nav-favorite" v-show="isDesktop">
        <a href="">
          <svg
            width="11"
            height="14"
            viewBox="0 0 11 14"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M5.38273 10.2994L10.7655 14V0H0V14L5.38273 10.2994ZM0.897121 12.3036L5.38273 8.97606L9.86834 12.3036V0.881352H0.897121V12.3036Z"
              fill="black"
            />
          </svg>
        </a>
      </div>
      <div class="product-header__nav-cab">
        <a href="">
          <svg
            width="14"
            height="15"
            viewBox="0 0 14 15"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M11.8025 11.7554C12.0763 12.9126 12.1688 14.1862 12.1688 15H13.125C13.125 14.7285 13.1155 14.4101 13.0936 14.0625C13.045 13.2931 12.9351 12.3804 12.7307 11.5166C12.5824 10.8895 12.3799 10.2692 12.1036 9.74302C11.8295 9.22078 11.4613 8.7508 10.9628 8.48559C10.5582 8.27027 10.2752 8.11652 10.0828 8.00925V7.52186C10.1692 7.44741 10.2446 7.36412 10.3074 7.28726C10.4613 7.09871 10.6121 6.85666 10.7447 6.58244C11.0088 6.03567 11.2236 5.31271 11.2236 4.54543C11.2236 2.6195 9.5213 0 6.5625 0C3.6037 0 1.90137 2.6195 1.90137 4.54543C1.90137 5.31271 2.11613 6.03567 2.38033 6.58244C2.51285 6.85666 2.66362 7.09871 2.81758 7.28726C2.88039 7.36412 2.95583 7.44741 3.0422 7.52186V8.00925C2.84972 8.11652 2.56685 8.27027 2.16218 8.48559C1.6637 8.7508 1.29552 9.22078 1.02135 9.74302C0.745059 10.2692 0.542613 10.8895 0.39428 11.5166C0.189935 12.3804 0.0800307 13.2931 0.0314164 14.0625C0.00945319 14.4101 0 14.7285 0 15H0.956207C0.956207 14.1862 1.04872 12.9126 1.32247 11.7554C1.45935 11.1769 1.63717 10.6462 1.85999 10.2218C2.08493 9.79351 2.3347 9.51308 2.59678 9.3736C3.30264 8.99802 3.78533 8.6863 3.96514 8.57017L3.9984 8.54872V6.86657L3.67086 6.76976L3.66567 6.76527C3.65165 6.75386 3.61042 6.72027 3.54566 6.64094C3.45006 6.52387 3.3394 6.35139 3.23425 6.1338C3.0231 5.69693 2.85758 5.12712 2.85758 4.54543C2.85758 3.09891 4.19745 0.996988 6.5625 0.996988C8.92755 0.996988 10.2674 3.09891 10.2674 4.54543C10.2674 5.12712 10.1019 5.69693 9.8908 6.1338C9.78562 6.35139 9.67497 6.52387 9.57936 6.64094C9.51467 6.72019 9.47354 6.7537 9.45948 6.76515L9.45411 6.76976L9.1266 6.86657V8.32302L9.13042 8.5698C9.13042 8.5698 9.77302 8.97175 10.5282 9.3736C10.7903 9.51308 11.0401 9.79351 11.265 10.2218C11.4879 10.6462 11.6656 11.1769 11.8025 11.7554Z"
              fill="black"
            />
          </svg>
        </a>
      </div>
      <div class="product-header__nav-cart">
        <a href="">
          <svg
            width="13"
            height="13"
            viewBox="0 0 13 13"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M3.25 4.03227V6.03012L4.0625 6.03063V4.03278L8.91302 4.03227V6.03012H9.74489V4.03227H12.1333V12.2099H0.866667V4.03227H3.25ZM9.74489 3.24269L13 3.24218V13H0V3.24218H3.25C3.36768 1.67208 4.78977 0 6.4001 0C8.02681 0 9.58622 1.63637 9.74489 3.24269ZM8.91302 3.24218C8.77526 2.08635 7.58004 0.790087 6.4001 0.790087C5.11886 0.790087 4.16287 2.08438 4.0625 3.24218H8.91302Z"
              fill="black"
            />
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDesktop: false,
    };
  },
  mounted() {
    this.checkViewport();
    window.addEventListener("resize", this.checkViewport);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkViewport);
  },
  methods: {
    checkViewport() {
      this.isDesktop = window.innerWidth > 766;
    },
  },
};
</script>

<style lang="scss" scoped>
@use '../../assets/styles/var.scss';
.product-header {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    width: 100%;
    &__logo {
        position: absolute;
        left: calc(50% - 56.65px / 2);
        margin: 31px 0 31px 0;
    }
    &__nav {
        display: flex;
        flex-direction: row;
        position: relative;
        margin: 33px 48px 33px 0;
        gap: 16px;
    }
}
@media  (max-width: 766px) {
  .product-header {
    display: flex;
    flex-direction: row;
    position: relative;
    justify-content: space-between;
    width: 100%;
    padding: 0 16px;

    &__logo {
      position: absolute;
      left: calc(50% - 38px / 2);
      margin: 17px 0 16px 0;
    }

    &__nav {
      width: 100%;
      margin: 20px 0;
      justify-content: space-between;
      margin: 15px 15px 16px;

      &-cab {
        order: -1;
      }
      a:first-child,
      a:nth-child(2) {
        margin-right: auto;
      }
      &-cart {
        margin-left: auto;
      }
    }
  }
}
</style>
