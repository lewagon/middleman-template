# Le Wagon Middleman template

Welcome on this short guide on how to quickstart your next Middleman project with [Le Wagon](https://www.lewagon.com) best practices.

## Getting started

In your terminal, check you have Middleman:

```bash
gem install middleman
# You should have a version >= 4.2.1
```

Then run the following:

```bash
cd ~/code/YOUR_GITHUB_NICKNAME
middleman init YOUR_PROJECT -B -T lewagon/middleman-template
cd YOUR_PROJECT

git init
git add .
git commit -m 'Generated a new middleman project with lewagon/middleman-template'

hub create    # To create a repo on GitHub
git remote -v # Check that the `origin` remote is set.
git push origin master
```

You should be able to run:

```bash
middleman server
```

And go to [localhost:4567](http://localhost:4567)

## If the GitHub pages is not for an user but for an organization
You need to change the default branch to deploy 'gh-pages' -> 'master'
```bash
activate :deploy do |deploy|
  deploy.build_before = true
  deploy.deploy_method = :git
  deploy.branch   = 'master'
end
```
## Deployment

Make sure that your `git status` is clean and run:

```bash
middleman deploy
```

This should build your Middleman project and push it to the `gh-pages` of your GitHub repository. Then go to `YOUR_GITHUB_NICKNAME.github.io/YOUR_PROJECT` to see it live 🚀 !
