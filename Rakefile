require 'fileutils'

BASE_FILENAME = 'basefilename'
AUTHOR = 'author'

LATEX = 'platex'
DVIP = 'dvipdfm'
VIEW = 'evince'

def get_last_tag()
  tags = `git tag`.split("\n")[-1]
  if tags.nil?
    return ''
  else
    return tags[-1]
  end
end

def exec_commands(commands)
  for command in commands
    if system(command) == false
      return
    end
  end
  return true
end

def view()
  exec_commands(["#{LATEX} #{BASE_FILENAME}.tex",
                 "#{DVIP}  #{BASE_FILENAME}.dvi",
                 "#{VIEW}  #{BASE_FILENAME}.pdf"])
end

desc "default task is view: make pdf file and view pdf file"
task :default do
  view()
end

desc "Only compile with latex command"
task :compile do
  exec_commands(["#{LATEX} #{BASE_FILENAME}.tex"])
end

desc "compile and make pdf file from tex file"
task :create do
  exec_commands(["#{LATEX} #{BASE_FILENAME}.tex",
                 "#{DVIP}  #{BASE_FILENAME}.dvi"])
end

desc "make pdf from tex file and view pdf"
task :view do
  view()
end

desc "make tex and pdf files for referee (format: AUTOR-FILENAME-VER.ext)"
task :publish do
  ver = get_last_tag()
  status = exec_commands([
    "#{LATEX} #{BASE_FILENAME}.tex",
    "#{DVIP}  #{BASE_FILENAME}.dvi"])
  if status == true
    pub_filename = "#{AUTHOR}-#{BASE_FILENAME}"
    if ver != ''
      pub_filename += "-#{ver}"
    end
    FileUtils.cp("#{BASE_FILENAME}.tex", "#{pub_filename}.tex")
    FileUtils.cp("#{BASE_FILENAME}.pdf", "#{pub_filename}.pdf")
  end
end

desc "delete all files for referee"
task :clean_pub do
  FileUtils.rm(Dir.glob('*').select{|s| s.start_with?(AUTHOR)})
end

EXTENSIONS_ABOUT_TEX = ['aux', 'log', 'dvi', 'pdf', 'fdb_latexmk', 'fls',
                        'nav', 'out', 'snm', 'toc']

def is_latex_file(filename)
  for ext in EXTENSIONS_ABOUT_TEX
    if filename.end_with?('.' + ext)
      return true
    end
  end
  return false
end

desc "clean all files made from tex file and for referee"
task :clean do
  FileUtils.rm(Dir.glob('*').select{|fname| fname.start_with?(AUTHOR)})
  FileUtils.rm(Dir.glob('*').select{|fname| is_latex_file(fname)})
end

