<template>
  <div class="loading-container">
    <div class="logo">
      <div class="white" />
      <div class="orange" />
      <div class="red" />
    </div>
    <h1>Loading ...</h1>
  </div>
</template>

<script>
export default {
  name: 'Loading'
}
</script>

<style scoped lang="less">
  @color: black;
  @time: 1.5s;
  @size: 100px;

  html,
  body,
  .loading-container {
    margin: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  .loading-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  h1 {
    font-family: 'Helvetica', 'Arial', sans-serif;
    font-size: 1.05rem;
  }

  .logo {
    position: relative;
    width: @size;
    height: @size;
    box-sizing: border-box;

    &::before,
    &::after {
      content: '';
      position: absolute;
      width: 100%;
      height: 100%;
      box-sizing: border-box;
      border: 4px solid transparent;
      animation-timing-function: linear;
    }

    &::before {
      top: 0;
      left: 0;
      border-top-color: @color;
      border-right-color: @color;
      animation: border-before @time infinite;
      animation-direction: alternate;
    }

    &::after {
      bottom: 0;
      right: 0;
      border-bottom-color: @color;
      border-left-color: @color;
      animation: border-after @time infinite;
      animation-direction: alternate;
    }

    & > div {
      position: absolute;
    }

    .red {
      top: 4px;
      bottom: 0;
      left: 0;
      border-right: 4px solid @color;
      background-color: #EA5664;
      animation: red @time infinite;
      animation-direction: alternate;
    }

    .orange {
      bottom: 0;
      left: 27%;
      right: 4px;
      border-top: 4px solid @color;
      background-color: #F3B93F;
      animation: orange @time infinite;
      animation-direction: alternate;
    }

    .white {
      right: 5px;
      top: 4px;
      bottom: 50%;
      height: 50%;
      border-left: 4px solid @color;
      background-color: #fff;
      animation: white @time infinite;
      animation-direction: alternate;
    }
  }

  @keyframes border-before {
    0% {
      width: 0;
      height: 0;
      border-right-color: transparent;
    }
    5.99% {
      border-right-color: transparent;
    }
    6% {
      height: 0;
      width: 100%;
      border-right-color: @color;
    }
    25%,
    100% {
      width: 100%;
      height: 100%;
    }
  }

  @keyframes border-after {
    0%,
    24.99% {
      width: 0;
      height: 0;
      border-left-color: transparent;
      border-bottom-color: transparent;
    }
    25% {
      border-left-color: transparent;
      border-bottom-color: @color;
    }
    36.99% {
      border-left-color: transparent;
    }
    37% {
      height: 0;
      width: 100%;
      border-left-color: @color;
    }
    50%,
    100% {
      width: 100%;
      height: 100%;
    }
  }

  @keyframes red {
    0%,
    50% {
      width: 0;
      opacity: 0;
    }
    50.01% {
      opacity: 1;
    }
    65%,
    100% {
      width: 27%;
      opacity: 1;
    }
  }

  @keyframes orange {
    0%,
    65% {
      height: 0;
      opacity: 0;
    }
    65.01% {
      opacity: 1;
    }
    80%,
    100% {
      height: 50%;
      opacity: 1;
    }
  }

  @keyframes white {
    0%,
    75% {
      width: 0;
      opacity: 0;
    }
    75.01% {
      opacity: 1;
    }
    90%,
    100% {
      width: 27%;
      opacity: 1;
    }
  }
</style>
