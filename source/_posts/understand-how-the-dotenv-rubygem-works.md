title: Understand how the dotenv rubygem works
date: 2016-03-16 02:37:43
tags:
- dotenv
- ruby
- environment
- parser
- railtie
- regex
---

Today's video shows how the popular https://github.com/bkeepers/dotenv project works.

{% youtube MdcpJw4-QgQ %}

## Useful/Interesting techniques

~~~ruby
## use of ignoring_nonexistent_files as a DRY helper method to rescue and ignore Errno::ENOENT errors
  def ignoring_nonexistent_files
    yield
  rescue Errno::ENOENT
  end

  # with the above code the following wouldn't throw an error

  ignoring_nonexistent_files { File.read("/non/existent/file") }


## use of the hash.update method to update a hash's keys

  h = {a: 1, b: 2}
  h.update(b: 20, c: 40)

  puts h # => {:a=>1, :b=>20, :c=>40}

## use of symbol to proc
  File.open(@filename, "rb:bom|utf-8", &:read) #=>  File.open(@filename, "rb:bom|utf-8") {|f| f.read}

## discard/ignore a regex group using ?:

  "export FOO=bar".match(/(?:export\s+)?([\w]+)=([\w]+)/) # would return two matches http://rubular.com/r/geRhhYNzJe

~~~


## Notes

  1. [The ruby regex documentation](http://ruby-doc.org/core-2.2.0/Regexp.html)
  2. [The rubular ruby regular expression editor](http://rubular.com/)

