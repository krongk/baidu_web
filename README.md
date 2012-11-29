# MetaTags: a gem to make your Rails application SEO-friendly

[![Travis-CI build status](https://secure.travis-ci.org/kpumuk/meta-tags.png)](http://travis-ci.org/kpumuk/meta-tags)

Search Engine Optimization (SEO) plugin for Ruby on Rails applications.

## Rails 3

MetaTags master branch now fully supports Rails 3 and is backward
compatible.

## Installation

Add the "meta-tags" gem to your `Gemfile`.

    gem 'meta-tags', :require => 'meta_tags'

And run `bundle install` command.

## SEO Basics and MetaTags

### Titles

Page titles are very important for Search engines. The titles in the
browser are displayed in the title bar. The search engines would look at
the this title bar to determine what the page is all about.

    set_meta_tags :title => 'Member Login'
    # <title>Some Page Title</title>
    set_meta_tags :site => 'Site Title', :title => 'Member Login'
    # <title>Site Title | Page Title</title>
    set_meta_tags :site => 'Site Title', :title => 'Member Login', :reverse => true
    # <title>Page Title | Site Title</title>

Recommended title tag length: up to <b>70 characters</b>, <b>10 words</b>.

# Baidu_web

Baidu_web是一个基于百度的元搜索引擎，输入关键字，返还百度搜索结果和相关的关键词；
在线Demo: http://www.inruby.com/search

## 用法

    gem 'baidu_web'

## 返还结果

### Use baidu_web:

    result = BaiduWeb.search('key words')
    result[:record_arr].each do |record|
      puts record.title
      puts record.url
      puts record.summary
      puts record.updated_date
      puts record.item_index
      puts record.cached_url
    end
    result[:ext_key_arr].each do |ext_key|
     puts ext_key.title
     puts ext_key.url
    end

### Test baidu_web gem on irb:

    $:.unshift(File.dirname(__FILE__))
    require 'baidu_web'
    require 'cgi'
    result = BaiduWeb.search(CGI.escape("游戏"), :per_page => 10, :page_index => 1)
