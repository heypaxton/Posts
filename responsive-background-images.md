Responsive background images are easy if you can control theme in your Drupal 8 theme. Once they need to be managed by a content editor it adds some difficulty. You can absolutely position and adjust the z-index of inline images but that's no fun for responsive implementations. 

## Setup

Get a fresh install of (Drupal 8)[https://www.drupal.org/project/drupal/releases/8.2.6] or use an installation you already have. 

After you install your site, go to `admin/modules`. Enable the Responsive Image module.

Now add a theme to your site. If you don't have a theme use [ThinkBase](https://github.com/thinkshout/thinkbase). It's a project that already has the minimum requirements of a Drupal 8 theme. Go to `admin/appearance`. Install the theme and set it as default.

## Breakpoints
Let's add some breakpoints to our theme. Add a file called `<your theme name>.breakpoints.yml`. If you've used thinkbase call it `thinkbase.breakpoints.yml`. We'll use three breakpoints to keep it simple. You can learn more about D8 breakpoints in the [Drupal 8 documentation](https://www.drupal.org/docs/8/theming-drupal-8/working-with-breakpoints-in-drupal-8).

```yaml
thinkbase.small:
  label: Small 
  mediaQuery: ''
  weight: 0
  multipliers:
    - 1x

thinkbase.medium:
  label: Medium
  mediaQuery: 'all and (min-width: 560px) and (max-width: 850px)'
  weight: 1
  multipliers:
    - 1x

thinkbase.large:
  label: Large
  mediaQuery: 'all and (min-width: 851px)'
  weight: 2
  multipliers:
    - 1x
    - 2x
```

## Responsive Image Styles
Add some images styles to your site to use with your breakpoints. Visit `admin/config/media/image-styles` to add some. We can add three that match our breakpoints. I've added 3 images styles: Hero Large, Hero Medium and Hero Small. They all use scale and crop. The ratio I've chosen is arbitray. Just make each one smaller than the next. 



