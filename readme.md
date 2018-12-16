# WordPress Review Me Library
This library provides developers to ask end user to review their product (theme / plugin)

## Installation
The preferred way to install this extension is through [Composer](http://getcomposer.org/download/).

To install **WP_Review_Me library**, simply:

    $ composer require Varunsridharan/WP_Review_Me

The previous command will only install the necessary files, if you prefer to **download the entire source code** you can use:

    $ composer require Varunsridharan/WP_Review_Me --prefer-source

You can also **clone the complete repository** with Git:

    $ git clone https://github.com/varunsridharan/wp-review-me.git

Or **install it manually**:

[Download WP_Review_Me.php](https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/class-wp-review-me.php):

    $ wget https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/class-wp-review-me.php



## Options
| Option | Notes |
| ------ | ----- |
| `days_after` | Value should be in numbers |
| `slug` | Plugin Slug (Required) |
| `site` | Supported Sites : `wordpress` / `themeforest` / `codecanyon` |
| `item_id` | Item ID required if site is set-to `themeforest` / `codecanyon` |
| `type` | Set `plugin` or `theme` if site is set-to **wordpress** |
| `rating` | Set Int Val if site is set-to **wordpress** |
| `message` | Custom Message To Show In Admin |
| `link_label` | Review Button Label |
| `review_link` | You can override auto link generation by providing a link here |
| `notice_callback` | If you are using any admin notice handler / custom Library then you can provide a function to call when notice should be shown |



## Usage 

#### Plugin / Theme From Wordpress.org
```php
$review_instance = new Varunsridharan\WP_Review_Me\WP_Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'type' => 'plugin', # Use theme if you are using it in a theme
    'site' => 'wordpress',
    'rating' => 3 # review link will have a default count of rating 3 which sets rating to 3 in review form
));
```

#### Plugin From Codecanyon.net
```php
$review_instance = new Varunsridharan\WP_Review_Me\WP_Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'site' => 'codecanyon',
    'item_id' => 'xxxxxxxx'
));
```

#### Theme From themeforest.net
```php
$review_instance = new Varunsridharan\WP_Review_Me\WP_Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'site' => 'themeforest',
    'item_id' => 'xxxxxxxx'
));
```


#### Custom Notice Callback
```php
/**
 * $review_me is a instance of VS_WP_Review_Me Class
 */
function your_plugin_review_notice_add($review_me){
    // use your custom notice handle to add / display the notice
}

$review_instance = new Varunsridharan\WP_Review_Me\WP_Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'type' => 'plugin', # Use theme if you are using it in a theme
    'site' => 'wordpress',
    'notice_callback' => 'your_plugin_review_notice_add'
));
```
## Sample Output
[![View 1](https://raw.githubusercontent.com/varunsridharan/vs-wp-review-me/master/screenshot-1.jpg)](https://raw.githubusercontent.com/varunsridharan/vs-wp-review-me/master/screenshot-1.jpg)

[![View 1](https://raw.githubusercontent.com/varunsridharan/vs-wp-review-me/master/screenshot-2.jpg)](https://raw.githubusercontent.com/varunsridharan/vs-wp-review-me/master/screenshot-2.jpg)
