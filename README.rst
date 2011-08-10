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
#. edit 'resume.html' as you see fit.  Main things:
    #. add ``.. class:: pagebreak`` before sections that 
       need a pdf page break
    #. add/remove extra classes if you need more styles
#. add/remove styles in style.css as you like 
#. On OSX, I use the ``makeit`` script.  Look at it if you
   want to see the actual commands.  They should be installed
   by default.


Known Problems
----------------

#.  Webkit does poorly with the ``page`` and other 
    'css -> print' media formatting directives.  
#.  Automating the ``makeit`` bits is a little thin/hard/impossible. 

See further discussion:  http://writeonly.wordpress.com/



