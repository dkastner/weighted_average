require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "weighted_average"
    gem.summary = %Q{Perform weighted averages. Rails 3 only.}
    gem.description = %Q{Perform weighted averages, even across associations. Rails 3 only because it uses ARel.}
    gem.email = "seamus@abshere.net"
    gem.homepage = "http://github.com/seamusabshere/weighted_average"
    gem.authors = ["Seamus Abshere", "Andy Rossmeissl", "Ian Hough", "Matt Kling"]
    gem.add_dependency 'activerecord', '>=3.0.0.beta2'
    gem.add_dependency 'arel', '>=0.3.3'
    gem.add_development_dependency 'cohort_scope', '>=0.0.2'
    gem.add_development_dependency "shoulda", ">= 2.10.3"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "weighted_average #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
