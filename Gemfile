raise "Ruby versions less than 2.2.2 are unsupported!" if RUBY_VERSION < "2.2.2"

source 'https://rubygems.org'

#
# VMDB specific gems
#

gem "manageiq-gems-pending", ">0", :require => 'manageiq-gems-pending', :git => "https://github.com/ManageIQ/manageiq-gems-pending.git", :branch => "master"
# Modified gems for gems-pending.  Setting sources here since they are git references
gem "handsoap", "~>0.2.5", :require => false, :git => "https://github.com/ManageIQ/handsoap.git", :tag => "v0.2.5-5"

# when using this Gemfile inside a providers Gemfile, the dependency for the provider is already declared
def manageiq_plugin(plugin_name)
  unless dependencies.detect { |d| d.name == plugin_name }
    gem plugin_name, :git => "https://github.com/ManageIQ/#{plugin_name}", :branch => "master"
  end
end

manageiq_plugin "manageiq-automation_engine"
manageiq_plugin "manageiq-content"
manageiq_plugin "manageiq-providers-amazon"
manageiq_plugin "manageiq-providers-ansible_tower"
manageiq_plugin "manageiq-providers-azure"
manageiq_plugin "manageiq-providers-foreman"
manageiq_plugin "manageiq-providers-hawkular"
manageiq_plugin "manageiq-providers-google"
manageiq_plugin "manageiq-providers-kubernetes"
manageiq_plugin "manageiq-providers-lenovo"
manageiq_plugin "manageiq-providers-nuage"
manageiq_plugin "manageiq-providers-scvmm"
manageiq_plugin "manageiq-providers-openshift"
manageiq_plugin "manageiq-providers-openstack"
manageiq_plugin "manageiq-providers-ovirt"
manageiq_plugin "manageiq-providers-vmware"
manageiq_plugin "manageiq-ui-classic"

# Unmodified gems
gem "activerecord-id_regions",        "~>0.2.0"
gem "activerecord-session_store",     "~>1.0.0"
gem "acts_as_tree",                   "~>2.1.0" # acts_as_tree needs to be required so that it loads before ancestry
gem "ancestry",                       "~>2.2.1",       :require => false
gem "ansible_tower_client",           "~>0.12.2",      :require => false
gem "bundler",                        ">=1.11.1",      :require => false
gem "color",                          "~>1.8"
gem "config",                         "~>1.3.0",       :require => false
gem "dalli",                          "~>2.7.4",       :require => false
gem "default_value_for",              "~>3.0.2"
gem "elif",                           "=0.1.0",        :require => false
gem "fast_gettext",                   "~>1.2.0"
gem "gettext_i18n_rails",             "~>1.7.2"
gem "gettext_i18n_rails_js",          "~>1.1.0"
gem "hamlit",                         "~>2.7.0"
gem "hashie",                         "~>3.4.6",       :require => false
gem "htauth",                         "2.0.0",         :require => false
gem "inifile",                        "~>3.0",         :require => false
gem "jbuilder",                       "~>2.5.0" # For the REST API
gem "manageiq-api-client",            "~>0.1.0",       :require => false
gem "manageiq-network_discovery",     "~>0.1.1",       :require => false
gem "manageiq-smartstate",            "~>0.1.1",       :require => false
gem "mime-types",                     "~>2.6.1",       :path => "mime-types-redirector"
gem "more_core_extensions",           "~>3.2"
gem "nakayoshi_fork",                 "~>0.0.3"  # provides a more CoW friendly fork (GC a few times before fork)
gem "net-ldap",                       "~>0.14.0",      :require => false
gem "net-ping",                       "~>1.7.4",       :require => false
gem "net-ssh",                        "=3.2.0",        :require => false
gem "omniauth",                       "~>1.3.1",       :require => false
gem "omniauth-google-oauth2",         "~>0.2.6"
gem "open4",                          "~>1.3.0",       :require => false
gem "openscap",                       "~>0.4.3",       :require => false
gem "ovirt-engine-sdk",               "~>4.1.4",       :require => false # Required by the oVirt provider
gem "ovirt_metrics",                  "~>1.4.1",       :require => false
gem "pg-pglogical",                   "~>1.1.0",       :require => false
gem "puma",                           "~>3.3.0"
gem "query_relation",                 "~>0.1.0",       :require => false
gem "rails",                          "~>5.0.2"
gem "rails-controller-testing",                        :require => false
gem "rails-i18n",                     "~>5.x"
gem "responders",                     "~>2.0"
gem "rest-client",                    "~>2.0.0",       :require => false
gem "ripper_ruby_parser",                              :require => false
gem "ruby-dbus" # For external auth
gem "ruby-progressbar",               "~>1.7.0",       :require => false
gem "rubyzip",                        "~>1.2.1",       :require => false
gem "rufus-scheduler",                "~>3.1.3",       :require => false
gem "rugged",                         "=0.25.0b10",    :require => false
gem "secure_headers",                 "~>3.0.0"
gem "simple-rss",                     "~>1.3.1",       :require => false
gem "snmp",                           "~>1.2.0",       :require => false
gem "sshkey",                         "~>1.8.0",       :require => false
gem "thin",                           "~>1.7.0",       :require => false
gem "vmware_web_service",             "~>0.1.1",       :require => false
gem "websocket-driver",               "~>0.6.3"

