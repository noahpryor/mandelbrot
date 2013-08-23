
task :deploy do
  unless '' == (status = `git status --porcelain`)
    abort "You have unstaged changes. Make sure to commit or stash first.\n\n#{status}"
  end
  system  "s3cmd sync --delete --acl-public build/ s3://mandelbrotgroup.com" +
          " --add-header=Cache-Control:public,max-age=300"
end