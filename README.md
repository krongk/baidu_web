# Baidu_web

Baidu_web是一个基于百度的元搜索引擎，输入关键字，返还百度搜索结果和相关的关键词；
在线Demo: http://www.inruby.com/search

## 用法

    gem 'baidu_web'

## 返还结果

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

## 在irb中测试:

    $:.unshift(File.dirname(__FILE__))
    require 'baidu_web'
    require 'cgi'
    result = BaiduWeb.search(CGI.escape("游戏"), :per_page => 10, :page_index => 1)
