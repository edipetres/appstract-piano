<template>
  <div class="main-container">
    <div class="side-panel panel-left">
      <div class="text bold bottom-spacing">Workspace</div>
      <div class="text">Top bar style</div>
      <div class="custom-btn">Frequency</div>
      <div class="custom-btn pull-down">Active Experience</div>
    </div>

    <div class="center-panel">
      <div class="top-block">

      </div>

      <div class="center-block">
        <div class="text-content">
          <div>You pressed the note: <b>{{ lastKey }}</b></div>
          <div>That's the equivalent of <b>130.81 Hz</b> and a wavelength of <b>263.74 cm</b>.</div>
        </div>
      </div>

      <div class="bottom-block">
        <div class="piano-key-wrapper">
          <div class="piano-key" v-for="n in ['C', 'D', 'E', 'F', 'G', 'A', 'B', 'C']" :key="n" @click="keyClicked(n)"> 
            <div class="piano-note"> {{ n }} </div>
          </div>
        </div>
      </div>
    </div>

    <div class="side-panel panel-right">
      <div class="trainings">
        <div class="text bold">Pitch training</div>
        <div class="list-item">Notes</div>
        <div class="list-item">Intervals</div>
      </div>

      <div class="details pull-down">
        <div class="menu-item">
          <img class="avatar" src="https://cdn4.iconfinder.com/data/icons/web-ui-color/128/Account-512.png">
          <span class="text">10</span>
        </div>
        <div class="menu-item">
          <img class="avatar" src="https://cdn4.iconfinder.com/data/icons/web-ui-color/128/Account-512.png">
          <span class="text">Account</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      lastKey: ''
    }
  },
  methods: {
    keyClicked(key) {
      this.lastKey = key
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import './theme.scss';

.main-container {
  font-family: 'Muli', sans-serif;
  position:absolute;
  height: 700px;
  bottom: 0;
  top: 0;
  left: 0;
  right: 0;
  padding: 30px 25px;
  font-size: 18px;
  

  .pull-down {
    position: absolute;
    bottom: 0;
  }

  // Define overall text styles
  .text {
    color: $light-green;
    margin-bottom: 5px;
    
    &.bold {
      font-weight: 900;
    }

    &.bottom-spacing {
      margin-bottom: 20px;
    }
  }

  .side-panel {
    width: 20%;
    height: 100%;
    position: relative;

    &.panel-left {
      float: left;
    }

    &.panel-right {
      float: right;
      text-align: left;
      padding-left: 5%;
      box-sizing: border-box;
      color: $light-green;

      .list-item {
        padding-left: 25px;
        line-height: 150%;
      }

      .details {

        .menu-item {
          margin-bottom: 10px;

          .avatar {
            width: 30px;
            height: 30px;
          }
  
          .text {
            position: relative;
            font-weight: 400;
            left: 15%;
            bottom: 8px;
          }
        }
        
      }
    }
  }

  .center-panel {
    float: left;
    height: 100%;
    width: 60%;
    $border-size: 3px;

    .top-block {
      border: $border-size solid $faded-red;
      height: 20%;
      box-sizing: border-box;
    }

    .center-block {
      border: $border-size solid $faded-red;
      height: 40%;
      background-color: $faded-red;
      color: $light-green;
      box-sizing: border-box;

      .text-content {
        padding: 20px;
      }
    }

    .bottom-block {
      box-sizing: border-box;
      width: 100%;
      height: 40%;
      background-color: $cream-white;
      border: $border-size solid $dark-grey;
      display: table;

      .piano-key-wrapper {
        display: table-row;

        .piano-key {
          display: table-cell;
          position: relative;
          width: 50px;
          height: 100%;
          border: 2px solid $dark-grey;

          &:active {
            background-color: $light-green;
          }

          .piano-note {
            position: absolute;
            bottom: 5px;
            text-align: center;
            width: 100%;
            font-weight: 900;
            color: $faded-red;
          }
        }
      }

    }
  }
  
}

</style>
