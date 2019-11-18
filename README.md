# vue-date-picker

[![npm version][npm-image]][npm-url] [![david deps][david-image]][david-url] [![npm license][license-image]][download-url]

datepicker component for Vue 2.x
This is the original repo : https://github.com/8788/vue-date-picker

I made this repo because 8788/vue-date-picker did not fix the problem that was reported by the user and some pull requests were not merged to the master.

## Screenshot

![screenshot](screenshot.png)

## Instllation

```bash
$ npm install @madedwi/vuedatepicker
```

## Usage

```html
<template>
  <div class="demo">
    <datepicker :readonly="true" format="YYYY-MM-DD" name="date1"></datepicker>
    <datepicker v-model="exampledate" format="YYYY-M-D" name="date2" :input-attr="{ 'data-test': 'value' }"></datepicker>
    <datepicker :readonly="true" format="MMM/D/YYYY" name="date3" :disabled-date="disabledDate"></datepicker>
  </div>
</template>

<script>
import datepicker from 'vue-date-picker'

export default {
  components: {
    datepicker
  },
  data(){
    return {
      exampledate : '2019-11-10'
    }
  },
  methods: {
    disabledDate (date) {
      return date.getTime() < Date.now()
    }
  }
}
</script>
```

## Prop

| Prop                          | Type               | Default     | Description                              |
|-------------------------------|--------------------|:-----------:|------------------------------------------|
| value                         | String             | --          | Date value of the datepicker             |
| name                          | String             | --          | Input name property                      |
| format                        | String             | YYYY-MM-DD  | Date formatting string                   |
| readonly                      | String             | false       | Input readonly property                  |
| input-class                   | Array \| Object    | --          | Binding class for input                  |
| input-style                   | Array \| Object    | --          | Binding inline style for input           |
| input-attr                    | Object             | --          | Binding attribute for input              |
| calendar-class                | Array \| Object    | --          | Binding class for calendar               |
| calendar-style                | Array \| Object    | --          | Binding inline style for calendar        |
| calendar-attr                 | Object             | --          | Binding attribute for calendar           |
| disabled-date                 | Function           | --          | A function that determines if you want to disable dates |

## License

[The MIT License](http://opensource.org/licenses/MIT)

[npm-image]: https://img.shields.io/npm/v/vue-date-picker.svg?style=flat-square
[npm-url]: https://npmjs.org/package/vue-date-picker
[david-image]: https://img.shields.io/david/8788/vue-date-picker.svg?style=flat-square
[david-url]: https://david-dm.org/8788/vue-date-picker
[download-url]: https://npmjs.org/package/vue-date-picker
[license-image]: https://img.shields.io/npm/l/vue-date-picker.svg