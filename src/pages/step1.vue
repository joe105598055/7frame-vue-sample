<template>
  <f7-page name="step1" title="step1" stacked>
    <f7-navbar title="Step 1" back-link="Back"></f7-navbar>
    <f7-block-title>Step 1</f7-block-title>
    <!-- <f7-block>
      <f7-list-input
        label="Name"
        type="text"
        placeholder="Your name"
        :value="name"
        @input="name=$event.target.value"
      ></f7-list-input>
    </f7-block> -->
    <f7-block>
      <f7-row>
        <f7-col>
          <f7-card
            title="Card header"
            content="Card with header and footer. Card headers are used to display card titles and footers for additional information or just for custom actions."
            footer="Card footer"
          ></f7-card>
        </f7-col>
        <f7-col>
          <f7-card
            title="Card header"
            content="Card with header and footer. Card headers are used to display card titles and footers for additional information or just for custom actions."
            footer="Card footer"
          ></f7-card>
        </f7-col>
      </f7-row>
    </f7-block>
    <f7-block strong>
      <f7-link href="/step2/">Go step2</f7-link>
    </f7-block>
  </f7-page>
</template>

<script>
export default {
  data: function() {
    return {
      name: ""
    };
  },
  mounted() {
    // console.log(`[About Mounted]`);
  },
  destroyed() {
    // console.log("[About Destroyed]");
  },
  methods: {
    sendData() {
      console.log("sendData");
      this.$root.$emit("eventing", "hello");
    },
    reinit(el) {
      // console.log(`[About] reinit`);
    },
    beforeremove() {
      // console.log(`[About] beforeremove`);
    },
    afterout() {
      // console.log(`[About] afterout`);
    }
  }
};
</script>

