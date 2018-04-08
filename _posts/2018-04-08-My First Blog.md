---
layout: post
title: "First Blog in Github"
date: 2018-04-08 17:00
image: ''
description: ''
tags:
- etc
- None
categories:
- None
---

This is a highlight test.

# Normal block

```
alert('Hello World!');
```

    print 'helloworld'

# Highlight block
Java
```javascript
alert( 'Hello, world!' );
```

Python
```python
print 'helloworld'
```

Ruby
```ruby
def foo
  puts 'foo'
end
```

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

C++
```c++
#include <iostream>

using namespace std;

void foo(int arg1, int arg2)
{

}

int main()
{
  string str;
  foo(1, 2);
  cout << "Hello World" << endl;
  return 0;
}
```
