task :default => :build

desc 'Build html files'
task :build => Rake::FileList['**/*.erb'].ext('.html')

rule '.html' => '.erb' do |t|
  sh "erb -T - #{t.source} > #{t.name}"
end
