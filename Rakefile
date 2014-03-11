desc "Run server"
task :default => :use_keys do
  sh "ruby signin.rb"
end

desc "Save client_secrets.json out of the CVS"
task :keep_secrets do
  sh "cp client_secrets.json.unfilled client_secrets.json "
end

desc "Use the filled client_secrets"
task :use_keys do
  sh "cp client_secrets.json.filled client_secrets.json "
end

desc "Go to console.developers.google"
task :link do
  sh "open https://console.developers.google.com/project/apps~sinatra-ruby-gplus/apiui/api"
end

desc "Commit changes"
task :ci, [ :message ] => :keep_secrets do |t, args|
  message = args[:message] || ''
  sh "git ci -am '#{message}'"
end
