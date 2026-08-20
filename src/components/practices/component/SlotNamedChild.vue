<template>
  <div class="base-card">
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot></slot>
    </main>
  </div>
</template>

<style scoped>
.base-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 16px;
  margin-bottom: 12px;
  background: white;
}
header {
  font-weight: bold;
  font-size: 15px;
  color: #555;
  border-bottom: 1px solid #eee;
  padding-bottom: 8px;
  margin-bottom: 10px;
}
</style>
