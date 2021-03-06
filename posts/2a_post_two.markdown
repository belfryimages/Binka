#Binka

A semi-static PHP-based blog engine, with posts rendered from static Markdown files. No underlying database, no administrative console, built-in short URLs, comments outsourced to Disqus, each post is a physical file that works in a version control system.

It isn't ready yet. <strike>I haven't even implemented Markdown support yet.</strike> ;-) I only started it yesterday. Take it easy.

Binka is created and maintained by [Ben Scott/Belfry Images][5].


##Installation

1. fork the project from [Github][1]
2. play with the configuration in `/app/controllers/binka.php`
3. set up your own layout in `/app/views/layouts/default.php`
4. tweak the rest of the views to get the markup you want
5. add some posts to `/posts`
6. copy everything to the live server


##Usage
###Posting a new blog entry

A blog entry in Binka is a Markdown-formatted plain text file saved to the /posts folder. Files should be named `{shortlink}_{permalink}.md`.

- The `{shortlink}` is used for the short URL, but is most importantly used to order the posts. It is an alphanumeric code that should increase for each post. I would suggest starting at '1' up to '9', then 'a' then 'A' up to 'z' then 'z', then '10', and up, so you'll get shortlink codes like `13f7R`.
- The `{permalink}` is the extended link to the post. For example, the post titled 'My Example Post' could have a permalink of `my_example_post`.

Joined together, we get filenames like `13f7R_my_example_post.md`. That post could then be viewed via the following URLs:

- http://example.com/post/my_example_post
- http://example.com/p/my_example_post
- http://example.com/post/13f7R
- http://example.com/p/13f7R

The `/p` path is an alias for `/post`.

The post file is created locally, in a local working copy of the site. To post online, the file is just copied over. The post is available immediately and the landing page and RSS feeds just show the latest 10 (by default) posts ordered by the shortlink.


##Contributing
Contributions are welcome, in any form including code contributions, bug reports, feature suggestions, documentation, testing, and general feedback. The current version can be forked from its [Github repository][1]. I'm using [PivotalTracker][2] for story tracking, and issues can be submitted on the [Github page][4].


##License
###Binka License
I haven't even bothered with Creative Commons on this at the moment as it really is basic. Therefore the current branch of development is Public Domain. This may change in the future. It is likely that a future version will use the Creative Commons Attribution license.

###Third party libraries and components
- The [Slab MVC framework][3] uses the CC A-SA license
- [Markdown Extra][6] Copyright (C) Michel Fortin, based on [Markdown][7] Copyright (C) John Gruber




[1]: https://github.com/belfryimages/Binka
[2]: https://www.pivotaltracker.com/projects/150295
[3]: https://github.com/belfryimages/Slab
[4]: https://github.com/belfryimages/Binka/issues
[5]: http://blog.belfryimages.com.au
[6]: http://michelf.com/projects/php-markdown/
[7]: http://daringfireball.net/projects/markdown/