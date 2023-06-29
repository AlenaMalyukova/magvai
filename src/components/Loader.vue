<template>
  <div class="screen">
    <span class="icon-spinner"></span>
  </div>
</template>

<style lang="scss" scoped>

  .screen {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .icon-spinner {
    font-size: 36px;
    animation: spin 1s linear infinite;
  }

  @keyframes spin {
    from { transform: rotate(0deg)}
    to { transform: rotate(360deg)}
  }
</style>