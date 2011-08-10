===========================================================
Building Better Resumes Using Python (and some Design)
===========================================================


You already read about the princicples <...>.  So how do you build it?

Recently, people have been asking me how I created `my resume 
<http://www.python.org/>`_ .  

Stay On Message
------------------------

Like any document, a resume should keep it's purpose in mind.  
Resumes are your advertisement for yourself!  The form 

One thing I have been learning from being around the startup/entrepreneur world


With a few small steps, you can make your resume look *designed*.

For the actual document construction, you have lots of choices:

* InDesign
* Google Docs
* LaTeX
* Python Restructed Text (Docutils)



One solution is use Google Docs, which can produce documents like this:

Instead I use Python


Github for project  -- rst2resume

To follow along at home, open the https://github.com/gregglind/rst2resume/raw/master/example/resume.html.pdf

10 Simple Ideas For Better Resumes
----------------------------------------------

#. **Big margins** give air and room for the design to breathe.
#. **Increasing line height** gives some vertical rhythm to the page
#. **Nice fonts** look good.  Helvetica is classic, and free on OSX, but 
   choose your own and season to taste.  No more than two, and keep the number
   of color/size/font-face combinations small.
#. **Alignments matter**
#. **Stay on message**.  Remember your goal:  to advertise yourself.  Any text
   that doesn't support that message
#. **Write like it's a press release.**  P
#. **Page flow
#. **No bullets**
#. **use color for accent**.  Bold and other typographic choices can 
   sometimes be replaced by color changes.  Remember that we are visual people.
#. **Remove "references available on request".**  Of course they are!  


Read more about how I created this resume (and the trade-offs I made) at



FYI for your blog post: I got the template for my resume just from open templates available via Google Docs (Create New>From Template and searched for Resume)


``rst2resume`` is located at https://github.com/gregglind/rst2resume/


=====================================================
rst2resume - Resumes using Restructured Text (rst)
=====================================================


Use:
-----

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

Nits and Known Problems (or Why Not To Use RST)
------------------------------------------------------

* css isn't perfect

* Need a 'smaller' pdf (for CodeEval.com, for example)?  Use::

    Preview > Save as... > Quart Filter | Reduce File Size





#.  Webkit does poorly with the ``page`` and other 
    'css -> print' media formatting directives.  

    *   ``position: fixed`` is supposed to print on every page (which 
        can be exploited to make headers), but this doesn't really seem
        to work on either Safari or Chrome.
    *   the ``@page`` directives in http://www.alistapart.com/articles/boom
        don't seem to work in Safari.

#.  Automating the ``makeit`` bits is a little thin/hard/impossible.  Maybe
    I just don't understand AppleScript, ``osascript``, and Automator,
    but getting a workflow of 'open it in Safari, print to PDF, Preview
    though Quartz Filter' is beyond me.

#.  Chrome issue:  using 'Save as PDF' on OSX from Chrome doesn't link
    images (at all).  Save the following to a file, and the resulting 
    pdf won't link.  This works fine in Safari.

    :: 

        <a href="http://google.com"> 
        <img src="http://pystar.org/_static/pystar_flaming_160_150px.png"> 
        </a>

#.  Chrome:  'https' links don't seem to show up in Save as PDF

#.  Chrome:  much fussier on borders, made extra (blank) pages.

(Please educate me on any of these, if I have them wrong!)

More Links:
--------------

#.  Restructured text:

    * http://sphinx.pocoo.org/rest.html
    * http://docutils.sourceforge.net/docs/user/rst/quickref.html
    * http://docutils.sourceforge.net/docs/ref/rst/directives.html

#.  Another perpective, using ``rst2pdf`` directly.
    http://charlie137-2.blogspot.com/2010/02/writing-resume-using-restructuredtext.html
    
#.  http://www.documentsnap.com/how-to-split-pdf-documents-into-single-pages-using-mac-osx/






So, what sucks here:

# bugs in chrome and safari 
    - hard to do headers and footers.
    - image links don't work
# no nice breaking / hyphenation
# css is fussy





To use:

pagebreak

RST bits...

.. image
.. class







https://github.com/gregglind/rst2resume/raw/master/example/resume.html.pdf
