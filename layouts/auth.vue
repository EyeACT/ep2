<template>
  <div class="overlay relative flex h-screen items-center justify-center">
    <div class="gradient" />

    <UButton
      icon="i-heroicons-home"
      label="Home"
      to="/"
      color="neutral"
      class="absolute top-4"
    />

    <slot />
  </div>
</template>

<style scoped>
.gradient {
  position: absolute;
  inset: 0;
  pointer-events: none;
  background: radial-gradient(
    50% 50% at 50% 50%,
    rgb(var(--auth-color-primary-500) / 0.25) 0,
    #fff 100%
  );
}

.dark {
  .gradient {
    background: radial-gradient(
      50% 50% at 50% 50%,
      rgb(var(--auth-color-primary-400) / 0.1) 0,
      rgb(var(--auth-color-gray-950)) 100%
    );
  }
}

.overlay {
  background-size: 100px 100px;
  background-image:
    linear-gradient(
      to right,
      rgb(var(--auth-color-gray-200)) 0.5px,
      transparent 0.5px
    ),
    linear-gradient(
      to bottom,
      rgb(var(--auth-color-gray-200)) 0.5px,
      transparent 0.5px
    );
}
.dark {
  .overlay {
    background-image:
      linear-gradient(
        to right,
        rgb(var(--auth-color-gray-900)) 0.5px,
        transparent 0.5px
      ),
      linear-gradient(
        to bottom,
        rgb(var(--auth-color-gray-900)) 0.5px,
        transparent 0.5px
      );
  }
}
</style>
