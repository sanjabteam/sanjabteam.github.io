---
nav_order: 100
parent: Widgets
---
# Text Widget

A simple text input.

## Sample
```php
use Sanjab\Widgets\TextWidget;

$this->widgets[] = TextWidget::create('name', 'field Title')
                            ->required()
                            ->translation();
```
