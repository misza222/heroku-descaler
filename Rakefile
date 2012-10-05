require 'heroku-api'

if ENV['HEROKU_APP'].nil?       || ENV['HEROKU_APP'].empty? ||
   ENV['HEROKU_API_KEY'].nil?   || ENV['HEROKU_API_KEY'].empty? ||
   ENV['NUMBER_WHEN_UP'].nil?   || ENV['NUMBER_WHEN_UP'].empty? ||
   ENV['NUMBER_WHEN_DOWN'].nil? || ENV['NUMBER_WHEN_DOWN'].empty?
     raise "Please set HEROKU_APP, HEROKU_API_KEY, NUMBER_WHEN_UP and NUMBER_WHEN_DOWN variables. See README.md for details."
end

task :setup do
    @heroku = Heroku::API.new
end

task :scale_up => :setup do
    @heroku.post_ps_scale(ENV['HEROKU_APP'], 'web', ENV['NUMBER_WHEN_UP'])
end

task :scale_down => :setup do
    @heroku.post_ps_scale(ENV['HEROKU_APP'], 'web', ENV['NUMBER_WHEN_DOWN'])
end
