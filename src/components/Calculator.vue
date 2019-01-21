<template>
  <s-container>
    <h1>Avalara Tax Rates by Address</h1>
    <s-row>
      <div>
        Use the Avalara TaxRatesByAddress API to calculate tax rates for a given
        adddress.
      </div>
    </s-row>
    <s-row>
      <s-col span="4">
        <h2>Enter your address</h2>
        <div>Enter your data into the form below</div>
        <form>
          <!-- <fieldset>
            <legend>Your items</legend>
            <s-row class="pad-all-none">
              <s-col span="2">
                <label>Quantity</label>
                <input type="number" placeholder="Required" />
              </s-col>
              <s-col span="2">
                <label>Item code</label>
                <input type="text" placeholder="Optional" />
              </s-col>
              <s-col span="2">
                <label>Tax code</label>
                <input type="text" placeholder="Optional" />
              </s-col>
              <s-col span="2">
                <label>Price</label>
                <input type="text" placeholder="Required" />
              </s-col>
              <s-col span="2">
                <label>Total</label> <input type="number" readonly />
              </s-col>
            </s-row>
            <s-row>
              <s-col span="8">
                <label>Item description</label>
                <input type="text" placeholder="Optional" />
              </s-col>
            </s-row>
          </fieldset>-->
          <fieldset>
            <s-row class="pad-all-none">
              <s-col span="12">
                <label>Address Line 1</label>
                <input type="text" placeholder="Required" :value="line1" />
              </s-col>
            </s-row>
            <s-row class="pad-all-none">
              <s-col span="12">
                <label>Address Line 2</label>
                <input type="text" placeholder="Optional" :value="line2" />
              </s-col>
            </s-row>
            <s-row class="pad-all-none">
              <s-col span="12">
                <label>Address Line 3</label>
                <input type="text" placeholder="Optional" :value="line3" />
              </s-col>
            </s-row>
            <s-row class="pad-all-none">
              <s-col span="6">
                <label>City</label>
                <input type="text" placeholder="Required" :value="city" />
              </s-col>
              <s-col span="6">
                <label>Region</label>
                <input
                  type="text"
                  placeholder="Required: ISO 3166 code"
                  :value="region"
                />
              </s-col>
            </s-row>
            <s-row class="pad-all-none">
              <s-col span="6">
                <label>Postal Code</label>
                <input type="text" placeholder="Required" :value="postalCode" />
              </s-col>
              <s-col span="6">
                <label>Country</label>
                <input
                  type="text"
                  placeholder="Required: ISO 3166 code"
                  :value="country"
                />
              </s-col>
            </s-row>
          </fieldset>
          <s-row class="pad-all-none">
            <s-col span="6">
              <button type="button" class="primary" v-on:click="submit">
                Submit
              </button>
            </s-col>
            <s-col span="6">
              <button type="button" class="secondary right" v-on:click="reset">
                Reset
              </button>
            </s-col>
          </s-row>
        </form>
      </s-col>
      <s-col span="auto"> <h2>Results</h2> </s-col>
    </s-row>
  </s-container>
</template>

<script>
export default {
  name: 'Calculator',
  data: function() {
    return {
      line1: '',
      line2: '',
      line3: '',
      city: '',
      region: '',
      postalCode: '',
      country: ''
    };
  },
  methods: {
    submit: function() {
      console.log(this.line1);
    },
    reset: function() {
      console.log('reset');
      return {
        line1: '',
        line2: '',
        line3: '',
        city: '',
        region: '',
        postalCode: '',
        country: ''
      };
    }
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
