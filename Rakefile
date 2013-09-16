require 'rake/clean'

html_files = Rake::FileList['**/*.erb'].ext('.html')
CLOBBER.include html_files

task :default => :build

desc 'Build html files (default task)'
task :build => html_files

desc 'Rebuild html files'
task :rebuild => [:clobber, :build]

rule '.html' => '.erb' do |t|
  sh "erb -T - #{t.source} > #{t.name}"
end