# Modified gems (forked on Github)
gem "amazon_ssa_support",                          :require => false, :git => "https://github.com/ManageIQ/amazon_ssa_support.git", :branch => "master" # Temporary dependency to be moved to manageiq-providers-amazon when officially release
gem "ruport",                         "=1.7.0",                       :git => "https://github.com/ManageIQ/ruport.git", :tag => "v1.7.0-3"

# In 1.9.3: Time.parse uses british version dd/mm/yyyy instead of american version mm/dd/yyyy
# american_date fixes this to be compatible with 1.8.7 until all callers can be converted to the 1.9.3 format prior to parsing.
# See miq_expression_spec Date/Time Support examples.
# https://github.com/jeremyevans/ruby-american_date
gem "american_date"

group :ui_dependencies do # Added to Bundler.require in config/application.rb
  # Modified gems (forked on Github)
  gem "font-fabulous",                                                :git => "https://github.com/ManageIQ/font-fabulous.git", :branch => "master" # FIXME: this is just a temporary solution and it'll go to the ui-classic later
  gem "jquery-rjs",                   "=0.1.1",                       :git => "https://github.com/ManageIQ/jquery-rjs.git", :tag => "v0.1.1-1"
end

### Start of gems excluded from the appliances.
# The gems listed below do not need to be packaged until we find it necessary or useful.
# Only add gems here that we do not need on an appliance.
#
unless ENV["APPLIANCE"]
  group :development do
    gem "haml_lint",        "~>0.20.0", :require => false
    gem "rubocop",          "~>0.47.0", :require => false
    gem "scss_lint",        "~>0.48.0", :require => false
  end

  group :test do
    gem "brakeman",         "~>3.3",    :require => false
    gem "capybara",         "~>2.5.0",  :require => false
    gem "coveralls",                    :require => false
    gem "factory_girl",     "~>4.5.0",  :require => false
    gem "sqlite3",                      :require => false
    gem "timecop",          "~>0.7.3",  :require => false
    gem "vcr",              "~>3.0.2",  :require => false
    gem "webmock",          "~>2.3.1",  :require => false
  end

  group :development, :test do
    gem "good_migrations"
    gem "parallel_tests"
    gem "rspec-rails",      "~>3.6.0"
  end
end

#
# Custom Gemfile modifications
#
# To develop a gem locally and override its source to a checked out repo
#   you can use this helper method in Gemfile.dev.rb e.g.
#
# override_gem 'manageiq-ui-classic', :path => File.expand_path("../manageiq-ui-classic", __dir__)
#
def override_gem(name, *args)
  if dependencies.any?
    raise "Trying to override unknown gem #{name}" unless (dependency = dependencies.find { |d| d.name == name })
    dependencies.delete(dependency)

    calling_file = caller_locations.detect { |loc| !loc.path.include?("lib/bundler") }.path
    gem(name, *args).tap do
      warn "** override_gem: #{name}, #{args.inspect}, caller: #{calling_file}" unless ENV["RAILS_ENV"] == "production"
    end
  end
end

# Load developer specific Gemfile
#   Developers can create a file called Gemfile.dev.rb containing any gems for
#   their local development.  This can be any gem under evaluation that other
#   developers may not need or may not easily install, such as rails-dev-boost,
#   any git based gem, and compiled gems like rbtrace or memprof.
dev_gemfile = File.expand_path("Gemfile.dev.rb", __dir__)
if File.exist?(dev_gemfile)
  Bundler::UI::Shell.new.warn "** Gemfile.dev.rb deprecated, please move it to bundler.d/"
  eval_gemfile(dev_gemfile)
end

# Load other additional Gemfiles
Dir.glob(File.join(__dir__, 'bundler.d/*.rb')).each { |f| eval_gemfile(File.expand_path(f, __dir__)) }
