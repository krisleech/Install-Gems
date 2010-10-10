
desc 'Install a list of gems from a text file generated by "gem list"'
task :reinstall_gems do
  raise 'Supply filename for list of gems, file=/path/to/gems.txt' unless ENV['file']
  File.open(ENV['file']).each do | line |
    name = line.split(' ')[0]
    versions = line.split('(')[1].chomp.delete(' )').split(',')
    
    versions.each do | version |
      cmd = "sudo gem install #{name} --version=#{version}  --ignore-dependencies"
      puts cmd
      system cmd
    end    
  end
end