**Jan 18th, 2009 - Note: we're still moving in here.  Things are a little rough right now.**

Whirlycache is a fast, configurable in-memory object cache for Java. It can be used, for example, to speed up a website or an application by caching objects that would otherwise have to be created by querying a database or by another expensive procedure. From the testing that we have done, it appears to be faster than any other Java cache that we have been able to inspect.

For the impatient, here's how to get started using Whirlycache. You will first need to provide a whirlycache.xml file in your classpath as well though.

```
//Use the cache manager to create the default cache
Cache c = CacheManager.getInstance().getCache();

//Put an object into the cache
c.store("yourKeyName", new WhateverObject());

//Get the object back out of the cache
WhateverObject o = (WhateverObject) c.retrieve("yourKeyName");

//Shut down the cache manager
CacheManager.getInstance().shutdown();
```

As you can see, this is straightforward. You can have many named caches or you can just use the default cache.

If you are using Cocoon and want to use Whirlycache as the Store implementation, you should read the Whirlycache+Cocoon Howto.