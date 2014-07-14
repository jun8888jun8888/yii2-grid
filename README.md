yii2-grid
=========

Yii2 GridView on steroids. A module with various modifications and enhancements to one of the most used widgets by Yii developers. The widget contains new additional Grid Columns with enhanced settings for Yii Framework 2.0. The widget also incorporates various Bootstrap 3.x styling options.
Refer [detailed documentation](http://demos.krajee.com/grid) and/or a [complete demo](http://demos.krajee.com/grid-demo).

## Latest Release
The latest version of the module is v1.7.0 released on 14-Jul-2014. Refer the [CHANGE LOG](https://github.com/kartik-v/yii2-grid/blob/master/CHANGE.md) for details.

> NOTE: This extension depends on the [kartik-v/yii2-widgets](https://github.com/kartik-v/yii2-widgets) extension which in turn depends on the
[yiisoft/yii2-bootstrap](https://github.com/yiisoft/yii2/tree/master/extensions/bootstrap) extension. Check the 
[composer.json](https://github.com/kartik-v/yii2-grid/blob/master/composer.json) for this extension's requirements and dependencies. 
Note: Yii 2 framework is still in active development, and until a fully stable Yii2 release, your core yii2-bootstrap packages (and its dependencies) 
may be updated when you install or update this extension. You may need to lock your composer package versions for your specific app, and test 
for extension break if you do not wish to auto update dependencies.

## Module
The extension has been created as a module to enable access to advanced features like download actions (exporting as csv, text, html, or xls). You should configure the module with a name of `gridview` as shown below:
```php
'modules' => [
   'gridview' =>  [
        'class' => '\kartik\grid\Module'
    ]
],
```

## GridView
### \kartik\grid\GridView
The following functionalities have been added/enhanced:

### Table Styling (Enhanced)
Control various options to style your grid table. Added `containerOptions` to customize your grid table container.

### Custom Header & Footer (New)
Add custom header or footer rows, above / below your default grid header and footer.

### Floating Header (New)
Allows the grid table to have a floating table header. Uses the [JQuery Float THead plugin](http://mkoryak.github.io/floatThead) to display a seamless floating table header. 

### Panel (New)
Allows configuration of GridView to be enclosed in a panel that can be styled as per  Bootstrap 3.x. The panel will enable configuration of  various
sections to embed content/buttons, before and after header, and before and after footer.

### Page Summary (New)
This is a new feature added to the GridView widget. The page summary is an additional row above the footer - for displaying the
summary/totals for the current GridView page. The following parameters are applicable to control this behavior:

- `showPageSummary`: _boolean_ whether to display the page summary row for the grid view. Defaults to `false`.
- `pageSummaryRowOptions`:  _array_, HTML attributes for the page summary row. Defaults to `['class' => 'kv-page-summary warning']`.

### Export Grid Data (New)
This is a new feature added to the GridView widget. It allows you to export the displayed grid content as HTML, CSV, TEXT, or EXCEL. It uses the rendered grid data on client to convert to one of the format specified using JQuery. 
This is supported across all browsers. The following are new features added since release v1.6.0:

- Ability to preprocess and convert column data to your desired value before exporting. There is a new property `exportConversions` that can be setup in GridView. 
For example, this currently is set as a default to convert the HTML formatted icons for BooleanColumn to user friendly text like `Active` or `Inactive` after export.
- Hide any row or column in the grid by adding one or more of the following CSS classes:
    - `skip-export`: Will skip this element during export for all formats (`html`, `csv`, `txt`, `xls`).
    - `skip-export-html`: Will skip this element during export only for `html` export format.
    - `skip-export-csv`: Will skip this element during export only for `csv` export format.
    - `skip-export-txt`: Will skip this element during export only for `txt` export format.
    - `skip-export-xls`: Will skip this element during export only for `xls` (excel) export format.
    These CSS can be set virtually anywhere. For example `headerOptions`, `contentOptions`, `beforeHeader` etc.

## Data Column (Enhanced)
### \kartik\grid\DataColumn
The default Yii data column has been enhanced with various additional parameters. Refer [documentation](http://demos.krajee.com/grid#data-column) for details.

## Formula Column (New)
### \kartik\grid\FormulaColumn
This is a new grid column class that extends the \kartik\grid\DataColumn class. It allows calculating formulae just like in spreadsheets - based on
values of other columns in the grid. The formula calculation is done at grid rendering runtime and does not need to query the database. Hence you can use formula columns
within another formula column. Refer [documentation](http://demos.krajee.com/grid#formula-column) for details.

## Boolean Column (New)
### \kartik\grid\BooleanColumn
This is a new grid column class that extends the \kartik\grid\DataColumn class. It automatically converts boolean data (true/false) values to user friendly indicators or labels (that are configurable). 
Refer [documentation](http://demos.krajee.com/grid#boolean-column) for details. The following are new features added since release v1.6.0:

- `BooleanColumn` icons have been setup as `ICON_ACTIVE` and `ICON_INACTIVE` constants in GridView.

## Action Column (Enhanced)
### \kartik\grid\ActionColumn
Enhancements of `\yii\grid\ActionColumn` to include optional dropdown Action menu and work with the new pageSummary and a default styling to work for many scenarios. Refer [documentation](http://demos.krajee.com/grid#action-column) for details.
The following are new features added since release v1.6.0:
- `ActionColumn` content by default has been disabled to appear in export output. The `skip-export` CSS class has been set as default in `headerOptions` and `contentOptions`.

## Serial Column (Enhanced)
### \kartik\grid\SerialColumn
Enhancement of `\yii\grid\SerialColumn` to work with the new pageSummary and a default styling to work for many scenarios. Refer [documentation](http://demos.krajee.com/grid#serial-column) for details.

## Checkbox Column (Enhanced)
### \kartik\grid\CheckboxColumn
Enhancements of `\yii\grid\CheckboxColumn` to work with the new pageSummary and a default styling to work for many scenarios. Refer [documentation](http://demos.krajee.com/grid#checkbox-column) for details.

### Demo
You can see detailed [documentation](http://demos.krajee.com/grid) and [demonstration](http://demos.krajee.com/grid-demo) on usage of the extension.

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

> Note: You must set the `minimum-stability` to `dev` in the **composer.json** file in your application root folder before installation of this extension.

Either run

```
$ php composer.phar require kartik-v/yii2-grid "dev-master"
```

or add

```
"kartik-v/yii2-grid": "dev-master"
```

to the ```require``` section of your `composer.json` file.

## Usage
```php
use kartik\widgets\GridView;
```

## License

**yii2-grid** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.