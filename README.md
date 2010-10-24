# Form Replacements

Creates styleable elements that function like standard form elements complete with
keyboard navigation and selection.

## History

The classes in this project started in [mootools-plugins](http://github.com/bryanjswift/mootools-plugins)
but in order to get them submitted to the forge they needed to be broken up more logically.

This repository breaks out just the Classes that represent styleable form elements.

## Build

Build via [Packager][packager], requires [MooTools Core][core] to be registered to Packager already.

[packager]: http://github.com/kamicane/packager
[core]: http://github.com/mootools/mootools-core

    ./packager register /path/to/form-replacements
    ./packager build Form-Replacements/* > form-replacements.js

To build this plugin without external dependencies use

    ./packager build Form-Replacements/* +use-only Form-Replacements > form-replacements.js

## How To Use

There are a couple of different classes to replace forms.

### Form.Check and Form.CheckGroup

`Form.Check` will create an individual checkbox replacement. It wraps the passed in
`input[type=checkbox]` in a `div.check` (it also copies class names). So:

    <input type="checkbox" class="mycheck" name="mycheckName" id="mycheckId" value="mycheckValue" />

becomes

    <div class="check mycheck" id="mycheckIdCheck">
      <input type="checkbox" class="mycheck" name="mycheckName" id="myCheckId" value="mycheckValue" />
    </div>

`Form.CheckGroup` does `Form.Check` creation for each `input[type=checkbox]` inside the
element passed to the `Form.CheckGroup` constructor.

### Form.Radio and Form.RadioGroup

`Form.Radio` behaves exactly like `Form.Check` except that the class it adds is radio. So:

    <input type="radio" class="mycheck" name="mycheckName" id="mycheckId" value="mycheckValue" />

becomes

    <div class="radio mycheck" id="mycheckIdCheck">
      <input type="radio" class="mycheck" name="mycheckName" id="myCheckId" value="mycheckValue" />
    </div>

`Form.RadioGroup` behaves like `Form.CheckGroup` except it creates `Form.Radio` instances
rather than `Form.Check` instances.

### Form.Dropdown and Form.SelectOption

`Form.Dropdown` replaces a `<select>` input with a series of nested elements which can be used
to simulate the functionality of the `<select>`. So:

    <select name="myselect" id="myselectId" class="myselectClass">
      <option>1</option>
      <option>2</option>
      <option>3</option>
    </select>

becomes

    <div class="myselectClass select" id="myselectIdDropdown">
      <div class="menu">
        <div class="list">
          <ul class="options">
            <li class="option">1</li>
            <li class="option ">2</li>
            <li class="option ">3</li>
          </ul>
        </div>
      </div>
      <div class="selection">
        <div class="dropdownBackground"></div>
        <span class="selectionDisplay">1</span>
        <input type="text" id="myselectId" name="myselect">
      </div>
    </div>

`Form.SelectOption` is used by `Form.Dropdown` but should not be used alone.

#### More Information

For more detailed information about the classes see the
[documentation](http://bryanjswift.github.com/mootools-form-replacements)

## Demo

See the [documentation](http://bryanjswift.github.com/mootools-form-replacements)