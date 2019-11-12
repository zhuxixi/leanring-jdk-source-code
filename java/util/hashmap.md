# HashMap源码解析

## 基础知识

* AbstractMap
* Map<K,V>
* Cloneable
* Serializable

## Java Doc 正文
这是一个Map接口的哈希表实现。这个实现提供了所有的map操作，允许null值和null键。(HashMap类和Hashtable基本一样，区别是HashMap不是线程安全的
而且允许null。)这个类不会保证map中元素的顺序； 而且元素的顺序不会一直保持不变，可能随着新元素的添加，顺序就变化了。

假如hash算法足够优秀，没有哈希冲突，这样哈希表中的每个元素都分散在不同的哈希桶中时，那么hashMap的一些基本方法都是O(1)复杂度的，快的一笔(get和put)。
迭代整个集合的耗时与HashMap的capacity和它的size成正比。因此，如果迭代的性能对你来说很重要，那么不要将initial capacity设置太高(或者负载因子设置太低)
。
> 后面会解答原因

HashMap的两个参数会影响其性能: initial capacity和 load factor(负载因子)
capacity就是哈希表的桶的数量，initial capacity就是哈希表在创建时的capacity(废话)。
load factor用例测量哈希表的水位，然后自动增长它的capacity。当entry的数量超过`load factor * current capacity`时，哈希表就会rehash(
所有的内部数据都会重建)所以哈希表会有2倍的长度。

一般来说，默认的load factor(.75)在时间和空间都是最优的。如果这个值很大，会减少空间浪费，但是会提高查找的消耗(大多数HashMap的方法都会有影响，包括get和put)。
HashMap要保存的数据量和load factor应该在map初始化时就要去考虑，这样才能减少rehash的次数，因为这是很耗费性能的。
如果initial capacity 大于entry最大值除以 load factor(`initial capacity> entry count /load factor`)，那么永远都不会发生rehash。

If many mappings are to be stored in a HashMap instance,
 creating it with a sufficiently large capacity will allow the mappings to be stored more efficiently 
 than letting it perform automatic rehashing as needed to grow the table. 
 Note that using many keys with the same hashCode() is a sure way to slow down performance of any hash table.
  To ameliorate impact, when keys are Comparable, this class may use comparison order among keys to help break ties.

Note that this implementation is not synchronized. If multiple threads access a hash map concurrently, and at least one of the threads modifies the map structurally, it must be synchronized externally. (A structural modification is any operation that adds or deletes one or more mappings; merely changing the value associated with a key that an instance already contains is not a structural modification.) This is typically accomplished by synchronizing on some object that naturally encapsulates the map. If no such object exists, the map should be "wrapped" using the Collections.synchronizedMap method. This is best done at creation time, to prevent accidental unsynchronized access to the map:

   Map m = Collections.synchronizedMap(new HashMap(...));
The iterators returned by all of this class's "collection view methods" are fail-fast: if the map is structurally modified at any time after the iterator is created, in any way except through the iterator's own remove method, the iterator will throw a ConcurrentModificationException. Thus, in the face of concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior at an undetermined time in the future.

Note that the fail-fast behavior of an iterator cannot be guaranteed as it is, generally speaking, impossible to make any hard guarantees in the presence of unsynchronized concurrent modification. Fail-fast iterators throw ConcurrentModificationException on a best-effort basis. Therefore, it would be wrong to write a program that depended on this exception for its correctness: the fail-fast behavior of iterators should be used only to detect bugs.

This class is a member of the Java Collections Framework.

## 构造器

## 方法

## 源码解析

## 样例代码

## 扩展阅读
* LinkedHashMap
* PrinterStateReasons

## 总结

