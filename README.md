# &lt;eel-translate&gt;

This is a very simple custom element that allows alternate content to be displayed based on a language parameter.



## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install eel-translate --save
```

Or [download as ZIP](https://github.com/my-user/eel-translate/archive/master.zip).

## Usage

1. Import polyfill:

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents-lite.min.js"></script>
    ```

2. Import custom element:

    ```html
    <link rel="import" href="bower_components/eel-translate/eel-translate.html">
    ```

3. Start using it!



    ```html
    Change language:
    <a onclick="changeLanguage('en')" href="#">english</a>
    <a onclick="changeLanguage('fr')" href="#">french</a>
    <a onclick="changeLanguage('zh')" href="#">mandarin</a>

    <eel-translate current="en">
      <span lang="en" default="true">Hello!</span>
      <span lang="fr">Bonjour!</span>
      <span lang="zh">你好!</span>
    </eel-translate>

    <script>
      function changeLanguage(newLang) {
        var elements = document.querySelectorAll("eel-translate");
        for (var i = 0; i < elements.length; ++i) {
          var element = elements[i];
          element.setAttribute("current", newLang);
        }
      }
    </script>
    ```
    It will display the value in the span with the `lang` attribute that matches the value in the `current` attribute.

    Determining the language key to use is outside the scope of this element.


## Options

Attribute         | Options     | Default      | Description
---               | ---         | ---          | ---
`current`         | *string*    | `en`         | The current language to use in the element.



## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

1. Install [bower](http://bower.io/) & [polyserve](https://npmjs.com/polyserve):

    ```sh
    $ npm install -g bower polyserve
    ```

2. Install local dependencies:

    ```sh
    $ bower install
    ```

3. Start development server and open `http://localhost:8080/components/eel-translate/`.

    ```sh
    $ polyserve
    ```

4. Testing

   Open browser and open `http://localhost:8080/components/eel-translate/test/`

   or

   Install Web Component Tester

   `npm install -g web-component-tester`

   then run

   `wct`

## History

For detailed changelog, check [Releases](https://github.com/my-user/eel-translate/releases).

## License

[MIT License](http://opensource.org/licenses/MIT)
