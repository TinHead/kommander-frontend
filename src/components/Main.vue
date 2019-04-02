<template>
  <v-container
      grid-list-md
      fluid
  > 
    <v-layout
      text-xs-center
      wrap
    >
    <v-flex xs3>
      <v-card>
        <v-card-title primary-title>
          <div class="headline">
           File Panel
           </div>
        </v-card-title>
        <v-card-text>
          <ol>
            <li> test </li>
          </ol>
        </v-card-text>
      <v-card-actions>
                  <v-btn flat small color="primary">Upload</v-btn>
      </v-card-actions>
      </v-card>
    </v-flex>
    <v-flex xs9>
      <v-card>
      <v-card-title primary-title>
        <div class="headline">
           Control Panel
        </div> 
      </v-card-title>
        <v-tabs
          v-model="active"
          color="secondary"
          dark
          slider-color="primary"
        >
        <v-tab
                v-for="n in tab_items"
                :key="n"
                ripple
              >
                {{ n }}

              </v-tab>
              <v-tab-item
                v-for="n in tab_items"
                :key="n"
              >
              <v-layout row wrap>
                <Temperature v-if="n=='Temperature'"/>
              </v-layout>
                <!-- <v-card flat v-if="n == 'Temperature'">
                  
                  <v-card-text><Temperature /></v-card-text>
                </v-card> -->
              </v-tab-item>
            </v-tabs>
      </v-card>
    </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
   import Temperature from "./Temperature";
   export default {
    data () {
      return {
        tab_items: ['Temperature', 'Control', 'Gcode Terminal'],
        active: null,
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
      }
    },
    components:{
      Temperature
    },
    methods: {
      next () {
        const active = parseInt(this.active)
        this.active = (active < 2 ? active + 1 : 0)
      }
    }
  }
</script>

<style>

</style>
