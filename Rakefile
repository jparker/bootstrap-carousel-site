html_files = Rake::FileList['**/*.erb'].ext('.html')

task :default => :build

desc 'Build html files (default task)'
task :build => html_files

desc 'Remove html files'
task :clean do
  rm html_files, force: true
end

desc 'Rebuild html files'
task :rebuild => [:clean, :build]

rule '.html' => '.erb' do |t|
  sh "erb -T - #{t.source} > #{t.name}"
end
