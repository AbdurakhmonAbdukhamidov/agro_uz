<script>
export default{
 data() {
  return {
     simpleStatisticsDemoCards: [
  {
    icon: 'tabler-currency-dollar',
    color: 'info',
    title: 'partiya 1',
    subTitle: 'pamidor',
    stat: '12.28k',
    change: '1k',
  },
  {
    icon: 'tabler-chart-bar',
    color: 'info',
    title: 'partiya 2',
    subTitle: 'bodring',
    stat: '4.673k',
    change: '2k',
  },
]
  }
 },
}
</script>

<template>
  <VRow>
    <VCol
      v-for="demo in simpleStatisticsDemoCards"
      :key="demo.title"
      cols="12"
      sm="6"
      md="4"
      lg="2"
    >
      <VCard>
        <VCardText>
          <VAvatar
            :color="demo.color"
            variant="tonal"
            rounded
            size="42"
          >
            <VIcon :icon="demo.icon" />
          </VAvatar>

          <h6 class="text-h6 mt-3">
            {{ demo.title }}
          </h6>
          <p class="text-sm text-disabled mt-1 mb-0">
            {{ demo.subTitle }}
          </p>
          <p class="my-2">
            {{ demo.stat }}
          </p>
          <VChip
            :color="demo.color"
            label
          >
            {{ demo.change }}
          </VChip>
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>
