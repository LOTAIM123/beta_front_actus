<template>
  <section class="search-card">
    <div class="search-card__head row items-center justify-between">
      <div class="search-card__title row items-center no-wrap">
        <span class="search-card__dot" />
        VIEDĀ PRAKSES VIETU ATLASE
      </div>
      <span class="search-card__hint actus-mono gt-xs">
        Verificētas valsts un privātā sektora vakances
      </span>
    </div>

    <div class="search-card__form row items-end no-wrap">
      <div class="search-card__field search-card__field--profession">
        <label class="search-card__label">PROFESIJA VAI NOZARE</label>
        <q-select
          v-model="profession"
          :options="professions"
          outlined
          dense
          emit-value
          map-options
          :display-value="profession || 'Ievadi vai izvēlies savu apgūstamo profesiju...'"
          :class="{ 'search-card__input--empty': !profession }"
          class="search-card__input"
          dropdown-icon="expand_more"
        />
      </div>

      <div class="search-card__field search-card__field--region">
        <label class="search-card__label">PILSĒTA / REĢIONS</label>
        <q-select
          v-model="region"
          :options="regions"
          outlined
          dense
          class="search-card__input"
          dropdown-icon="expand_more"
        />
      </div>

      <q-btn
        unelevated
        no-caps
        color="primary"
        text-color="dark"
        icon="search"
        label="ATRAST PRAKSI"
        class="search-card__submit"
      />
    </div>

    <div class="search-card__filters row items-center justify-between">
      <div class="row items-center no-wrap">
        <span class="search-card__label search-card__label--inline">DARBA VIETAS VEIDS:</span>
        <q-btn-toggle
          v-model="placeType"
          unelevated
          no-caps
          rounded
          toggle-color="secondary"
          color="white"
          text-color="grey-8"
          class="search-card__toggle"
          :options="placeTypes"
        />
      </div>

      <q-btn
        flat
        no-caps
        dense
        icon="refresh"
        label="Atiestatīt"
        color="positive"
        class="search-card__reset"
        @click="reset"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const professions = ['Programmētājs', 'Pavārs', 'Elektriķis', 'Grāmatvedis', 'Mehāniķis']
const regions = [
  'Visi reģioni un pilsētas',
  'Rīga',
  'Pierīga',
  'Vidzeme',
  'Kurzeme',
  'Zemgale',
  'Latgale',
]
const placeTypes = [
  { label: 'Visi', value: 'all' },
  { label: 'Vienā vietā', value: 'single' },
  { label: 'Vairākos objektos', value: 'multi' },
]

const profession = ref(null)
const region = ref(regions[0])
const placeType = ref('all')

function reset() {
  profession.value = null
  region.value = regions[0]
  placeType.value = 'all'
}
</script>

<style scoped lang="scss">
.search-card {
  margin-top: 28px;
  padding: 30px 31px 30px;
  color: #0b3b2b;
  background: var(--actus-card);
  border-radius: 28px;
  box-shadow: 0 30px 70px rgba(0, 0, 0, 0.35);

  &__head {
    margin-bottom: 28px;
  }

  &__title {
    gap: 12px;
    font-size: 15.5px;
    font-weight: 800;
    letter-spacing: 0.02em;
    color: #0b3b2b;
  }

  &__dot {
    width: 13px;
    height: 13px;
    border-radius: 50%;
    background: var(--actus-green);
    box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.18);
  }

  &__hint {
    font-size: 12px;
    color: #3d7a63;
  }

  &__form {
    gap: 18px;
    padding-bottom: 20px;
    border-bottom: 1px solid #dde8e3;
  }

  &__field {
    min-width: 0;
    display: flex;
    flex-direction: column;
    gap: 10px;

    &--profession {
      flex: 1 1 0;
    }

    &--region {
      flex: 0 0 351px;
    }
  }

  &__label {
    font-size: 13.5px;
    font-weight: 700;
    letter-spacing: 0.03em;
    color: #0b3b2b;

    &--inline {
      margin-right: 14px;
    }
  }

  &__input {
    :deep(.q-field__control) {
      height: 55px;
      padding: 0 16px;
      background: #f7fbf9;
      border-radius: 14px;
    }

    :deep(.q-field__control:before) {
      border-color: #cfe0d8;
    }

    :deep(.q-field__native),
    :deep(.q-field__input) {
      font-size: 17px;
      color: #1a4a39;
    }

    :deep(.q-field__native span) {
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }

    &--empty :deep(.q-field__native) {
      color: #8fa8a0;
    }
  }

  &__submit {
    flex: 0 0 351px;
    height: 55px;
    border-radius: 14px;
    font-size: 15px;
    font-weight: 800;
    letter-spacing: 0.05em;
    box-shadow: 0 10px 24px rgba(34, 197, 94, 0.35);
  }

  &__filters {
    padding-top: 20px;
    gap: 16px;
  }

  &__toggle {
    border: 1px solid #cfe0d8;
    border-radius: 999px;
    background: #fff;
    padding: 2px;

    :deep(.q-btn) {
      padding: 5px 16px;
      font-size: 15px;
    }
  }

  &__reset {
    font-weight: 700;
    color: #16a34a !important;
    text-decoration: underline;
    text-underline-offset: 4px;
  }
}

@media (max-width: 1023px) {
  .search-card {
    &__form {
      flex-wrap: wrap;
    }

    &__field,
    &__field--region,
    &__submit {
      flex: 1 1 100%;
    }
  }
}

@media (max-width: 600px) {
  .search-card {
    padding: 22px 18px;
    border-radius: 22px;

    &__filters {
      flex-direction: column;
      align-items: flex-start !important;
    }

    &__toggle {
      margin-top: 10px;
    }
  }
}
</style>
