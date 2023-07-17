<script>
export default{
 data() {
  return {
     simpleStatisticsDemoCards: [
  {
    icon: 'noto:tomato',
    color: 'info',
    title: 'partiya 1',
    subTitle: 'pamidor',
    stat: '12.28k',
    change: '9.28k',
    bought: '3k'
  },
  {
    icon: 'noto:cucumber',
    color: 'info',
    title: 'partiya 2',
    subTitle: 'bodring',
    stat: '4.673k',
    change: '2k',
    bought: '1k'
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
          <VChip
            :color="demo.color"
            label
            style="margin-left: 4px;"
          >
            {{ demo.bought }}
          </VChip>
        </VCardText>
      </VCard>
    </VCol>
  </VRow>
</template>
