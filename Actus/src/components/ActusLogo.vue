<template>
  <div class="actus-logo row items-center no-wrap" :class="{ 'actus-logo--large': large }">
    <svg class="actus-logo__mark" viewBox="0 0 64 64" aria-hidden="true">
      <defs>
        <linearGradient id="actusLogoGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0" stop-color="#4ade80" />
          <stop offset="1" stop-color="#16a34a" />
        </linearGradient>
      </defs>
      <path d="M32 3 L61 60 H45 L32 33 L19 60 H3 Z" fill="url(#actusLogoGrad)" />
      <path d="M32 36 L41 54 H23 Z" fill="#0b3b2b" opacity="0.55" />
    </svg>
    <div class="actus-logo__text">
      <div class="actus-logo__name">Actus</div>
      <div class="actus-logo__tagline actus-mono">PRAKSE • IZAUGSME • KARJERA</div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  large: { type: Boolean, default: false },
})
</script>

<style scoped lang="scss">
.actus-logo {
  gap: 14px;

  &__mark {
    width: 34px;
    height: 34px;
    flex: none;
  }

  &__name {
    font-size: 30px;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
  }

  &__tagline {
    margin-top: 6px;
    font-size: 10.5px;
    font-weight: 500;
    letter-spacing: 0.22em;
    color: #cfe3da;
  }

  &--large {
    gap: 24px;

    .actus-logo__mark {
      width: 62px;
      height: 62px;
    }

    .actus-logo__name {
      font-size: 56px;
    }

    .actus-logo__tagline {
      margin-top: 10px;
      font-size: 15px;
      letter-spacing: 0.26em;
    }
  }
}

@media (max-width: 600px) {
  .actus-logo--large {
    gap: 14px;

    .actus-logo__mark {
      width: 44px;
      height: 44px;
    }

    .actus-logo__name {
      font-size: 40px;
    }

    .actus-logo__tagline {
      font-size: 11px;
    }
  }
}
</style>
