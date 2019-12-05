<template>
    <v-app>
        <v-dialog v-model="showLoading" persistent>
            <v-card>
                <v-card-title class="headline">Loading game assets</v-card-title>
                <v-card-text>Please wait a moment, game is loading...</v-card-text>
            </v-card>
        </v-dialog>

        <v-layout class="buildings">
                        <h2>Guns</h2>

                        <div class="buy-buttons">
                            <v-btn default class="green" :class="{ active:buyAmount == 1 }" @click.native="setBuyAmount(1)">Buy 1</v-btn>
                            <v-btn default class="green" :class="{ active:buyAmount == 10 }" @click.native="setBuyAmount(10)">Buy 10</v-btn>
                            <v-btn default class="green" :class="{ active:buyAmount == 100 }" @click.native="setBuyAmount(100)">Buy 100</v-btn>
                        </div>
                        
                        <v-layout class="gun" v-for="(gun, gunIndex) in guns" :key="gunIndex" v-if="gun.owned > 0 || showGun(gun)">
                            <v-flex xs5>
                                <div v-if="gun.unlocked">
                                    <v-tooltip left v-if="gun.unlocked">
                                        <span slot="activator">
                                            {{ gun.name }} ({{ gun.owned }} owned)
                                        </span>
                                        <span v-html="gunText(gun)"></span>
                                    </v-tooltip>
                                </div>
                                <div v-else>
                                    <span slot="activator">
                                        <span :class="{ redacted:gun.unlocked == false }">{{ gun.name }}</span>
                                    </span>
                                </div>
                            </v-flex>
                        </v-layout>
                    </v-layout>
                </v-flex>
                
<script>
    import Big from "big.js";
    import EventBus from './eventBus.js';
    import Words from "./words.js";
    import Options from './options.js';
    import DefaultData from './defaultData.js';
    import GameData from "./gameData.js";
    import FlavorText from "./flavorText.js";
    import Stats from "./stats.js";
    import Utils from "./utils.js";
    import Particles from "./particles.js";
    import Sounds from "./sounds.js";
    import SaveLoad from "./saveLoad.js";
   
    export default {
        data: function () {
            return DefaultData.data();
        },
        
 </script>
