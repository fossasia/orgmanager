<img alt="OrgManager" src="/docs/images/orgmanager.png">

![Build Status](https://github.com//fossasia/orgmanager/workflows/actions%20CIbadge.svg?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/fossasia/orgmanager/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/fossasia/orgmanager/?branch=master)
[![CodeCov](https://codecov.io/gh/fossasia/orgmanager/branch/master/graph/badge.svg)](https://codecov.io/gh/fossasia/orgmanager)
[![GitHub release](https://api.releasepage.co/v1/pages/0af37d75-ff86-4381-8f0d-5590fa8027a1/badge.svg?apiKey=live.QzuQeWHAAvXWoO5h)](http://releases.orgmanager.miguelpiedrafita.com)
[![license](https://img.shields.io/github/license/fossasia/orgmanager.svg)](LICENSE.md)
[![Packagist](https://img.shields.io/packagist/v/fossasia/orgmanager.svg)](https://packagist.org/packages/fossasia/orgmanager)

Orgmanager is an invite system for GitHub organizations created by [Miguel Piedrafita](https://github.com/m1guelpf). FOSSASIA is using the system and we decided to fork it and update it to keep it running. We also encourage the community to continue the development. An automatically deployed version of Orgmanager from the repository at FOSSASIA is available at https://orgmanager.herokuapp.com. Anyone can use it to invite others to their organization.

## Dependencies

* [PHP](https://php.net) - The programming language used.
* [MySQL](https://mysql.com) - Database software used.
* [Laravel](https://laravel.com) - The web framework used.
* [Composer](https://getcomposer.org) - The Dependency Management software used.
* [Github](https://github.com) - Thank you for your awesome API, and to the awesome people at [Github Support](https://github.com/contact)!
* [Socialite](https://github.com/laravel/socialite) - The OAuth library used.
* [PHP Github API](https://github.com/KnpLabs/php-github-api) & [Laravel Version](https://github.com/GrahamCampbell/Laravel-GitHub) - The API clients used
* [PHP reCaptcha](https://github.com/google/recaptcha) - The reCaptcha Client
* [Tailwind CSS](https://tailwindcss.com/) - The frontend framework used
* [Octicons](https://octicons.github.com/) - The icons used

## Installation

To install OrgManager, ensure you fulfill the minimum version requirements and then follow the steps below.

## Requirements

To install and run the OrgManager you need need:

- A web server of your choice - (We recommend [hotel](https://github.com/typicode/hotel) for development, as it is easy to setup and doesn't require any configuration.)
- PHP - (At least v5.6.4, although v7.* is recommended. [Installing PHP](http://php.net/manual/en/install.php))
- Some PHP libraries - (OpenSSL, PDO, Mbstring, Tokenizer, XML)
- Composer - ([Install Composer](https://getcomposer.org/download/))
- MySQL database - ([You can get one online for free](https://www.google.com/search?q=free+mysql+database)
- Git - ([Install GIT](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))

## Installation Steps

### 1. Download

Open your terminal and run

``` bash
git clone https://github.com/orgmanager/orgmanager
```

### 2. Add OrgManager to your server

Note: The following steps are outlined for typical server setups, but they can differ greatly depending on your specific setup. Normally you can get the process by searching "How to setup Laravel with X" and skipping the laravel install part. Instructions for hotel are provided, as it is the recommended server for development.

#### Setup instructions for [hotel](https://github.com/typicode/hotel):

Open the OrgManager folder with the terminal/console and run

``` bash
hotel add 'php artisan serve --port $PORT'
```

Now, if you configured custom domains, you can now access `orgmanager.{yourtld}`. If you didn't, access `localhost:2000` and click OrgManager. Yeah, it should be showing that error page, don't worry :smile:

### 3. Setup .env

Copy the `.env.example` file to an `.env` file. Open the .env file with your favourite text editor/IDE and fill the database, reCaptcha and GitHub settings (you can leave the rest empty).

### 4. Finish the setup
Open the orgmanager folder with the terminal/console and run

``` bash
composer update
```
and

``` bash
php artisan app:install
```

### 5. Done!
You have now the OrgManager beta version up an running in your server! (Note that OrgManager is not auto-updated, read the updating section for more info).

## Testing

### Automated Tests
For automated testing we use 
* the Laravel testing functionalities
* PHPUnit

### Setting up the testing enviroment
By default, the tests will run in a special database called `orgmanager_test` in `localhost` with username `root` and password `root`. If you need to change this, edit the `.env.testing` file. This is an example of a customized `.env.testing` file:

``` env
APP_ENV=testing # don't change this!
APP_KEY=base64:GIkaQ57IIVtTeTQOIh7eAFo1FAcoWkfwYPkfcOyusW4= # this is autogenerated

DB_CONNECTION=sqlite
DB_DATABASE=:memory:

CACHE_DRIVER=array # you shouldn't need to change this
SESSION_DRIVER=array # you shouldn't need to change this
QUEUE_DRIVER=sync # you shouldn't need to change this
```

Once you've customized your .env.testing file, you have to migrate the database to your test database. You can do this by running 

``` bash
php artisan migrate --env=testing
```

### Running the tests
To run the tests, run

``` bash
composer test
```

## Contributions Best Practices

### Commits

-   Write clear meaningful git commit messages (Do read [https://chris.beams.io/posts/git-commit/](https://chris.beams.io/posts/git-commit/))
-   Make sure your PR's description contains GitHub's special keyword references that automatically close the related issue when the PR is merged. (More info at [https://github.com/blog/1506-closing-issues-via-pull-requests](https://github.com/blog/1506-closing-issues-via-pull-requests) )
-   When you make very minor changes to a PR of yours (like for example fixing a failing Travis build or some small style corrections or minor changes requested by reviewers) make sure you squash your commits afterward so that you don't have an absurd number of commits for a very small fix. (Learn how to squash at [https://davidwalsh.name/squash-commits-git](https://davidwalsh.name/squash-commits-git) )
-   When you're submitting a PR for a UI-related issue, it would be really awesome if you add a screenshot of your change or a link to a deployment where it can be tested out along with your PR. It makes it very easy for the reviewers and you'll also get reviews quicker.

### Feature Requests and Bug Reports

When you file a feature request or when you are submitting a bug report to the issue tracker, make sure you add steps to reproduce it. Especially if that bug is some weird/rare one.

### Join the development

-   Before you join development, please set up the project on your local machine, run it and go through the application completely. Press on any button you can find and see where it leads to. Explore. (Don't worry ... Nothing will happen to the app or to you due to the exploring :wink: Only thing that will happen is, you'll be more familiar with what is where and might even get some cool ideas on how to improve various aspects of the app.)
-   If you would like to work on an issue, drop in a comment at the issue. If it is already assigned to someone, but there is no sign of any work being done, please feel free to drop in a comment so that the issue can be assigned to you if the previous assignee has dropped it entirely.

## License

Licensed under the Mozilla Public License (MPL). For more information, checkout the [LICENSE](LICENSE.md).
