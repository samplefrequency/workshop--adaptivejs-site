#Step 5: Style the header

Now that we've added content to the header, we need to style it.

##Task

###Style the Header

1. Open the file `_header.scss` found under **/assets/styles/templates/partials**

    This file was generated by the Adaptive.js project generator with some default styles. We'll need to replace these with styles for our site's header.

2. Replace the file contents with the following:

    ```SCSS
    // Header
    // ===

    .t-header {
        display: flex;
        padding: $v-space $small-h-space;
    }


    // Header: Logo
    // ---
    //
    // 1. Height comes from the logo img tag
    // 2. Legacy flexbox fix

    .t-header__logo {
        flex: 1 1 auto;
        padding: 0 $h-space;

        a {
            display: block; // 2
            height: 39px; //1
        }

        img {
            max-height: 100%;
        }
    }


    // Header: Cart
    // ---

    .t-header__cart {
        flex: 1 0 auto;
    }


    // Header: Menu, Logo AND Cart!
    // ---

    .t-header__menu,
    .t-header__logo,
    .t-header__cart {
        display: flex;
        align-items: center;
    }
    ```

    We've got the header layout set up, but the menu and cart buttons aren't visible yet.

3. Create a new file called `_button.scss` in the folder **/assets/styles/components**

4. Add the following content to the file:

    ```SCSS
    // Button
    // ===

    .c-button {
        @extend %button;
    }


    // Button Themes
    // ---

    .c-button.c--brand {
        border: 0;

        background-color: $brand-color;

        color: white;
    }
    ```

5. Open the file `_components.scss` found under **/assets/styles**

6. Add the `_button.scss` file to the list of components

    ```SCSS
    // Project Components
    // ------------------
    //
    // Styles for project-specific components.
    //
    // eg. @import 'components/button';

    @import 'components/card';
    @import 'components/product-list';
    @import 'components/price';
    @import 'components/button';
    ```

7. Now when we have common button styles we need to adjust our header menu button a little. Open `_header.scss` file found under **/assets/styles/templates/** partials again and add button modifications within `.t-header__menu block`

    ```SCSS
    // Header: Menu
    // ---

    .t-header__menu {
        flex: 1 0 auto;

        .c-button {
            display: block;
            min-width: 45px;
            min-height: 45px;

            background-image: url('/images/menu.png');
            background-repeat: no-repeat;
            background-position: center;
            background-size: 25px auto;
        }
    }
    ```

8. Repeat steps 3-6 to add another component called `_cart-count` with the following styles:

    ```SCSS
    // Cart Count
    // ===
    //
    // 1. Absolutely positioned number badge relative to the parent .c-cart-count
    // 2. Width must account for the presence of the number badge

    $cart-count__cauldron-width: 30px;
    $cart-count__cauldron-height: 40px;
    $cart-count__badge-size: 20px;
    $cart-count__width-with-badge: $cart-count__cauldron-width + ($cart-count__badge-size / 2);

    .c-cart-count {
        position: relative; // 1

        width: $cart-count__width-with-badge; // 2
        height: $cart-count__cauldron-height;

        background: url('/images/cauldron.png') top left no-repeat;

        .c-cart-count__number {
            position: absolute; // 1
            top: 0;
            right: 0;
        }
    }


    // Card Count: Number
    // ---
    //
    // 1. Make a circle!

    .c-cart-count__number {
        display: block;
        width: $cart-count__badge-size;
        height: $cart-count__badge-size;
        border-radius: 50%; // 1

        background-color: $accent-color;
        color: #fff;

        font-family: $oswald;
        font-weight: 300;
        text-align: center;
    }
    ```

9. Run `grunt preview`

10. View the mobile site in your browser

    Your header should look like this:

    ![Header final styling](https://s3.amazonaws.com/uploads.hipchat.com/15359/64553/Z8Dwb5hT0q9nYXO/Screen%20Shot%202015-01-19%20at%2010.28.56%20AM.png)


## Ready to Continue?

When you're ready to continue, run the following command:

```
git reset --hard HEAD && git clean -df && git checkout step-6-update-footer
```

Then, follow the directions in that branch's [README](https://github.com/mobify/workshop--adaptivejs-site/blob/step-6-update-footer/README.md)
