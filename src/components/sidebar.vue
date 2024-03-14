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
          <div class="air-quantity__label"/>
          <div class="air-quantity__label"/>
          <div class="air-quantity__label"/>
          <div class="air-quantity__label"/>
          <div class="air-quantity__label"/>
        </div>
        <div class="air-quantity__value">
          0.8%
        </div>
      </div>
      <div class="air-quantity-info">
        <div class="air-quantity-info__container">
          <p class="air-quantity-info__label">Safe</p>
          <p class="air-quantity-info__value">0.0% - 0.9%</p>
          <p class="air-quantity-info__value">0.9% - 11 %</p>
        </div>
        <div class="air-quantity-info__container">
          <p class="air-quantity-info__label">Dangerous</p>
          <p class="air-quantity-info__value">12.0% - 0.9%</p>
          <p class="air-quantity-info__value">0.9% - 11 %</p>
        </div>
      </div>
    </div>

    <div class="graph">
      <div class="graph-wrapper">
        <img :src="TempChartImg" alt=""/>
        <p>21°C</p>
      </div>
      <div class="xAxis">
        <p class="xAxis__label">11 pm</p>
        <p class="xAxis__label">1 pm</p>
        <p class="xAxis__label">11 am</p>
        <p class="xAxis__label">1 am</p>
      </div>
      <div class="yAxis">
        <p class="yAxis__label">14</p>
        <p class="yAxis__label">16</p>
        <p class="yAxis__label">18</p>
        <p class="yAxis__label">20</p>
        <p class="yAxis__label">22</p>
        <p class="yAxis__label">24</p>
      </div>
    </div>

  </div>
</template>

<script setup>
import TempChartImg from "../assets/tempChart.svg"
</script>

<style scoped>
.sidebar {
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(5px);
  padding: 32px 24px;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  border-right: 1px solid rgba(255, 255, 255, 0.4);
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

.air-quantity-container {
}

.air-quantity {
  display: flex;
  align-items: end;
  justify-content: space-between;
}

.air-quantity__label--container {
  display: flex;
}

.air-quantity__label {
  width: 28px;
  height: 28px;
  border-radius: 9999px;
  margin-left: -12px;
  border: 1px solid #e0e0e0;
}

.air-quantity__label:nth-child(1) {
  background-color: #DF5054;
}

.air-quantity__label:nth-child(2) {
  background-color: #D08744;
}

.air-quantity__label:nth-child(3) {
  background-color: #D5B550;
}

.air-quantity__label:nth-child(4) {
  background-color: #E6C96B;
}

.air-quantity__label:nth-child(5) {
  background-color: #F8DD82;
}

.air-quantity__value {
  font-size: 28px;
  position: relative;
}

.air-quantity__value::before {
  content: "";
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 9999px;
  background-color: #E6C96B;
  left: -16px;
  bottom: 30%;
}

.air-quantity-info {
  display: flex;
  justify-content: space-between;
  margin-top: 16px;
}

.air-quantity-info__label {
  margin-bottom: 8px;
}
</style>

