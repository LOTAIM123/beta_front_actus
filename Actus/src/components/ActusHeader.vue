<template>
  <q-header class="actus-header">
    <div class="actus-container row items-center no-wrap actus-header__inner">
      <router-link to="/" class="actus-header__brand">
        <ActusLogo />
      </router-link>

      <nav class="actus-header__nav row items-center no-wrap gt-sm">
        <a
          v-for="item in navItems"
          :key="item.label"
          href="#"
          class="actus-header__link"
          :class="{ 'actus-header__link--active': item.active }"
          @click.prevent
        >
          {{ item.label }}
        </a>
      </nav>

      <q-space />

      <div class="row items-center no-wrap q-gutter-md">
        <button type="button" class="actus-header__saved gt-xs">
          <q-icon name="favorite_border" size="18px" />
          <strong>0</strong>
          <span>Saglabāts</span>
        </button>

        <q-btn
          unelevated
          no-caps
          color="primary"
          text-color="dark"
          icon="person_outline"
          label="IENĀKT"
          class="actus-header__login"
        />
      </div>
    </div>
  </q-header>
</template>

<script setup>
import ActusLogo from '@/components/ActusLogo.vue'

const navItems = [
  { label: 'Prakses vietas', active: true },
  { label: 'Uzņēmumiem', active: false },
  { label: 'Izglītības iestādēm', active: false },
  { label: 'Par mums', active: false },
]
</script>

<style scoped lang="scss">
.actus-header {
  background: var(--actus-bg-header);
  border-bottom: 1px solid var(--actus-border);
  color: #fff;

  &__inner {
    height: 83px;
  }

  &__brand {
    color: inherit;
    text-decoration: none;
  }

  &__nav {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    gap: 10px;
  }

  &__link {
    padding: 9px 18px;
    border: 1px solid transparent;
    border-radius: 999px;
    font-size: 15px;
    font-weight: 700;
    color: #e6efeb;
    text-decoration: none;
    letter-spacing: 0.01em;
    transition:
      background 0.2s,
      border-color 0.2s;

    &:hover {
      background: rgba(255, 255, 255, 0.06);
    }

    &--active {
      color: var(--actus-green);
      background: rgba(34, 197, 94, 0.14);
      border-color: rgba(34, 197, 94, 0.55);
    }
  }

  &__saved {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    font: inherit;
    font-size: 14px;
    color: #dfece6;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid var(--actus-border);
    border-radius: 999px;
    cursor: pointer;

    strong {
      font-weight: 700;
    }
  }

  &__login {
    flex: none;
    white-space: nowrap;
    height: 40px;
    padding: 0 22px;
    border-radius: 999px;
    font-weight: 700;
    letter-spacing: 0.06em;
    box-shadow: 0 6px 18px rgba(34, 197, 94, 0.28);
  }
}
</style>

<style lang="scss">
@media (max-width: 600px) {
  .actus-header .actus-logo__tagline {
    display: none;
  }
}
</style>
