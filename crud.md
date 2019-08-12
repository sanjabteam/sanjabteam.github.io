# CRUD
CRUD Controllers are controllers that handle resources Create/Edit/Update/Delete. CRUD Controllers working with a model and list of the model fields that in sanjab we call them Widget. Each widget handling operation like saving, form field, view field, table field, search, sort and etc.

## Example
Let's create a sample crud controller step by step. Our sample is a simple **Category** resource that contains name, description, and image.

### Step 1
Create a model and migrations.
```bash
php artisan make:model -m Category
```

### Step 2
Fill migration and model.
```php
Schema::create('categories', function (Blueprint $table) {
    $table->bigIncrements('id');
    $table->string('name');
    $table->string('image')->nullable();
    $table->text('description')->nullable();
    $table->timestamps();
});
```
Model:
```php
class Category extends Model
{
    protected $fillable = [
        'name',
        'image',
        'description'
    ];
}
```

### Step 3
Migrate.
```bash
php artisan migrate
```

### Step 4
Make Sanjab controllers.
```bash
php artisan sanjab:make:crud CategoryController
```

### Step 5
Change the content of `app/Http/Controllers/Admin/Crud/CategoryController.php`.

```php
<?php

namespace App\Http\Controllers\Admin\Crud;

use Sanjab\Widgets\IdWidget;
use Sanjab\Helpers\MaterialIcons;
use Sanjab\Helpers\CrudProperties;
use Sanjab\Controllers\CrudController;
use Illuminate\Database\Eloquent\Model;
use Sanjab\Widgets\TextAreaWidget;
use Sanjab\Widgets\TextWidget;
use Sanjab\Widgets\File\UppyWidget;

class CategoryController extends CrudController
{
    protected static function properties(): CrudProperties
    {
        return CrudProperties::create('categories')
                ->model(\App\Category::class)
                ->title("Category")
                ->titles("Categories")
                ->icon(MaterialIcons::GROUP_WORK);
    }

    protected function init(string $type, Model $item = null): void
    {
        $this->widgets[] = IdWidget::create();
        $this->widgets[] = TextWidget::create('name')
                            ->required();
        $this->widgets[] = TextAreaWidget::create('description');
        $this->widgets[] = UppyWidget::image('image')
                            ->width(512)
                            ->height(512);
    }
}
```

### Step 6
Done!

Open `yoursite/admin` and open **Categories** link in sidebar. Your CRUD is ready to use.
If you don't see link make sure your controller has been added to `controllers` in `config/sanjab.php`.
