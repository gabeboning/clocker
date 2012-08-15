clocker
=======

Git post-commit hook to easily log time in basecamp. At this time, the script can only bill time to a todo item. 


Usage
=====

Python (I'm running 2.7), python's standard libraries, and the [python requests module](http://docs.python-requests.org/en/latest/index.htm) are the only dependencies. 

Setting up the script is pretty easy. 

You'll need your basecamp url, user id, and API key. For each project you intend to log time for, you'll need the todo id that you bill time to.

Drop the post-commit into the git hooks directory for whatever project you intend to use it for. Then set up the git config:

    $ git config --global --add basecamp.url https://yours.basecamphq.com
    $ git config --global --add basecamp.user-id youruserid
    $ git config --global --add basecamp.key yourlongauthenticationtoken

Those are global config used across all repositories you'll be logging time for. In each repository, you'll need to set the todo ID:

    $ git config --add basecamp.todo-id todoid

Once that's all set up, billing time is as easy as putting it in your commit message
  
    $ git commit -m "whooo billing stuff [.5]"

will bill .5 hours. Anything inside the [ ] braces will be posted straight to basecamp as the time amount.



