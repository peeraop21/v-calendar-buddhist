# VCalendar Plugin for Vue 3

A calendar and date picker plugin for [Vue.js](https://vuejs.org) (requires version 3.2+).

## Install Plugin

### NPM

```shell
npm install v-calendar
```

### Yarn

```shell
yarn add v-calendar
```

## Use Plugin

:warning: **As of `v3.0.0-alpha.7`, all installation methods require manual import of component styles. This is due to Vite build restrictions in libary mode.**

```js
import 'v-calendar/style.css';
```

### Method 1: Use Globally

```js
import VCalendar from 'v-calendar';
import 'v-calendar/style.css';

// Use plugin with optional defaults
app.use(VCalendar, {})
```

```html
<!-- MyComponent.vue -->
<template>
  <VCalendar />
  <VDatePicker v-model="date" />
</template>
```

### Method 2: Use Components Globally

```js
// main.js
import { SetupCalendar, Calendar, DatePicker } from 'v-calendar';
import 'v-calendar/style.css';

// Use plugin defaults (optional)
app.use(SetupCalendar, {})

// Use the components
app.component('VCalendar', Calendar)
app.component('VDatePicker', DatePicker)
```

```html
<!-- MyComponent.vue -->
<template>
  <VCalendar />
  <VDatePicker v-model="date" />
</template>
```

### Method 3: Use Components As Needed

```js
// main.js
import { SetupCalendar } from 'v-calendar';

// Use calendar defaults (optional)
app.use(SetupCalendar, {})
```

```vue
<!-- MyComponent.vue -->
<template>
  <Calendar />
  <DatePicker v-model="date">
</template>

<script>
import { Calendar, DatePicker } from 'v-calendar';
import 'v-calendar/style.css';

export default {
  components: {
    Calendar,
    DatePicker,
  },
  data() {
    return {
      date: new Date(),
    };
  },
}
</script>
```

## Source setup

Please follow below mentioned steps to clone and build this project:

### Clone the repo

```sh
git clone https://github.com/nathanreyes/v-calendar

# Move to directory
cd v-calendar
```

### Install dependencies

```sh
yarn
```

### Switch to `/next` branch

```sh
git checkout next
```

### Build Library

```sh
# Types, ES, ESM, CommonJS, IIFE
yarn build
```

### Lint and fix files

```sh
yarn lint
```
