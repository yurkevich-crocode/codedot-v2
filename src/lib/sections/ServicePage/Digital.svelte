<script>
  import imageUrl from '../../js/imageUrlBuilder'
  export let data, openModal
</script>

{#if data}
  <section class="digital">
    <div class="digital__img-wrapper">
      <img src={imageUrl(data.digaitalImage)} alt="" class="digital__img" />
    </div>
    <div class="digital__wrapper">
      <div class="container">
        <div class="digital__text-wrapper">
          <h2 class="digital__text">{data.digitalText}</h2>
          <btn class="digital__link" on:click={openModal}>
            <img src="../icons/arrow-btn.svg" alt="#" class="digital__link-icon" />
          </btn>
        </div>
      </div>
    </div>
  </section>
{/if}

<style lang="scss">
  @import '../../styles/base/mixins.scss';

  .digital {
    @include media-breakpoint-down(xl) {
      margin: 100px 0;
    }

    @include media-breakpoint-up(xl) {
      margin: 250px 0;
    }
    position: relative;

    @include media-breakpoint-down(md) {
      height: 254px;
    }

    @include media-breakpoint-up(md) {
      height: 540px;
    }
    &__img-wrapper {
      position: absolute;

      border-radius: 40px;
      overflow: hidden;

      @include media-breakpoint-down(md) {
        width: calc(100% - 40px);
        margin-left: 20px;
        height: 254px;
      }

      @include media-breakpoint-up(md) {
        width: 100%;
        height: 540px;
      }
    }

    &__img {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      object-fit: cover;
    }

    &__wrapper {
      display: flex;
      align-items: center;
      height: 100%;
    }

    &__text-wrapper {
      display: flex;
      align-items: center;
      background-color: rgba(255, 255, 255, 0.703);
      border-radius: 40px;

      @include media-breakpoint-down(md) {
        flex-direction: column;
        padding: 20px;
        margin-left: 20px;
        margin-right: 20px;
      }

      @include media-breakpoint-up(md) {
        padding: 40px;
      }
    }

    &__text {
      font-weight: 700;

      @include media-breakpoint-down(md) {
        font-size: 24px;
        padding-bottom: 20px;
        text-align: center;
      }

      @include media-breakpoint-between(md, lg) {
        font-size: 30px;
      }

      @include media-breakpoint-between(lg, xl) {
        font-size: 50px;
      }

      @include media-breakpoint-between(xl, xxl) {
        font-size: 75px;
      }

      @include media-breakpoint-up(xxl) {
        font-size: 100px;
      }
    }

    &__link {
      cursor: pointer;
    }

    &__link-icon {
      filter: brightness(0);

      transform: rotate(-45deg);

      @include media-breakpoint-down(lg) {
        width: 40px;
        height: 40px;
      }

      @include media-breakpoint-between(lg, xl) {
        width: 60px;
        height: 60px;
      }

      @include media-breakpoint-between(xl, xxl) {
        width: 100px;
        height: 100px;
      }

      @include media-breakpoint-up(xxl) {
        width: 150px;
        height: 150px;
      }
    }
  }
</style>
