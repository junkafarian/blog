:Publish Date: 2010-03-26 13:0

Using Sphinx as a CMS
=====================

After having some success using `Sphinx <http://sphinx.pocoo.org/>`_ to document
current projects and having a stab at `some documentation <http://github.com/junkafarian/karldocs>`_
for the `KARL <http://karlproject.org>`_ project, I've decided that Sphinx makes
for a fairly decent CMS when coupled with version control. 

The advantages of this approach (or at least the things I appreciate about this
method) are:

#. ``reStructuredText``: The ability to create a new page with such an emphasis
   on content using whichever text editor you like has a lot going for it. There
   is no clicking around an online CMS to create new pages, and I personally
   much prefer editing text in a `Text Editor <http://aquamacs.org>`_ than
   through a WYSIWYG in a web form.

#. ``file-system based``: Having the site structure and text files all
   accessible through you're local file browser makes a lot of sense. It's
   searchable (as any text file would be) and you don't have to worry about
   forgetting the URL to one of the pages which isn't linked up to the rest of
   the site.

#. ``static output``: When Sphinx has built the source into HTML, there is no
   need for additional processing when serving the content. This means you can
   stick the HTML files straight behind Apache wih no need to set up an
   application server.

#. ``versioning``: One of the major problems I find with Content Management
   Systems is versioning (whether it is making them or using them). Either it
   isn't implemented or you have to use whatever custom interface is provided.
   Some of these interfaces work quite well, however, they usually only track
   changes on a single file / page. That is where having a tool made for the job
   comes in handy.

#. ``previewing and staging``: A lot of CMS solutions have the ability to
   preview content before publishing it to world+dog. The way I will preview
   this post (when finished) is to::
   
        $ make html
        (view in browser)
        (adjust if necessary)
        $ git commit ...
        $ git push
   
   And then update the live server. I know this methodology is very orientated
   to developers used to dealing with this sort of process on a daily basis,
   however, I am one of those people and I find it quite sensible.

#. ``search``: Sphinx compiles some javascript at build time to allow the source
   files to be searchable. This would be the main reason (for me) to use a
   dynamic element server-side, however, I am glad that I don't have to!

#. ``RSS / Syndication``: Another element of blog functionality that makes a
   lot of sense to process server-side. By plugging into the Sphinx extension
   framework, it is fairly easy to generate the xml required at build time.


The above does not in any way suggest that I am going to start promoting the
idea of using Sphinx to clients who don't understand the difference between a
web browser and an operating system. Nevertheless, I think it is a useful tool
to have in the web development arsenal.
