# Password Widget

A simple password input.

## Sample
```php
use Sanjab\Widgets\PasswordWidget;

$this->widgets[] = PasswordWidget::create('password')
    ->rules('required|min:8');
```
