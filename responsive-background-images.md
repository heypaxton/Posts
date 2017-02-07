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

These image styles can now be used in a responsive way. Go to `admin/config/media/responsive-image-style` and add a responsive image style called "Hero Image." Set the breakpoint group to your theme name or to ThinkBase, if you are using that one. For each of our breakpoints use the option "Select a single image style." For large use "Hero Large", for medium use "Hero Medium and for small use "Hero Small." We can just use the original image for the fallback image.

The last thing we want to do is configure our content type to use the responsive image style we've created. D8 has a default content type "Article" that already has an image field. Go to `admin/structure/types/manage/article/display` and change the image format to to Responsive Image. Click the gear to set the responsive image style to "Hero image." Click save. Let's go create some content.

## Adding an image to our content
Create an article and add an image that's large enough to match your image styles. 
