Twig env tag
============

  To change configuration you have to remove cached templates.

## Usage

```php
	$twig = new Twig_Environment(new Twig_Loader_Filesystem('/path/to/templates'));
	$twig->addTokenParser(new \TwigEnv\TokenParser('environment'));
```

```twig
  {% env 'production' %}
  	<div>Production specific fragment of code</div>
  {% env 'development' %}
  	<div>Development specific fragment of code</div>
  {% env not 'production' %}
  	<div>Match any environment, except production</div>
  {% env 'development_*' %}
  	<div>Match any environment with name starting with "development_"</div>
  {% env not %}
  	<div>In unknown environment</div>
  {% endenv %}
```