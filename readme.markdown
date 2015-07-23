latex-template
================

This is template for my project by using latex (thesis, report or prezentation).

What are files in this project?
---------------------------------

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

LICENSE
---------

Copyright 2015 yassu

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
