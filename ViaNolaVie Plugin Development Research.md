**ViaNolaVie Plugin Development Research**

1.  General Resources:

    a.  [[Writing a
        > Plugin]{.underline}](https://codex.wordpress.org/Writing_a_Plugin)​-
        > General information about what a plugin is and logistics for
        > writing and integrating it. Also has a list of general tips to
        > keep in mind during development.

    b.  [[Plugin
        > API]{.underline}](https://codex.wordpress.org/Plugin_API)​-
        > Wordpress codex.

    c.  [[Plugin
        > Resources]{.underline}](https://codex.wordpress.org/Plugin_Resources)​-
        > Contains links to blogs and helpful articles form plugin
        > developers.

    d.  [[PHP Coding
        > Standards]{.underline}](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/)

2.  FTP

    a.  FTP (File Transfer Protocol) is software that allows the
        > transfer of files from a personal computer to the web hosting
        > server.

    b.  In order to upload a plugin to a wordpress site, the WordPress
        > must be accessed using FTP with credentials provided by the
        > hosting service.

    c.  We need to know more about if Tulane has an FTP that they use
        > and who has the login credentials we would need to access the
        > VNV website via an FTP Client

    d.  [[https://www.wpbeginner.com/beginners-guide/how-to-use-ftp-to-upload-files-to-wordpress-for-beginners/]{.underline}](https://www.wpbeginner.com/beginners-guide/how-to-use-ftp-to-upload-files-to-wordpress-for-beginners/)

3.  Steps to upload a plugin to a WordPress website

    a.  Connect to the WordPress using FTP (above)

    b.  Navigate to WordPress plugins folder (​/wp-content/plugins​)

    c.  Create a new folder for the plugin

    d.  Create the main PHP file within the folder.

    e.  Open the PHP file and add the basic plugin information:

![](media/image1.jpeg){width="5.1875in" height="1.6354166666666667in"}

4.  Hooks - Actions and Filters

    a.  Hooks are provided by WordPress to allow your plugin to modify
        > the default actions of WordPress. Hooks simplify the
        > development process by modifying already developed WordPress
        > code rather than starting from scratch. In general, Hooks call
        > functions into WordPress at specific times and can be divided
        > into two categories:

        i.  Actions - Adds a piece of code to the WordPress system that
            > is triggered and run at specific times.

        ii. Filters - serve a similar function to action hooks, however
            > it is intended that filters receive a value and return a
            > modified version of that value. For example, a filter
            > could be used to capitalize the first letter of a title
            > before posting it.

    b.  The most basic steps to add actions or filters to a WordPress:

        i.  Create a PHP function that should execute when a specific
            > WordPress event occurs, in your plugin file.

        ii. Hook this function to the event by using the
            > ​[add_action()](https://codex.wordpress.org/Function_Reference/add_action)​or
            > ​add_filter() function.

        iii. Put your PHP function in a plugin file, and activate it.

    c.  [[Plugin
        > API]{.underline}](https://codex.wordpress.org/Plugin_API)​-
        > contains more relevant information on how to create an action
        > or filter and how to hook it to wordpress

    d.  Further resources:

        i.  [[Action
            > Reference]{.underline}](https://codex.wordpress.org/Plugin_API/Action_Reference)​-
            > List of WordPress's action hooks

        ii. [[Filter
            > Reference]{.underline}](https://codex.wordpress.org/Plugin_API/Filter_Reference)​-
            > List of WordPress's filter hooks

```{=html}
<!-- -->
```
5.  Pre Existing Plugins to look into:

    a.  [[WP-o-Matic]{.underline}](https://github.com/themeskult/wp-o-matic)

        i.  [What it is]{.underline}​: Plugin that automatically creates
            > posts from the RSS/Atom feeds you choose.

        ii. Pros:

            1.  Free to download from Github

            2.  Extremely powerful and flexible

            3.  Automatically updates when the source it pulls from is
                > updated

        iii. Cons/Concerns:

             1.  Complicated and will require training and research to
                 > understand its capabilities

             2.  Requires SimplePie software - not entirely sure what
                 > that is

             3.  Requires understanding of what an RSS/Atom feed is

             4.  Not sure if it can be customized to add content to a
                 > post or if it is only possible to create a new post

             5.  Not sure if it can be customized to filter content
                 > based on tags

        iv. [[More
            > information]{.underline}](https://wparena.com/how-to-pull-content-from-other-websites-automatically/)

    b.  [[WP Web
        > Scraper]{.underline}](https://wordpress.org/plugins/wp-scraper/)

        i.  [What it is:]{.underline} ​Uses CURL and phpQuery to grab
            > and manipulate data from any public website.

        ii. Pros:

            1.  Free to download from the WordPress repository

            2.  Allows content to be uploaded to a specific post.

            3.  Uses JquerySelectors allows you to select which elements
                > you want from the external website. (would allow us to
                > filter content by tags)

        iii. Cons/Concerns:

             1.  Complicated and requires understanding of CSS Selectors

        ```{=html}
        <!-- -->
        ```
        2.  New scraping code must be written for each post created. It
            > is unclear if the plugin could be customized to
            > automatically query and upload content for each new post.

> c\. [[Remote Content
> Shortcode]{.underline}](https://wordpress.org/plugins/remote-content-shortcode/)

i.  [What it is:]{.underline} ​Plugin that allows you to use shortcode
    > to upload remotely hosted content into posts or pages of the
    > WordPress.

ii. Pros:

    1.  Seems to be a simplified, streamlined version of WP Web Scraping

    2.  Free to download from the WordPress repository

    3.  Allows content to be uploaded to a specific post.

    4.  Uses JquerySelectors allows you to select which elements you
        > want from the external website. (would allow us to filter
        > content by tags)

    5.  Has the option to add or remove content from the imported data.

iii. Cons/Concerns:

     1.  Requires an understanding of HTML and CSS Selectors.

     2.  New scraping code must be written for each post created. It is
         > unclear if the plugin could be customized to automatically
         > query and upload content for each new post.

     3.  Less established and not as widely used as WP Web Scraping
