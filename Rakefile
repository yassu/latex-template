require 'fileutils'

BASE_FILENAME = 'base_filename_of_tex'
AUTHOR = 'author_name'

LATEX = 'latex'
DVIP = 'dvipdfm'
VIEW = 'evince'

def get_last_tag()
  return `git tag`.split("\n")[-1]
end

def exec_commands(commands)
  for command in commands
    print("#{command}\n")
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
    FileUtils.cp("#{BASE_FILENAME}.tex", "#{AUTHOR}-#{BASE_FILENAME}-#{ver}.tex")
    FileUtils.cp("#{BASE_FILENAME}.pdf", "#{AUTHOR}-#{BASE_FILENAME}-#{ver}.pdf")
  end
end

desc "delete all files for referee"
task :clean_pub do
  FileUtils.rm(Dir.glob('*').select{|s| s.start_with?(AUTHOR)})
end

desc "clean all files made from tex file and for referee"
task :clean do
  FileUtils.rm(Dir.glob('*').select{|s| s.start_with?(AUTHOR)})
  FileUtils.rm(Dir.glob('*').select{|s| \
    s.end_with?('.aux') \
    or s.end_with?('.log') \
    or s.end_with?('.dvi') \
    or s.end_with?('.pdf')})
end
