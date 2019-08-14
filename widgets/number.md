# Number Widget

A simple number input.

## Sample
```php
use Sanjab\Widgets\NumberWidget;

$this->widgets[] = NumberWidget::create('age', 'Your age')
                            ->required()
                            ->min(18)
                            ->max(120);
```

## Properties

### min
`type: number`

minimum value.

### max
`type: number`

maximum value.
