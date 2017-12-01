require 'bundler/gem_tasks'
require 'rake/testtask'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

# desc 'Run tests'
# task :test do
#   sh 'ruby ./test/todolist_project_test.rb'
# end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List all files'
task :files do
  Find.find('./') do |path|
    next if path.match(/\.\/\./)
    puts path if File.file?(path)
  end
end

# LS solution:
desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with .names
    puts name if File.file?(name)
  end
end
