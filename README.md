# latex-journal
Latex journal template

For a long time, i've been writing my personal journal. Here's LaTeXified way of doing it:

```
mkdir dear_diary && cd dear_diary
mkdir output
git init
```

bash script "edit.sh":

```
theMonth=$(LC_ALL=en_US.utf8 date +%b)
theYear=$(LC_ALL=en_US.utf8 date +%Y)
theDay=$(LC_ALL=en_US.utf8 date +%d)
mkdir -p $theYear/$theMonth
vim $theYear/$theMonth/$theDay.tex 
git add ./*
git commit -a -m "$theDay.$theMonth.$theYear"
pdflatex -synctex=1 -interaction=nonstopmode -output-directory=output main.tex > /dev/null
```

main.tex:

**The \usepackage code in my blog is broken markdown. Check out main.tex in the repo.**

Make your log entries like:

```
\mytitle{My daily log entry}
Dear diary,\\
... .... ...
```

For original looping template, special thanks to Tom Bombadil @ StackExchange - https://tex.stackexchange.com/a/68528

Microtype package suggestion and FontAwesome icons commands from my friend Deni b4d @ GitHub - https://github.com/b4d/latex-journal/blob/master/journal.tex
