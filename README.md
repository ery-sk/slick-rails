# jQueryプラグインSlickを使う
```bash
rails new . -T -O
rails g controller home index
```
```ruby
# routes.rb
root 'home#index'
```
```ruby
# Gemfile
gem 'jquery-rails'
```
```bash
bundle
```
```js
// application.js
//= require jquery
```
[Slickファイルダウンロード](https://github.com/kenwheeler/slick/archive/v1.8.1.zip)

`slick.js`と`slick.scss`を`vendor/assets/javascripts(stylesheets)`に格納
```erb
<%# home/index.html.erb %>
<div class="slider">
  <div><%= image_tag 'image1' %></div>
  <div><%= image_tag 'image2' %></div>
</div>
```
```rb
# config/initializers/assets.rb
Rails.application.config.assets.paths << Rails.root.join('vendor', 'assets', 'stylesheets')
Rails.application.config.assets.paths << Rails.root.join('vendor', 'assets', 'javascripts')
```
```js
// application.js
//= require slick
```
```css
/* application.css */
/*= require slick */
```
```coffee
# home.coffee
$ ->
  $('.slider').slick()
```
```bash
rails s
```
