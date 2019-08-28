---
layout: post
title: Permutations
---

Perhaps we could attempt to mimic Haskell's concise x:xs syntax?

<!--kg-card-begin: code-->

    template <typename T, template class CONT>
    void operator<<=(T &x, CONT &xs) {
    	x = xs.front();
        xs.pop_front();
    }

<!--kg-card-end: code-->

And remove the head from a list like thus:

<!--kg-card-begin: code-->

    a <<= vec;

<!--kg-card-end: code-->
## Append to list operator (push back)

Not concerning ourselves with the overhead of reallocation.

<!--kg-card-begin: code-->

    template <typename T, template <typename> class CONT>
    CONT<T> operator+(CONT<T> a, const T &b) {
    	a.push_back(b);
    	return a;
    }

<!--kg-card-end: code-->