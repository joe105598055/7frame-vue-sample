<template>
  <f7-page
    name="about"
    title="about"
    @page:reinit="reinit"
    @page:beforeremove="beforeremove"
    @page:afterout="afterout"
  >
    <f7-navbar title="About" back-link="Back"></f7-navbar>
    <f7-block-title>About My App</f7-block-title>
    <f7-block strong>
      <p>Fugiat perspiciatis excepturi, soluta quod non ullam deleniti. Nobis sint nemo consequuntur, fugiat. Eius perferendis animi autem incidunt vel quod tenetur nostrum, voluptate omnis quasi quidem illum consequuntur, a, quisquam.</p>
      <p>Laudantium neque magnam vitae nemo quam commodi, in cum dolore obcaecati laborum, excepturi harum, optio qui, consequuntur? Obcaecati dolor sequi nesciunt culpa quia perspiciatis, reiciendis ex debitis, ut tenetur alias.</p>
    </f7-block>
    <f7-block>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magni molestiae laudantium dignissimos est nobis delectus nemo ea alias voluptatum architecto, amet similique, saepe iste consectetur in repellat ut minus quibusdam!</p>
      <p>Molestias et distinctio porro nesciunt ratione similique, magni doloribus, rerum nobis, aliquam quae reiciendis quasi modi. Nam a recusandae, fugiat in ea voluptates fuga eius, velit corrupti reprehenderit dignissimos consequatur!</p>
      <p>Blanditiis, cumque quo adipisci. Molestiae, dolores dolorum quos doloremque ipsa ullam eligendi commodi deserunt doloribus inventore magni? Ea mollitia veniam nostrum nihil, iusto doloribus a at! Ea molestiae ullam delectus!</p>
    </f7-block>
    <f7-block>
      <f7-link href="/form/">Go Form</f7-link>
      <f7-button @click="sendData">Send Data</f7-button>
      <f7-button :route-props="obj" target="/form/" href="/form/">Target</f7-button>

    </f7-block>
  </f7-page>
</template> 

<script>
export default {
  data: function() {
    return {
      obj:{
        text:'hello'
      }
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

