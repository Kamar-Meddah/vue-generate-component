# Vue js component generator [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

CLI util for easy generate Vue js component
## Installation
```js
npm install -g vue-generate-component-typescript
```

## Usage

```bash
vgc --help
```

### Create new component
```bash
vgc footer
```
Will generate five files:

**footer.component.ts**
```typescript
import Vue from 'vue';
import Component from 'vue-class-component';

@Component({})
export default class FooterComponent extends Vue {

  mounted (){
    console.log('hello from app');
  }
  
}

```


**footer.component.html**
```html
<div class="footer">
  <h1>footer Component</h1>
</div>

```

**footer.component.scss**
```css
.footer {

}
```

**index.vue**
```html
<template src="./footer.component.html"></template>
<script src="./footer.component.ts" lang="ts"></script>
<style src="./footer.component.scss" scoped lang="scss"></style>
```

### Create new component single file
```bash
vgc -s home
```
will generate one vue file:
```javascript
<template>
  <div class="home">
    <h1>home Component</h1>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';

@Component({})
export default class HomeComponent extends Vue {

  mounted (){
    console.log('hello from app');
  }
  
}
</script>

<style scoped lang="scss">
  .home {

  }
</style>
```

### Create new directive
```bash
vgc -d test
```
will generate:

**test.directive.ts**
```javascript
import Vue from 'vue';

export const TestDirective
{

    function bind(el, binding, vnode)
    {

    }
    // When the bound element is inserted into the DOM...
    function inserted(el)
    {
        // el.focus();
    }

    function update()
    {

    }

    function unbind()
    {

    }
};

// You can also make it available globally.
Vue.directive('test', TestDirective);
```


### Create new Pipe (filter)
```bash
vgc -p test
```
will generate:

**test.pipe.ts**
```javascript
import Vue from 'vue';

export const Test = function (value) {
    return value;
};

Vue.filter('test', Test});

```
