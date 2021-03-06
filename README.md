# php-cli-tiny-progress-bar

[![Build Status](https://travis-ci.org/convenient/php-cli-tiny-progress-bar.svg?branch=master)](https://travis-ci.org/convenient/php-cli-tiny-progress-bar) 
[![Coverage Status](https://coveralls.io/repos/convenient/php-cli-tiny-progress-bar/badge.svg?branch=master)](https://coveralls.io/r/convenient/php-cli-tiny-progress-bar?branch=master)


An itty bitty, super simple, 2 line progress bar for PHP command line applications.

Takes two parameters

1. The size of your `Traversable` or - if you're lazy - the `Traversable` itself.
2. How many characters across you want your progress bar to be.

It's hosted on packagist, so just add `convenient/tiny-progress-bar: "~0.1"` to your `composer.json` :)

## Example

![bash example](sample.gif "Bash Example")

### Passing the size of the Traversable

```
<?php
require_once '/vendor/autoload.php';

$progressBar = new \Convenient\ProgressPrinter(500);

for ($i=0; $i<500; $i++) {
    $progressBar->printProgress();
}
```

### Passing in the Traversable

```
<?php
require_once '/vendor/autoload.php';

$arr = new SplFixedArray(500);

$progressBar = new \Convenient\ProgressPrinter($arr);

foreach ($arr as $val) {
    $progressBar->printProgress();
}
```

### Change the size of the progress bar

```
<?php
require_once '/vendor/autoload.php';

$progressBar = new \Convenient\ProgressPrinter(500, 100);

for ($i=0; $i<500; $i++) {
    $progressBar->printProgress();
}
```
