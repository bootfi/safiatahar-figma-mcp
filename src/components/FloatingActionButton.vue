<script setup>
</script>

<template>
  <div class="fab-wrapper">
    <button class="fab-btn" aria-label="Customer Support">
      <img src="/icons/customer-support.svg" alt="Support" class="fab-icon" />
    </button>
  </div>
</template>

<style scoped>
.fab-wrapper {
  position: fixed;
  bottom: var(--spacing-lg);             /* 32px — closest to 40 (between Spacing-lg and xl) */
  right: var(--spacing-lg);
  z-index: 1000;
  padding: var(--spacing-xs);            /* 8px — Spacing-xs */
  border-radius: 50%;
  background: rgba(184, 151, 95, 0.15);
}

.fab-btn {
  width: 86px;
  height: 86px;
  border-radius: 50%;
  background-color: var(--sf-teal-deep);
  border: 4px solid var(--sf-gold);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 20px rgba(184, 151, 95, 0.5); /* Glowing effect */
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.fab-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 25px rgba(184, 151, 95, 0.6);
}

.fab-icon {
  width: 40px;
  height: 40px;
  filter: brightness(0) invert(1);
}

@media (max-width: 768px) {
  .fab-wrapper {
    bottom: var(--spacing-md);           /* 24px — Spacing-md */
    right: var(--spacing-md);
  }
  .fab-btn {
    width: 64px;
    height: 64px;
    border-width: 3px;
  }
  .fab-icon {
    width: 28px;
    height: 28px;
  }
}
</style>
