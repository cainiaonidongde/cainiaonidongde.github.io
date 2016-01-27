---
layout: post
title: 代码测试
categories: [algorithm]
tags: [algorithm,icpc]
---



{% highlight c++ %}
void manacher(char* s)
{
    int c = 0, r = 0, len = strlen(s);
    p[0] = 0;
    for( int i = 1; i < len ; ++i ) {
        if( r > i ) p[i] = min( p[ 2 * c - i ], r - i );
        else p[i] = 0;
        while( i < len && s[i + 1 + p[i]] == s[i - 1 - p[i]] ) p[i]++;
        if( i + p[i] > r ) {
            r = i + p[i];
            c = i;
        }
    }
}
{% endhighlight %}

