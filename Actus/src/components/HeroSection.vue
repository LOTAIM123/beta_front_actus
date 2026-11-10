<template>
  <section class="hero actus-container">
    <div class="hero__topbar row items-center justify-between">
      <span class="hero__eyebrow actus-mono">MINIMĀLISMS AR RAKSTURU</span>

      <div class="hero__badges row items-center no-wrap gt-xs">
        <span class="hero__badge">
          <q-icon name="verified_user" size="18px" />
          Verificēti uzņēmumi
        </span>
        <span class="hero__badge">
          <q-icon name="school" size="18px" />
          Akreditētas mācību programmas
        </span>
      </div>
    </div>

    <div class="hero__main row justify-between items-start">
      <div class="hero__copy">
        <ActusLogo large />

        <h1 class="hero__title">Tava nākamā prakse sākas šeit!</h1>

        <p class="hero__lead">
          Atrodi prakses vietu savā profesijā, sazinies tieši ar uzņēmumu mentoriem un sper soli
          pretī savai karjerai.
        </p>
      </div>

      <div class="hero__cta column items-end">
        <q-btn
          unelevated
          no-caps
          color="primary"
          text-color="dark"
          icon="add_circle_outline"
          label="UZŅĒMUMIEM: PUBLICĒT VIETU"
          class="hero__cta-btn"
        />
        <span class="hero__cta-note actus-mono">Oficiāli DVB un arodizglītības līgumi</span>
      </div>
    </div>
  </section>
</template>

<script setup>
import ActusLogo from '@/components/ActusLogo.vue'
</script>

<style scoped lang="scss">
.hero {
  padding-top: 48px;

  &__topbar {
    padding: 0 20px 24px;
    border-bottom: 1px solid var(--actus-border);
  }

  &__eyebrow {
    font-size: 12.5px;
    letter-spacing: 0.14em;
    color: var(--actus-green);
  }

  &__badges {
    gap: 28px;
  }

  &__badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 15px;
    color: #bfe9d0;

    .q-icon {
      color: var(--actus-green);
    }
  }

  &__main {
    padding-top: 38px;
    gap: 24px;
  }

  &__copy {
    max-width: 1000px;
  }

  &__title {
    margin: 22px 0 0;
    font-size: 58px;
    font-weight: 800;
    white-space: nowrap;
    line-height: 1.1;
    letter-spacing: -0.045em;
  }

  &__lead {
    max-width: 850px;
    margin: 22px 0 0;
    font-size: 20px;
    line-height: 1.65;
    color: #d6e6de;
  }

  &__cta {
    padding-top: 74px;
    gap: 18px;
  }

  &__cta-btn {
    height: 50px;
    padding: 0 26px;
    border-radius: 999px;
    font-size: 15px;
    font-weight: 700;
    letter-spacing: 0.05em;
    box-shadow: 0 10px 30px rgba(34, 197, 94, 0.3);
  }

  &__cta-note {
    font-size: 12px;
    color: #7fd8a4;
  }
}

@media (max-width: 1023px) {
  .hero {
    &__title {
      font-size: 44px;
      white-space: normal;
    }

    &__cta {
      padding-top: 0;
      align-items: flex-start;
    }
  }
}

@media (max-width: 600px) {
  .hero {
    padding-top: 28px;

    &__topbar {
      padding: 0 4px 18px;
    }

    &__title {
      font-size: 34px;
      white-space: normal;
    }

    &__lead {
      font-size: 17px;
    }

    &__cta-btn {
      font-size: 13px;
    }
  }
}
</style>
