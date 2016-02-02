latex-template
================

This is a template for my project by using latex (thesis, report or presentation).

Note that `SConStruct` is a file for building images in this project.
Please don't use this file.

Contents
----------

* What are files in this project?
* Basic Customization
* Functions in `yassu.sty`
* Tasks in Rakefile
* LICENSE

What are files in this project?
---------------------------------

* templates directory: You can start tex project by moving `templates/{type}.tex` to `{type}.tex`.
  - simple.tex: template for starting "simple" tex project.
  - slides.tex: template for starting tex project by using slides.
* .gitignore: the some file for ignore files if you use git
* Rakefile: task file by using rake command.
* yassu.sty: sty file for some pretty settings of latex
* .local.vimrc: setting of vim for this latex-project. This file is for
    [thinca/vim-localrc](https://github.com/thinca/vim-localrc).

Basic Customization
---------------------

I recommend that you setting following:

* change `AUTHOR` and `BASEFILENAME` variable in Rakefile.
  For example, if you use `square.tex` in main tex file of this tex project and
  author's name is guide, let

  ```
  BASEFILENAME = 'square'
  AUTHOR = 'guide'
  ```

  `AUTHOR` variable is only used for publish tasks.
  So, if you use tex project for yourself, you can ignore `AUTHOR` variable.

Functions in `yassu.sty`
--------------------------

`yassu.sty` includes some packages and pretty definitions (for me).

packages:
  * amsmath
  * amssymb
  * enumerate
  * ascmac

In text mode, you will be able to use following commands:

<table border>
<tr>
  <td> \propname </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/prop.png" alt="prop"> </td>
</tr>
</table>

And you will be able to use following environments(without Theorem Environments):

<table border>
<tr>
  <td> teacher_talk </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/teacher_talk.png" alt="teacher_talk"> </td>
</tr>
</table>

In math mode, you will be able to use or re-definition following commands:

<table border>
<tr>
  <td> \then </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/then.png" alt="then"> </td>
</tr>
<tr>
  <td> \st </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/st.png" alt="s.t."> </td>
</tr>
<tr>
  <td> \zero </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/zero.png" alt="zero"> </td>
</tr>
<tr>
  <td> \norm </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/norm.png" alt="norm"> </td>
</tr>
<tr>
  <td> \del </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/del.png" alt="del"> </td>
</tr>
<tr>
  <td> \set </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/set.png" alt="set"> </td>
</tr>
<tr>
  <td> \NN </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/NN.png" alt="NN"> </td>
</tr>
<tr>
  <td> \ZZ </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/ZZ.png" alt="ZZ"> </td>
</tr>
<tr>
  <td> \QQ </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/QQ.png" alt="QQ"> </td>
</tr>
<tr>
  <td> \RR </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/RR.png" alt="RR"> </td>
</tr>
<tr>
  <td> \CC </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/CC.png" alt="CC"> </td>
</tr>
<tr>
  <td> \corank </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/corank.png" alt="corank"> </td>
</tr>
<tr>
  <td> \ord </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/ord.png" alt="ord"> </td>
</tr>
<tr>
  <td> \Re </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Re.png" alt="Re"> </td>
</tr>
<tr>
  <td> \Im </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Im.png" alt="Im"> </td>
</tr>
<tr>
  <td> \epsilon </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/epsilon.png" alt="epsilon"> </td>
</tr>
<tr>
  <td> \phi </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/phi.png" alt="phi"> </td>
</tr>
</table>

You will be able to use following theorem environments:

<table border>
<tr>
  <td> thm </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/thm.png" alt="thm"> </td>
</tr>
<tr>
  <td> prop </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/prop.png" alt="prop"> </td>
</tr>
<tr>
  <td> Cor</td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Cor.png" alt="Cor"> </td>
</tr>
<tr>
  <td> Lem </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Lem.png" alt="Lem.png"> </td>
</tr>
<tr>
  <td> Example </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Example.png" alt="Example"> </td>
</tr>
<tr>
  <td> Sym </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Sym.png" alt="Sym"> </td>
</tr>
<tr>
  <td> Def </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Def.png" alt="Def.png"> </td>
</tr>
<tr>
  <td> conj</td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/conj.png" alt="conj.png"> </td>
</tr>
<tr>
  <td> Fact </td>
  <td> <img src="https://raw.githubusercontent.com/yassu/latex-template/master/imgs/Fact.png" alt="Fact"> </td>
</tr>
</table>

Tasks in Rakefile
-------------------

Tasks are following:
  * `clean:` clean all files made from tex file and for referee
  * `clean_pub:` delete all files for referee
  * `compile:` Only compile with latex command
  * `create:` compile and make pdf file from tex file
  * `default:` default task is view: make pdf file and view pdf file
  * `publish:` make tex and pdf files for referee. (format: AUTOR-FILENAME-VER.ext).  For this task, we use `AUTHOR` variable in Rakefile.
  * `view:` make pdf from tex file and view pdf

LICENSE
---------

Copyright 2015 yassu

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
