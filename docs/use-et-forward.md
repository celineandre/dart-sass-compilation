# @use et @forward

[> Revenir au Readme](./../README.md)

## 1ère solution : Appel individuellement des fichiers de paramètrage

- _style.scss_

    ```scss
    @use 'settings/colors';
    @use 'settings/fonts';

    body {
        background-color: colors.$color1;
        font-size: fonts.$size;
    }

    // ou

    @use 'settings/colors' as *;
    @use 'settings/fonts' as *;

    body {
        background-color: $color1;
        font-size: $size;
    }

    // ou

    @use 'settings/colors' as c;
    @use 'settings/fonts' as f;

    body {
        background-color: c.$color1;
        font-size: f.$size;
    }
    ```

## 2ème solution : Appel globale des fichiers de paramètrage

- _settings/_index.scss_

    ```scss
    @forward 'colors';
    @forward 'fonts';
    ```

- _style.scss_

    ```scss
    @use 'settings';

    body {
        background-color: settings.$color1;
        font-size: settings.$size;
    }

    // ou

    @use 'settings' as s;

    body {
        background-color: s.$color1;
        font-size: s.$size;
    }
    ```
