+++
title = 'LaTeX Printable Book Template'
date = 2025-02-13
+++

Just felt like sharing this since I personally don't have much use for it, but that doesn't mean someone else won't.

Basically I made a LaTeX template for writing books that you can just print out and staple together. It uses landscape oriented paper with a two column layout for the pages.

The only strange thing about it is figuring out the pages, since it will work a bit weird once the book is actually assembled. For example, Page 1 of the book and the last page of the book will be on the same sheet of paper. And then Page 2 and the second to last page, and so on. So you do have to plan things out a bit before printing. 

<img src="/latex_screenshot.png" alt="Meow from Tsukikage Ran standing next to a man on the beach." style="width:100%;">

You can see what I'm talking about with the file names in the image above.

So what I'd personally recommend doing is writing what you want until you hit the end of one column, and then instead of moving into the other column, just create a new file, copy all the same code over, and continue writing the same way. Repeat that until you have everything written that you want, so you'll know how many pages you actually need, and then go back and move everything around into their proper columns so that everything appears in the correct order when it's actually printed out.

I used [Overleaf](https://www.overleaf.com) to do this, but I guess you can use whatever you want because it's a free world. I've just used that website for other things in the past.

Anyways, here's the actual code. I highly doubt it's perfect, you'll probably have to mess around with it some.

###### Book Cover:
```latex
    \documentclass{book}
    \usepackage{graphicx} % Required for inserting images
    \usepackage{lscape}
    \usepackage{multicol}
    \usepackage{blindtext}
    \usepackage{fancyhdr}

    \usepackage[sfdefault]{atkinson}
    \usepackage[T1]{fontenc}

    \usepackage[letterpaper, landscape, margin=0.75in]{geometry}

    \pagenumbering{gobble}

    \setlength{\columnseprule}{1px}
    \setlength{\columnsep}{1.5in}

    \title{Book Title}
    \author{Book Author}
    \date{}

    \begin{document}

    \begin{multicols*}{2}

    \begin{center}
    \vspace*{\fill}
    Back Cover
    \vspace*{\fill}

    \end{center}

    \columnbreak

    \maketitle

    \end{multicols*}

    \end{document}
```

###### Book Page:
```latex
    \documentclass{book}
    \usepackage{graphicx} % Required for inserting images
    \usepackage{lscape}
    \usepackage{multicol}
    \usepackage{blindtext}
    \usepackage{fancyhdr}

    \usepackage{setspace}

    \usepackage{indentfirst}

    \usepackage[sfdefault]{atkinson}
    \usepackage[T1]{fontenc}

    \usepackage[letterpaper, landscape, margin=0.75in]{geometry}

    \pagenumbering{gobble}

    \setlength{\columnseprule}{1px}
    \setlength{\columnsep}{1.5in}

    \renewcommand{\headrulewidth}{0in}

    \fancypagestyle{plain}{%
        \fancyhead{}
        \fancyfoot{}
        \fancyfoot[L]{X}
        \fancyfoot[R]{X}
    }

    \pagestyle{fancy}
    \fancyhead{}
    \fancyfoot[L]{X}
    \fancyfoot[R]{X}

    \begin{document}
    \begin{multicols*}{2}
    \begin{spacing}{1.5}
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

    \blindtext

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \newcolumn
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

    \blindtext

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \end{spacing}
    \end{multicols*}
    \end{document}
```

That's all I have for now, I hope you have fun with this!