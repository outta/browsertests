task :default => :cucumber

# cucumber needs this
require "cucumber/rake/task"
Cucumber::Rake::Task.new(:cucumber, "Run all cucumber features.")

require 'rspec/core/rake_task'

require 'ci/reporter/rake/rspec' # ci_reporter needs this
RSpec::Core::RakeTask.new(:bogus => ["ci:setup:rspec"]) do |spec|
  spec.pattern = 'spec/bogus_page_spec.rb'
end

RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.ruby_opts = "-I lib:spec"
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rspec_opts = ["-r rspec-extra-formatters", "-f JUnitFormatter", '-o results.xml']
end

RSpec::Core::RakeTask.new(:login_spec) do |spec|
  spec.ruby_opts = "-I lib:spec"
  spec.pattern = 'spec/login/*_spec.rb'
end

RSpec::Core::RakeTask.new(:new_page_spec) do |spec|
  spec.ruby_opts = "-I lib:spec"
  spec.pattern = 'spec/new_page/*_spec.rb'
end

RSpec::Core::RakeTask.new(:proofread_page_spec) do |spec|
  spec.ruby_opts = "-I lib:spec"
  spec.pattern = 'spec/proofread_page/*_spec.rb'
end

RSpec::Core::RakeTask.new(:upload_wizard_spec) do |spec|
  spec.ruby_opts = "-I lib:spec"
  spec.pattern = 'spec/upload_wizard/*_spec.rb'
end
