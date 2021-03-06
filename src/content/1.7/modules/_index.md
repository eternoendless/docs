---
title: Modules
weight: 4
pre: "<b>4. </b>"
chapter: true
---

### Chapter 4

What is a PrestaShop module?
============================

PrestaShop's extensibility revolves around modules, which are small
programs that make use of PrestaShop's functionalities and changes them
or add to them in order to make PrestaShop easier to use or more
tailored to the merchant's needs.

Technical principles behind a module
------------------------------------

A PrestaShop module consists of a main PHP file with as many other PHP
files as needed, as well as the necessary template (`.tpl`) files and
assets (images, JavaScript, CSS, etc.) to display the module's
interface, whether to the customer (on the front office) or to the
merchant (on the back office).

Any PrestaShop module, once installed on an online shop, can interact
with one or more "hooks". Hooks enable you to hook/attach your code to
the current View at the time of the code parsing (i.e., when displaying
the cart or the product sheet, when displaying the current stock, etc.).
Specifically, a hook is a shortcut to the various methods available from
the `Module` object, as assigned to that hook.

Modules' operating principles
-----------------------------

Modules are the ideal way to let your talent and imagination as a
developer express themselves, as the creative possibilities are many and
you can do pretty much anything with PrestaShop's module API.

Any module:

-   can display a variety of content (blocks, text, etc.), perform many
    tasks (batch update, import, export, etc.), interface with other
    tools, and much much more.
-   can be made as configurable as necessary; the more configurable it
    is, the easier it will be to use, and thus will be able to address
    the needs of a wider range of users.
-   can add functionalities to PrestaShop without having to edit its
    core files, thus making it easier to perform an update of PrestaShop
    without having the transpose all core changes. Indeed, you should
    always strive to stay away from core files when building a module,
    even though this may seem necessary in some situations.

Main differences between 1.6 and 1.7 modules
--------------------------------------------

PrestaShop 1.7 was built so that modules that were written for PS 1.6
could work almost as-is -- save for minor changes and a cosmetic update,
the template files being in need of adapting to the 1.7 default theme.

The major module development changes in PrestaShop 1.7 are explained in
details [in this Build
article](http://build.prestashop.com/news/module-development-changes-in-17/),
and are integrated into this updated documentation. If you already know
how to create a module that works with PS 1.6, we strongly advise you to
read that article from top to bottom in order to get up to speed with
1.7 development.

Modules folder
--------------

PrestaShop's modules are found in the `/modules` folder, which is at the
root of the PrestaShop main folder. This is true for both default
modules (provided with PrestaShop) and 3rd-party modules that are
subsequently installed.

Modules can also be part of a theme if they are really specific to it.
In that case, they would be in the theme's own `/modules` folder, and
therefore under the following path: `/themes/[my-theme]/modules`

Each module has its own sub-folder inside the `/modules` folder:
/bankwire, `/birthdaypresent`, etc. About the cache

The `/cache/class_index.php` file contains the link between the class
and the declaration file. If there is a caching issue, this file can
safely be deleted.

The `/config/xml` folder contains the list of all the base modules:

    default_country_modules_list.xml
    must_have_modules_list.xml
    tab_modules_list.xml

When the store's front-end doesn't quite reflect your changes and
emptying the browser's cache is not effective, you should try emptying
the following folders:

    /cache/smarty/cache
    /cache/smarty/compile
