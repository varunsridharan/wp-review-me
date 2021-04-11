# WordPress Review Me Library
This library provides developers to ask end user to review their product (theme / plugin)

[![Latest Stable Version](https://poser.pugx.org/varunsridharan/wp-review-me/version)](https://packagist.org/packages/varunsridharan/wp-review-me)
[![Total Downloads](https://poser.pugx.org/varunsridharan/wp-review-me/downloads)](https://packagist.org/packages/varunsridharan/wp-review-me)
[![Latest Unstable Version](https://poser.pugx.org/varunsridharan/wp-review-me/v/unstable)](//packagist.org/packages/varunsridharan/wp-review-me)
[![License](https://poser.pugx.org/varunsridharan/wp-review-me/license)](https://packagist.org/packages/varunsridharan/wp-review-me)
[![composer.lock available](https://poser.pugx.org/varunsridharan/wp-review-me/composerlock)](https://packagist.org/packages/varunsridharan/wp-review-me)


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
$review_instance = new Varunsridharan\WordPress\Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'type' => 'plugin', # Use theme if you are using it in a theme
    'site' => 'wordpress',
    'rating' => 3 # review link will have a default count of rating 3 which sets rating to 3 in review form
));
```

#### Plugin From Codecanyon.net
```php
$review_instance = new Varunsridharan\WordPress\Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'site' => 'codecanyon',
    'item_id' => 'xxxxxxxx'
));
```

#### Theme From themeforest.net
```php
$review_instance = new Varunsridharan\WordPress\Review_Me(array(
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

$review_instance = new Varunsridharan\WordPress\Review_Me(array(
    'days_after' => 2,
    'slug' => 'your-plugin',
    'type' => 'plugin', # Use theme if you are using it in a theme
    'site' => 'wordpress',
    'notice_callback' => 'your_plugin_review_notice_add'
));
```

## Sample Output
[![View 1](https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/screenshot-1.jpg)](https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/screenshot-1.jpg)

[![View 2](https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/screenshot-2.jpg)](https://raw.githubusercontent.com/varunsridharan/wp-review-me/master/screenshot-2.jpg)


---

<!-- START common-footer.mustache  -->
## 📝 Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

[Checkout CHANGELOG.md](https://github.com/varunsridharan/wp-review-me/blob/main/CHANGELOG.md)


## 🤝 Contributing
If you would like to help, please take a look at the list of [issues](https://github.com/varunsridharan/wp-review-me/issues/).


## 📜  License & Conduct
- [**GNU General Public License v3.0**](https://github.com/varunsridharan/wp-review-me/blob/main/LICENSE) © [Varun Sridharan](website)
- [Code of Conduct](https://github.com/varunsridharan/.github/blob/main/CODE_OF_CONDUCT.md)


## 📣 Feedback
- ⭐ This repository if this project helped you! :wink:
- Create An [🔧 Issue](https://github.com/varunsridharan/wp-review-me/issues/) if you need help / found a bug


## 💰 Sponsor
[I][twitter] fell in love with open-source in 2013 and there has been no looking back since! You can read more about me [here][website].
If you, or your company, use any of my projects or like what I’m doing, kindly consider backing me. I'm in this for the long run.

- ☕ How about we get to know each other over coffee? Buy me a cup for just [**$9.99**][buymeacoffee]
- ☕️☕️ How about buying me just 2 cups of coffee each month? You can do that for as little as [**$9.99**][buymeacoffee]
- 🔰         We love bettering open-source projects. Support 1-hour of open-source maintenance for [**$24.99 one-time?**][paypal]
- 🚀         Love open-source tools? Me too! How about supporting one hour of open-source development for just [**$49.99 one-time ?**][paypal]

<!-- Personl Links -->
[paypal]: https://sva.onl/paypal
[buymeacoffee]: https://sva.onl/buymeacoffee
[twitter]: https://sva.onl/twitter/
[website]: https://sva.onl/website/


## Connect & Say 👋
- **Follow** me on [👨‍💻 Github][github] and stay updated on free and open-source software
- **Follow** me on [🐦 Twitter][twitter] to get updates on my latest open source projects
- **Message** me on [📠 Telegram][telegram]
- **Follow** my pet on [Instagram][sofythelabrador] for some _dog-tastic_ updates!

<!-- Personl Links -->
[sofythelabrador]: https://www.instagram.com/sofythelabrador/
[github]: https://sva.onl/github/
[twitter]: https://sva.onl/twitter/
[telegram]: https://sva.onl/telegram/


---

<p align="center">
<i>Built With ♥ By <a href="https://sva.onl/twitter"  target="_blank" rel="noopener noreferrer">Varun Sridharan</a> <a href="https://en.wikipedia.org/wiki/India">
   <img src="https://cdn.svarun.dev/flag-india.jpg" width="20px"/></a> </i> <br/><br/>
   <img src="https://cdn.svarun.dev/codeispoetry.png"/>
</p>

---


<!-- END common-footer.mustache  -->
