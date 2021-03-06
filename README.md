Selectize Input for Autoform

Adds a custom [Selectize](http://brianreavis.github.io/selectize.js/) input type for [Autoform](https://github.com/aldeed/meteor-autoform). 

## Installation

```bash
meteor add jeremy:autoform-selectize
```
The main Selectize library will be loaded via [jeremy:selectize](https://atmospherejs.com/jeremy/selectize) (which will be added automatically)

## Usage

Specify "selectize" for the `type` attribute of an Autoform input. This can be done in a number of ways:

In the schema, which will then work with a `quickForm` or `afQuickFields`:

```js
{
  tags: {
    type: [String],
    autoform: {
      type: "selectize",
      afFieldInput: {
        multiple: true,
        selectizeOptions: {}
      }
    }
  }
}
```

Or on the `afFieldInput` component or any component that passes along attributes to `afFieldInput`:

```js
{{> afQuickField name="tags" type="selectize" multiple=true }}

{{> afFormGroup name="tags" type="selectize" multiple=true }}

{{> afFieldInput name="tags" type="selectize" multiple=true }}
```

To provide selectize options, set a `selectizeOptions` attribute equal to a helper that returns the options object. Most of the `data-` attributes that the plugin recognizes should also work.

