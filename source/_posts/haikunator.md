title: Haikunator
date: 2016-03-28 23:26:23
tags:
- haikunator
- ruby
- random
- beginner
---

Today's video shows how the https://github.com/usmanbashir/haikunator rubygem works.

{% youtube ayCKiRRsOSM %}

## Useful/Interesting techniques

~~~ruby
# get a random number
SecureRandom.random_number(4000) #=> gives a max number between 0 to 4000
# get a random element from an array
[1, 2, 3, 4, 5].sample #=> 3

# use 36 character encoding to shorten a numeric id to an alphanumeric id
1_000_000.to_s(36) #=> "lfls"

# use compact to remove nils from an array
[:foo, nil, 33].compact #=> [:foo, 33]
~~~
