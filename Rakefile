require 'erb'

desc 'Build html files'
task :default do
  Dir['*.erb'].each do |input|
    output = input.sub(/\.erb\Z/, '.html')
    File.unlink output if File.exists? output
    File.open(output, 'w') do |f|
      f.write ERB.new(File.read(input), nil, '-').result
      f.chmod 0444
    end
  end
end
