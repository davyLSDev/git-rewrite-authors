Rewrite author/committer history of a git repository
====================================================

Have you ever accidentally committed to a git repository with a broken
user config?  No?  But your co-workers have?

So, you're stuck with commits like this:

    Author: root <root@localhost>

        Hotfix on the production server.  This was urgent!

Nasty.  Or:

    Author: John Doe <john@localhost>

        Fixed bug #1.  Committed on my laptop.

Would it be nice to rewrite history?  And take care of committers, as
well as of authors?  Without all the hassle?  Now, you can!

Usage:

    $ git-rewrite-authors -w "John Doe <john@localhost>" "John Doe <dearjohn@example.com>"
    
    $ git-rewrite-authors -f author_change_list.txt
    
    Where: authors_change_list.txt (or whatever you want to call it) file
    contains the list of author / committer changes that need to be changed.
    Each line in this file would look like this:
    
    Unknown AuthorName <unknown@localhost.com> John Doe <john_doe@realmail.com>
    
    (Unknown AuthorName is the author that needs to be changed,
    <unknown@localhost.com> is the author's email that needs to be changed,
    John Doe is the author's name to rewrite,
    <john_doe@realmail.com> is the author's real email address to rewrite.

You're not sure which authors/committers are hidden in your repository?
What about:

    $ git-rewrite-authors -l

Tags are rewritten automagically, too!

Enjoy!
