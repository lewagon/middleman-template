require 'thor/group'

module Middleman
  class Generator < ::Thor::Group
    include ::Thor::Actions

    source_root File.expand_path(File.dirname(__FILE__))

    def copy_default_files
      directory 'template', '.', exclude_pattern: /\.DS_Store$/
    end

    def bundle_install
      run 'bundle install'
    end

    def download_assets
      run 'curl -L https://github.com/lewagon/stylesheets/archive/master.zip > stylesheets.zip'
      run 'unzip stylesheets.zip -d source && rm stylesheets.zip'
      run 'mv source/rails-stylesheets-master source/stylesheets'
      run 'mv source/stylesheets/application.scss source/stylesheets/application.css.scss'
      run 'rm source/stylesheets/README.md'
      run 'rm source/stylesheets/pages/_home.scss && mv source/home.scss source/stylesheets/pages/_home.scss'
      run 'mv source/about.scss source/stylesheets/pages/_about.scss'
      run 'echo "@import \"about\";" >> source/stylesheets/pages/_index.scss'
    end

    def generate_binstub
      run 'bundle binstubs middleman-cli'
    end
  end
end
