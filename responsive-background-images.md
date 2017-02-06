Responsive background images are easy if you can control theme in your Drupal 8 theme. Once they need to be managed by a content editor it adds some difficulty. You can absolutely position and adjust the z-index of inline images but that's no fun for responsive implementations. 

# Setup

Get a fresh install of (Drupal 8)[https://www.drupal.org/project/drupal/releases/8.2.6] or use an installation you already have. 

After you install your site, go to `admin/modules`. Enable the Responsive Image module.

Now add a theme to your site. If you don't have a theme use [ThinkBase](https://github.com/thinkshout/thinkbase). It's a project that already has the minimum requirements of a Drupal 8 theme. 

Let's add some breakpoints to our theme. Add a file called `<your theme name>.breakpoints.yml`. If you've used thinkbase call it `thinkbase.breakpoints.yml`. We'll use three breakpoints to keep it simple. You can learn more about D8 breakpoints in the [Drupal 8 documentation](https://www.drupal.org/docs/8/theming-drupal-8/working-with-breakpoints-in-drupal-8).

```yaml

```
