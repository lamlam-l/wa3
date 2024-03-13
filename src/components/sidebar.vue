<template>
  <div class="sidebar">

    <div class="sidebar__header">
      <i class="fa-solid fa-temperature-three-quarters thermometer"></i>
      <div class="sidebar__input-wrapper">
        <input type="text" class="sidebar__input" placeholder="Enter a city"/>
      </div>
      <i class="fa-solid fa-magnifying-glass magnify-glass"></i>
    </div>

    <div class="temperature">
      <p class="temperature__value">20° <span class="temperature__different">/</span> 3</p>
      <div class="temperature__wind">
        <p> 9.8% </p>
        <p>Wind: WSW 6 km/h</p>
      </div>
    </div>

    <div class="air-quantity-container">
      <div class="air-quantity">
        <div class="air-quantity__label--container">
          <div class="air-quantity__label" />
          <div class="air-quantity__label" />
          <div class="air-quantity__label" />
          <div class="air-quantity__label" />
          <div class="air-quantity__label" />
        </div>
        <div class="">

        </div>
      </div>
    </div>

  </div>
</template>

<script setup>

</script>

<style scoped>
.sidebar {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(5px);
  padding: 32px 24px;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  border-right: 1px solid rgba(255, 255, 255, 0.2);
  border-top-right-radius: 16px;
  border-bottom-right-radius: 16px;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: space-between;
}

.sidebar__header {
  border-bottom: 1px solid #fff;
  padding: 8px;
  display: flex;
  align-items: end;
  gap: 8px;
}

.thermometer {
  font-size: 20px;
}

.magnify-glass {
  font-size: 16px;
}

.sidebar__input {
  border: 0;
  outline: 0;
  background: none;
  color: var(--white);
  width: 100%;
}

.sidebar__input-wrapper {
  flex: 1;
  flex-basis: 20px;
  width: 20px;
}

.sidebar__input::placeholder {
  color: #cccccc;
}

.temperature__value {
  font-size: 72px;
  font-weight: 200;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.temperature__different {
  font-size: 32px;
}

.temperature__different::before {
  content: "+";
  position: relative;
  top: -12px;
}

.temperature__different::after {
  content: "-";
  position: relative;
  bottom: -10px;
}

.temperature__wind {
  display: flex;
  justify-content: space-between;
  align-items: end;
}

.temperature__wind :first-child {
  font-weight: 200;
  font-size: 32px;
}

.temperature__wind :last-child {
  font-size: 14px;
  line-height: 32px;
  font-weight: 200;
}
</style>

