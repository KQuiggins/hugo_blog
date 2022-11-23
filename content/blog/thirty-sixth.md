---
title: "Vue.js & Copy to Clipboard"
date: 2022-11-23T17:48:16-05:00
draft: false
author: "Kenneth Quiggins"
---
Today I made a webpage that transforms a square on a webpage to different shapes using transform on the X, Y, and Z axis. Once you get the shape that you want you can copy the CSS properties to your clipboard.

In my index.html file I have 3 sliders representing X, Y, and Z axis.
```
<label>rotateX: {{rotateX}}; </label>
<input v-model="rotateX" type="range" min="-180" max="180" />

<label>rotateY: {{rotateY}}; </label>
<input v-model="rotateY" type="range" min="-180" max="180" />

<label>rotateZ: {{rotateZ}}; </label>
<input v-model="rotateZ" type="range" min="-180" max="180" />
``` 
I have two buttons one to copy the CSS properties to the clipboard and one to reset the sliders to 0.
```
<button type="button" @click.prevent="reset">Reset</button>
<button type="button" @click.prevent="copy">Copy</button>
```
In my app.js file I have a Vue instance that has the data for the sliders and the methods for the buttons. The copy method uses the navigator.clipboard.writeText() method to copy the CSS properties to the clipboard. This method should also be asynchronous using the async and await keywords per the documentation. It is also supported on all major browser but may not work on older browsers.
```
Vue.createApp({
    data(){
        return {
            perspective: 100,
            rotateX: 0,
            rotateY: 0,
            rotateZ: 0

        }
    },
    computed: {
        box(){
            return {
                transform: `
                perspective(${this.perspective}px)
                rotateX(${this.rotateX}deg)
                rotateY(${this.rotateY}deg)
                rotateZ(${this.rotateZ}deg)
                `
            }
        }
    },
    methods: {
        reset() {
            this.perspective = 100
            this.rotateX = 0
            this.rotateY = 0
            this.rotateZ = 0
        },
        async copy(){
            let text = `transform:${this.box.transform};`
            await navigator.clipboard.writeText(text)

            alert("CSS Copied to Clipboard!")
        }
    }
}).mount('#app')
```
Happy Coding!!!