# Text Area Widget

A simple textarea input.

## Sample
```php
use Sanjab\Widgets\TextAreaWidget;

$this->widgets[] = TextAreaWidget::create('name', 'field Title')
                            ->required()
                            ->translation();
```
## Properties

### rows
`type: int`

Rows attribute of textarea
