---
nav_order: 100
parent: Widgets
---
# Password Widget

A simple password input.

## Sample
```php
use Sanjab\Widgets\PasswordWidget;

$this->widgets[] = PasswordWidget::create('password')
    ->rules('required|min:8');
```
