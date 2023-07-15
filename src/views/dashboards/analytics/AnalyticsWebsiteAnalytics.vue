<script setup>
import { VIcon } from 'vuetify/components'
import sliderBar1 from '@images/illustrations/sidebar-pic-1.png'
import sliderBar2 from '@images/illustrations/sidebar-pic-2.png'
import sliderBar3 from '@images/illustrations/sidebar-pic-3.png'

const websiteAnalytics = [
  {
    name: 'Hozirgi holat',
    slideImg: sliderBar1,
    data: [
      {
        number: '3',
        text: 'Partiyalar',
      },
      {
        number: '8',
        text: 'Hodimlar',
      },
      {
        number: '1.680 k',
        text: 'Ko`chatlar',
      },
      {
        number: '3',
        text: 'o`simliklar turlari',
      },
    ],
  },
  {
    name: 'krim',
    slideImg: sliderBar2,
    data: [
      {
        number: '1 m',
        text: 'Sotilgan',
      },
      {
        number: '200 000',
        text: 'Foyda',
      },
      {
        number: '200',
        text: 'buyurtmasi yopilgan mijozlar',
      },
    ],
  },
  {
    name: 'chiqim va yoqotishlar',
    slideImg: sliderBar3,
    data: [
      {
        number: '268',
        text: 'harajatlar',
      },
      {
        number: '890',
        text: 'Yoqotishlar',
      },
      {
        number: '622',
        text: 'Soliq harajatlari',
      },
    ],
  },
]
</script>

<template>
  <VCard color="primary">
    <VCarousel
      cycle
      :continuous="false"
      :show-arrows="false"
      hide-delimiter-background
      :delimiter-icon="() => h(VIcon, { icon: 'fa-circle', size: '10' })"
      height="auto"
      class="carousel-delimiter-top-end web-analytics-carousel"
    >
      <VCarouselItem
        v-for="item in websiteAnalytics"
        :key="item.name"
      >
        <VCardText>
          <VRow>
            <VCol cols="12">
              <h6 class="text-h6 text-white mb-1">
                Analytics
              </h6>
            </VCol>

            <VCol
              cols="12"
              sm="6"
              order="2"
              order-sm="1"
            >
              <VRow>
                <VCol
                  cols="12"
                  class="pb-0"
                >
                  <p class="font-weight-semibold">
                    {{ item.name }}
                  </p>
                </VCol>

                <VCol
                  v-for="d in item.data"
                  :key="d.number"
                  cols="6"
                  class="text-no-wrap"
                >
                  <VChip
                    label
                    class="me-2"
                  >
                    {{ d.number }}
                  </VChip>
                  <span>{{ d.text }}</span>
                </VCol>
              </VRow>
            </VCol>

            <VCol
              cols="12"
              sm="6"
              order="1"
              order-sm="2"
              class="position-relative text-center"
            >
              <img
                :src="item.slideImg"
                class="card-website-analytics-img"
              >
            </VCol>
          </VRow>
        </VCardText>
      </VCarouselItem>
    </VCarousel>
  </VCard>
</template>

<style lang="scss">
.card-website-analytics-img {
  block-size: 160px;
}

@media screen and (min-width: 600px) {
  .card-website-analytics-img {
    position: absolute;
    margin: auto;
    inset-block-end: 40px;
    inset-block-start: -1rem;
    inset-inline-end: 1rem;
  }
}

.web-analytics-carousel {
  .v-carousel__controls {
    .v-btn:not(.v-btn--active) {
      opacity: 0.4;
    }
  }
}
</style>

