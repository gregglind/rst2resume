===========================================================
Building Better Resumes Using Python (and Good Design!)
===========================================================

Recently, people have been asking me how I created `my resume <https://github.com/gregglind/rst2resume/raw/master/example/resume.html.pdf>`_.  You already read about my princicples of resume design in `Part 1 <http://writeonly.wordpress.com/2011/08/10/12-simple-ideas-for-better-resumes/>`_, so let's get on to building it!

For the actual document construction, you have lots of choices:

* InDesign:  Proprietary, no 'scripting', anything is possible
* Google Docs:  Look great! For example, look at:  `this resume <https://github.com/gregglind/rst2resume/raw/master/blogs/cathy.resume.png>`_, (made using "Create New>From Template", then searching for Resume).  
* LaTeX:  Painful on OSX, very good rendering engine, can be fussy.
* Python Restructured Text (Docutils).


What Rocks About Restructured Text
----------------------------------------

*   Simple markup syntax.
*   Full power of css.
*   Source control (i.e., they are plain text, and can be used to construct 
    documents).
*   scriptable::

        rst2html.py --link-stylesheet --no-doc-title --stylesheet style.css resume.txt > resume.html

Nits and Known Problems (or Why Not To Use RST)
------------------------------------------------------

*   css isn't perfect, and is hard to get right.
*   No hyphenation / layout (which InDesign and LaTeX get right).
*   Need a 'smaller' pdf (for CodeEval.com, for example)?  Use::
    
        Preview > Save as... > Quart Filter | Reduce File Size

*   Webkit does poorly with the ``page`` and other 
    'css -> print' media formatting directives.  
  
    *   ``position: fixed`` is supposed to print on every page (which 
        can be exploited to make headers), but this doesn't really seem
        to work on either Safari or Chrome.
    *   the ``@page`` directives in http://www.alistapart.com/articles/boom
        don't seem to work in Safari.

*   Automating the ``makeit`` bits is a little thin/hard/impossible.  Maybe
    I just don't understand AppleScript, ``osascript``, and Automator,
    but getting a workflow of 'open it in Safari, print to PDF, Preview
    though Quartz Filter' is beyond me.
*   Chrome issue:  using 'Save as PDF' on OSX from Chrome doesn't link
    images (at all).  Save the following to a file, and the resulting 
    pdf won't link.  This works fine in Safari.

    :: 

        <a href="http://google.com"> 
        <img src="http://pystar.org/_static/pystar_flaming_160_150px.png"> 
        </a>

*   Chrome:  'https' links don't seem to show up in Save as PDF
*   Chrome:  much fussier on borders, made extra (blank) pages.

(Please educate me on any of these, if I have them wrong!)


Introducing ``rst2resume`` - Resumes using Restructured Text (rst)
---------------------------------------------------------------------

#. Install Python, understand how to use the cli.
   On OSX, this is built in.
#. ``git clone git@github.com:gregglind/rst2resume.git``
#. ``pip install docutils``
#. copy files from the example directory, season to taste
#. edit ``resume.html`` as you see fit.  Main things:
    #. add ``.. class:: pagebreak`` before sections that 
       need a pdf page break
    #. add/remove extra classes if you need more styles
#. add/remove styles in style.css as you like 
#. On OSX, I use the ``makeit`` script.  Look at it if you
   want to see the actual commands.  They should be installed
   by default.


More Links:
--------------

#.  Restructured text:

    * http://sphinx.pocoo.org/rest.html
    * http://docutils.sourceforge.net/docs/user/rst/quickref.html
    * http://docutils.sourceforge.net/docs/ref/rst/directives.html

#.  Another perpective, using ``rst2pdf`` directly.
    http://charlie137-2.blogspot.com/2010/02/writing-resume-using-restructuredtext.html
    
#.  http://www.documentsnap.com/how-to-split-pdf-documents-into-single-pages-using-mac-osx/

#.  ``rst2resume`` is located at https://github.com/gregglind/rst2resume/



