ignore /.asset-cache/,/build/,/.deploy/,/_site/,/.sass-cache/,/.idea/

guard 'jekyll-plus' do
  watch /.*/
end

guard 'livereload', notify: true, host: '0.0.0.0', apply_css_live: true, grace_period: 0.5 do
  watch /.*/
end