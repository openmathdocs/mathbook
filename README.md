OpenMathDocs version of MathBook XML
============

A lightweight XML application for authors of scientific articles, textbooks and monographs.

GPL License.

*Be sure* to checkout the dev branch, master is currently a fiction.

Quickstart instructions at project website:  http://mathbook.pugetsound.edu

============

We have tried to keep this version of MathBook as close to 
its original as possible, but some of our features are 
not appropriate or compatible, so some divergence has/will occur.

# How to get a copy or contribute to this project
Use the following steps if you would like to contribute 
to this project. If you just want a copy of the project, 
you can probably stop after the first step.

### clone the origin of mathbook
    git clone https://github.com/rbeezer/mathbook
    cd mathbook
### check your remote repositories
    git remote -v
    origin    https://github.com/rbeezer/mathbook (fetch)
    origin    https://github.com/rbeezer/mathbook (push)
### add omd remote repo
    git remote add omd https://github.com/openmathdocs/mathbook
### check remotes again
    git remote -v
    omd    https://github.com/openmathdocs/mathbook (fetch)
    omd    https://github.com/openmathdocs/mathbook (push)
    origin    https://github.com/rbeezer/mathbook (fetch)
    origin    https://github.com/rbeezer/mathbook (push)
### check branches
    git branch -a
    * master
      remotes/origin/HEAD -> origin/master
      remotes/origin/dev
      remotes/origin/master
### create a local dev branch that tracks origin/dev
    git checkout -b dev origin/dev
    Branch dev set up to track remote branch dev from origin.
    Switched to a new branch 'dev'
### check branches
    git branch -a -vv
    * dev                   84152a8 [origin/dev] Notation list in HTML
      master                30ce2c1 [origin/master] Merge dev branch to make v0.01
      remotes/origin/HEAD   -> origin/master
      remotes/origin/dev    84152a8 Notation list in HTML
      remotes/origin/master 30ce2c1 Merge dev branch to make v0.01
### fetch branches from OMD
    git fetch omd
    * [new branch]      dev        -> omd/dev
     * [new branch]      feature/quant -> omd/feature/quant
     * [new branch]      master     -> omd/master
### verify branches
    git branch -v -aa
    * dev                       84152a8 [origin/dev] Notation list in HTML
      master                    30ce2c1 [origin/master] Merge dev branch to make v0.01
      remotes/omd/dev           84152a8 Notation list in HTML
      remotes/omd/feature/quant 0861565 added gallon to units in mathbook-html.xsl
      remotes/omd/master        30ce2c1 Merge dev branch to make v0.01
      remotes/origin/HEAD       -> origin/master
      remotes/origin/dev        84152a8 Notation list in HTML
      remotes/origin/master     30ce2c1 Merge dev branch to make v0.01
### create a branch that tracks omd/dev
    git checkout -b omddev omd/dev
    Branch omddev set up to track remote branch dev from omd.
    Switched to a new branch 'omddev'
### and one that tracks omd/master
    git checkout -b omdmaster omd/master
    Branch omdmaster set up to track remote branch master from omd.
    Switched to a new branch 'omdmaster'
### verify branches
    git branch -a -vv
    dev                       84152a8 [origin/dev] Notation list in HTML
      master                    30ce2c1 [origin/master] Merge dev branch to make v0.01
      omddev                    84152a8 [omd/dev] Notation list in HTML
    * omdmaster                 30ce2c1 [omd/master] Merge dev branch to make v0.01
      remotes/omd/dev           84152a8 Notation list in HTML
      remotes/omd/feature/quant 0861565 added gallon to units in mathbook-html.xsl
      remotes/omd/master        30ce2c1 Merge dev branch to make v0.01
      remotes/origin/HEAD       -> origin/master
      remotes/origin/dev        84152a8 Notation list in HTML
# creating a new feature
    git checkout -b feature/<FEATURE NAME> origin/dev
    git fetch
    git pull
    <do work>
    git status
    <check that you've updated/added the files you think you had!>
    <possibly run git diff as a further check>
    git add <new files and edited files>
    git commit -m <MESSAGE GOES HERE>
    git push omd feature/<FEATURE NAME>

and then submit pull request to `omd/dev` and, if appropriate, to `origin/dev`

# running MBX script to update images; sample usage:
    ./script/mbx -vv -c tikz -f svg -d ~/Documents/projects/openmathdocs/mathbook/examples/images examples/sample-article.xml


