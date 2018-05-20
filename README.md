# wepy-com-paper-drawer
A  useful drawer/sheet component for use in [wepyjs](https://github.com/wepyjs/wepy), a Vue-like framework for building WeChat mini programs.

## What it looks like
‘left’ mode<br/>
![left-drawer](https://user-images.githubusercontent.com/11850362/40283131-1e496a18-5cac-11e8-8b19-d2fe913ad26c.gif)<br/>
‘right’ mode<br/>
![right-drawer](https://user-images.githubusercontent.com/11850362/40283134-1ebefc60-5cac-11e8-9c0e-54460a9d4f05.gif)<br/>
‘bottom’ mode<br/>
![bottom-drawer](https://user-images.githubusercontent.com/11850362/40283128-1d933a9a-5cac-11e8-88bc-220ac482e38a.gif)<br/>
‘full’ mode<br/>
![full-drawer](https://user-images.githubusercontent.com/11850362/40283130-1e0afb7a-5cac-11e8-93b7-e4617abaa5d4.gif)<br/>

## Usage
### installation
```
npm install wepy-com-paper-drawer --save
```

### Importing the component

For example, on a page `index.wpy`
```javascript
// index.wpy
<template>
    <drawer :mode.sync="left">
    // Slot, put your WXML content of the drawer here
    </drawer>
</template>
<script>
    import wepy from 'wepy'
    import Drawer from 'wepy-com-paper-drawer'

    export default class Index extends wepy.page {
        components = {
            drawer: Drawer
        }

        data = {
            left: "left"
        }
    }
</script>
```

### Showing the drawer
Inside of a `@tap` handler (or anywhere in a wepy component or page),  you could invoke the drawer to display, i.e. show the drawer by calling the /toggle/ function
```javascript
// index.wpy
	this.$invoke('drawer', 'toggle', null)
```

### Props
There are four props exposed on `wepy-com-paper-drawer`

#### open
Default set to `true`
```javascript
    <drawer :open.sync="customOpen">
		// slot
    </drawer>
```

#### mode
The direction & style of the drawer.
Default set to `left`, available options: `left`, `right`, `bottom`, `full`
```javascript
    <drawer :mode.sync="bottom">
		// slot
    </drawer>
```

#### closeCLass
Set a custom class to the ‘x’ close icon 
```javascript
    <drawer :closeClass.sync="customCloseClass">
		// slot
    </drawer>
```

#### displayClose
Remove the ‘x’ close icon if needed
```javascript
    <drawer :displayClose.sync="hasDisplayClose">
		// slot
    </drawer>
```
