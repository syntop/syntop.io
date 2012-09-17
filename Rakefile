task :deploy do
  head = open('.git/refs/heads/master').read().strip()
  
  puts "Create static website ..."
  sh "bonsai --repot"
  
  puts "Commit changes to GitHub pages repository ..."
  sh "cd site && cp -R ../output/* . && git add . && git commit -am 'Update site based on #{head}'"
  
  puts "Pushing to GitHub ..."
  sh "cd site && git push origin gh-pages"
end