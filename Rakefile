require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "bio-gem"
  gem.homepage = "http://github.com/helios/bioruby-gem"
  gem.license = "MIT"
  gem.summary = %Q{Biogem is a software generator for Ruby in bioinformatics}
  gem.description = %Q{Biogem is a software generator for those bioinformaticans who want to start coding an application or a library for using/extending BioRuby core library and sharing it through rubygems.org .
  The basic idea is to simplify and promote a modular approach to bioinformatics software development}
  gem.email = "ilpuccio.febo@gmail.com"
  gem.authors = ["Raoul J.P. Bonnal", "Pjotr Prins"]
  # Include your dependencies below. Runtime dependencies are required when using your gem,
  # and development dependencies are only needed for development (ie running rake tasks, tests, etc)
  #gem.version='0.0.1'
  gem.rdoc_options << '--main' << 'README' << '--line-numbers'
  gem.required_ruby_version = ">= 1.9.3"
  gem.extra_rdoc_files = ['LICENSE.txt', 'README.rdoc','Tutorial.rdoc']
end



# # Ricordati ti aggiungere README e Tutorial
# #  spec.extra_rdoc_files = ['README', 'doc/user-guide.txt']
# 
# def extra_rdoc_files
#   @extra_rdoc_files ||= []
# end
# 
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  # test.pattern = 'test/**/test_*.rb' breaks in Ruby 1.9.3
  test.test_files = Dir.glob("test/**/test_*.rb")
  test.verbose = true
end

# No proper rcov support in 1.9
#
# require 'rcov/rcovtask'
# Rcov::RcovTask.new do |test|
#   test.libs << 'test'
#   test.pattern = 'test/**/test_*.rb'
#   test.verbose = true
# end

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bio-gem #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('Tutorial.rdoc')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
