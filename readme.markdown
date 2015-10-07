latex-template
================

This is a template for my project by using latex (thesis, report or presentation).

Note that `SConStruct` is a file for building images in this project.
Please don't use this file.

What are files in this project?
---------------------------------

* templates directory: You can start tex project by moving `templates/{type}.tex` to `{type}.tex`.
  - simple.tex: template for starting "simple" tex project.
  - slides.tex: template for starting tex project by using slides.
* .gitignore: the some file for ignore files if you use git
* Rakefile: task file by using rake command.
  tasks are following:
  - clean: clean all files made from tex file and for referee
  - clean_pub: delete all files for referee
  - compile: Only compile with latex command
  - create: compile and make pdf file from tex file
  - default: default task is view: make pdf file and view pdf file
  - publish: make tex and pdf files for referee. (format: AUTOR-FILENAME-VER.ext)
             For this task, we use `AUTHOR` variable in Rakefile.
  - view: make pdf from tex file and view pdf
* yassu.sty: sty file for some pretty settings of latex
* .local.vimrc: setting of vim for this latex-project. This file is for
    [thinca/vim-localrc](https://github.com/thinca/vim-localrc).

Basic Customize
-----------------

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
