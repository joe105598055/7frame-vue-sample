<template>
  <f7-page name="form">
    <f7-navbar title="Form" back-link="Back"></f7-navbar>
  <f7-block>
      <f7-link href="/about/">Go About</f7-link>
    </f7-block>
    <f7-block-title>Form Example</f7-block-title>
    <f7-list no-hairlines-md>
      <f7-list-input label="Name" type="text" placeholder="Your name"></f7-list-input>

      <f7-list-input label="E-mail" type="email" placeholder="E-mail"></f7-list-input>

      <f7-list-input label="URL" type="url" placeholder="URL"></f7-list-input>

      <f7-list-input label="Password" type="password" placeholder="Password"></f7-list-input>

      <f7-list-input label="Phone" type="tel" placeholder="Phone"></f7-list-input>

      <f7-list-input label="Gender" type="select">
        <option>Male</option>
        <option>Female</option>
      </f7-list-input>

      <f7-list-input
        label="Birth date"
        type="date"
        placeholder="Birth day"
        defaultValue="2014-04-30"
        @input="date=$event.target.value"
        :value="date"
        required
        info="this is info!"
      ></f7-list-input>

      <f7-list-item title="Toggle">
        <f7-toggle slot="after"></f7-toggle>
      </f7-list-item>

      <f7-list-input label="Range" :input="false">
        <f7-range slot="input" :value="50" :min="0" :max="100" :step="1"></f7-range>
      </f7-list-input>

      <f7-list-input type="textarea" label="Textarea" placeholder="Bio"></f7-list-input>
      <f7-list-input type="textarea" label="Resizable" placeholder="Bio" resizable></f7-list-input>
    </f7-list>

    <f7-block-title>Buttons</f7-block-title>
    <f7-block strong>
      <f7-row tag="p">
        <f7-button class="col">Button</f7-button>
        <f7-button class="col" fill>Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" raised>Raised</f7-button>
        <f7-button class="col" raised fill>Raised Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" round>Round</f7-button>
        <f7-button class="col" round fill>Round Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" outline>Outline</f7-button>
        <f7-button class="col" round outline>Outline Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" small outline>Small</f7-button>
        <f7-button class="col" small round outline>Small Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" small fill>Small</f7-button>
        <f7-button class="col" small round fill>Small Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" large raised>Large</f7-button>
        <f7-button class="col" large fill raised>Large Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" large fill raised color="red">Large Red</f7-button>
        <f7-button class="col" large fill raised color="green">Large Green</f7-button>
      </f7-row>
    </f7-block>

    <f7-block-title>Checkbox group</f7-block-title>
    <f7-list>
      <f7-list-item checkbox name="my-checkbox" value="Books" title="Books" @change="changeList"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Movies" title="Movies" @change="changeList"></f7-list-item>
      <f7-list-item checkbox name="my-checkbox" value="Food" title="Food" @change="changeList"></f7-list-item>
    </f7-list>

    <f7-block-title>Radio buttons group</f7-block-title>
    <f7-list>
      <f7-list-item radio name="radio" value="Books" title="Books"></f7-list-item>
      <f7-list-item radio name="radio" value="Movies" title="Movies"></f7-list-item>
      <f7-list-item radio name="radio" value="Food" title="Food"></f7-list-item>
      <f7-block>
        <f7-button class="col" reload-all fill color="green" @click="submit" href="/">Submit</f7-button>
      </f7-block>
    </f7-list>
  </f7-page>
</template>
<script>
export default {
  props:['obj'],
  data() {
    return {
      date: null,
      checkmodel:[]
    };
  },
  mounted(){
    console.log('[form mounted]')
  },
  destroyed(){
    console.log(`[form destroyed]`)
  },
  methods:{
    submit(){
      // console.log(this.date)
      console.log(this.checkmodel)
    },
    changeList(el){
      if(el.target.checked && this.checkmodel.indexOf(el.target.value)===-1){
        this.checkmodel.push(el.target.value)
      }
      if(!el.target.checked){
        this.checkmodel.splice( this.checkmodel.indexOf(el.target.value), 1 );
      }
    }
  },
};
</script>
