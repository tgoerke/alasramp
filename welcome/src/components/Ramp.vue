<template>
  <div class="about">


<section>
  <button v-on:click="buy" variant="danger">Send us some DAI</button>
</section>

</div>

</template>

<script>
import { RampInstantSDK } from '@ramp-network/ramp-instant-sdk';

  function simple_buy() {
    new RampInstantSDK({
      url: 'https://ri-widget-staging.firebaseapp.com',
      swapAsset: 'DAI',
      userAddress: '0xCEEfA7764F7BB3a8D1e23C7F15F3f17d9C8d9395',
      //swapAmount: '10000000000000',
      hostAppName: "Alas Ramp",
      hostLogoUrl: "https://github.com/tgoerke/alasramp/blob/cb4c3a60bb36bab1a3da3d0d2d4f759687dbd1b9/welcome/src/assets/alas.png?raw=true",
      variant: "auto",
    }).show();
  }

  function advanced_buy() {
    let data = Array.from(document.forms["ramp-instant-form"]).reduce(
      (acc, cur) => {
        acc[cur.id] = cur.value;
        return acc;
      },
      {}
    );
    let widget = new RampInstantSDK({
    hostAppName: 'Maker DAO',
    hostLogoUrl: 'https://cdn-images-1.medium.com/max/2600/1*nqtMwugX7TtpcS-5c3lRjw.png',
    swapAmount: parseFloat(data["ramp-instant-amount"]) * 10 ** 18,
    swapAsset: data["ramp-instant-asset"],
    url: 'https://widget-instant.ramp.network/', // only specify the url if you want to use testnet widget versions,
    // use variant: 'auto' for automatic mobile / desktop handling,
    // 'hosted-auto' for automatic mobile / desktop handling in new window,
    // 'mobile' to force mobile version
    // 'desktop' to force desktop version (default)
    variant: 'auto', 
    });
    widget.domNodes.overlay.style.zIndex = 1000;
    widget.on("*", (event) => console.log(event));
    widget.show();
  }

export default {
  name: 'Ramp',
  components: {
  },
  data() {
    return {
      name: 'kn00t'
    }
  },
  methods: {
    handleClick: function() {
      console.log(this.name)
    },
    buy: function() {
      console.log("buy called!");
      simple_buy()
    },
    buy2: advanced_buy
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>
