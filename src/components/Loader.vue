<template>
  <div class="screen">
    <span class="icon-spinner"></span>
  </div>
</template>

<style lang="scss" scoped>

  .screen {
    width: 100%;
    height: 100%;
    padding: 30px 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .icon-spinner {
    font-size: 64px;
    animation: spin 1s linear infinite;
    color: #C2AB81;
  }

  @keyframes spin {
    from { transform: rotate(0deg)}
    to { transform: rotate(360deg)}
  }
</style>