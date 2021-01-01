<template>
  <div id="name-container">
    <div id="name-inside-container">
      <span id="name">Leand<span id="inside-letters">ro Rod</span>rigues</span>
      <div id="square"></div>
    </div>
  </div>

</template>

<script>

export default {
  components: {
  }
}
</script>

<style>
  #name-container {
    user-select: none;
    margin-top: 40%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
  }

  #name-inside-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }

  #name {
    font-family: 'Manrope', sans-serif;
    color: #3e363f;
    font-size: 3rem;
    z-index: 10;
  }

  #inside-letters {
    margin: 0;
    padding: 0;
    color: rgb(249, 251, 232);
  }

  #square {
    position: relative;
    bottom: 96px;
    border: solid rgb(36, 36, 36) 2px;
    height: 8.3rem;
    width:  8.3rem;
    background-color: rgb(36, 36, 36);
    margin-bottom: -4.7rem;
  }

  @media only screen and (max-width: 1050px) {
    #square {
      height: 5.9rem;
      width:  5.9rem;
      bottom: 73px;

    }

    #name {
      font-size: 2.1rem
    }

    #name-inside-container {

    }
  }

</style>