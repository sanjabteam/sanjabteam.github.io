# Sanjab
Sanjab is an admin package for laravel.

Currenly sanjab is on beta version and development to be a ready to use kit. so  **I DO NOT RECOMMEND** to use it on real world project for NOW.

[Installation](./install.md)

## Quick start
Use
```bash
php artisan sanjab:make:sanjab TestController
```
to generate a CRUD controller.

CRUD controller is a basic Create/Read/Update/Delete controller easily

> make sure controller added to config file.`config/sanjab.php` in controllers array.

each controller consist of table columns and input fields.
we call them widgets.
very basic widget is `Sanjab\Widgets\TextWidget` and you can add text fields like this in init function.
```php
$this->widgets[] = TextWidget('fieldName', 'Field placeholder')->rules('required|string|max:50')
```

You need also set properties in `properties` function.

Use
```bash
php artisan sanjab:make:setting TestSettingController
```
So you have a setting controller.
setting controllers also have widgets but without table.
you can access setting value with `setting` function.

```php
setting('group.fieldName')
```
