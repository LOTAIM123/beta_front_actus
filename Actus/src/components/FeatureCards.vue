<template>
  <section class="features">
    <div class="features__grid">
      <div v-for="item in items" :key="item.title" class="features__card row items-center no-wrap">
        <span class="features__icon">
          <q-icon :name="item.icon" size="22px" />
        </span>
        <span class="features__title">{{ item.title }}</span>
      </div>
    </div>
  </section>
</template>

<script setup>
const items = [
  { icon: 'search', title: 'Viegli atrast piemērotu vietu' },
  { icon: 'chat_bubble_outline', title: 'Sazinies ar uzņēmumu' },
  { icon: 'how_to_reg', title: 'Profils un prasmes' },
  { icon: 'favorite_border', title: 'Saglabā vēlākam' },
]
</script>

<style scoped lang="scss">
.features {
  margin-top: 40px;
  padding: 30px 0 60px;
  border-top: 1px solid var(--actus-border);

  &__grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
  }

  &__card {
    gap: 16px;
    padding: 0 16px;
    height: 77px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid var(--actus-border);
    border-radius: 16px;
  }

  &__icon {
    display: grid;
    place-items: center;
    width: 46px;
    height: 46px;
    flex: none;
    border-radius: 50%;
    color: var(--actus-green);
    background: rgba(34, 197, 94, 0.14);
    border: 1px solid rgba(34, 197, 94, 0.45);
  }

  &__title {
    font-size: 15px;
    font-weight: 700;
    letter-spacing: -0.01em;
  }
}

@media (max-width: 1023px) {
  .features__grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 600px) {
  .features__grid {
    grid-template-columns: 1fr;
  }
}
</style>
