# Simplux template

A simple, lightweight & elegant template engine for PHP.

## Example code:

### Render function:

```php
Template::view('index.splx', [
    'title' => 'Home Page',
    'colors' => ['red', 'blue', 'green']
]);
```

_index.splx:_

```html
[# extends 'layout.splx' #]

[# block 'title' #]
    {{ $title }}
[# endblock #]

[# block 'content' #]
    <h1>Home</h1>
    <p>Welcome to the home page, list of colors:</p>
    <ul>
        [# foreach($colors as $color): #]
            <li>{{ $color }}</li>
        [# endforeach #]
    </ul>

    [# if (1 < 2): #]
        <p>Hello world!</p>
    [# endif #]

    [# if (3 > 5): #]
        <p>Hello world!</p>
    [# else: #]
        <h1>Yee!</h1>
    [# endif #]

[# endblock #]
```

_layout.splx:_

```html
<!DOCTYPE html>
<html>

<head>
    <title>[# yield 'title' #]</title>
    <meta charset="utf-8">
</head>

<body>
    [# yield 'content' #]
</body>

</html>
```
