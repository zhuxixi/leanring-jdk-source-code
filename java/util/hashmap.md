# HashMapԴ�����

## ����֪ʶ

* AbstractMap
* Map<K,V>
* Cloneable
* Serializable

## Java Doc ����
����һ��Map�ӿڵĹ�ϣ��ʵ�֡����ʵ���ṩ�����е�map����������nullֵ��null����(HashMap���Hashtable����һ����������HashMap�����̰߳�ȫ��
��������null��)����಻�ᱣ֤map��Ԫ�ص�˳�� ����Ԫ�ص�˳�򲻻�һֱ���ֲ��䣬����������Ԫ�ص���ӣ�˳��ͱ仯�ˡ�

����hash�㷨�㹻���㣬û�й�ϣ��ͻ��������ϣ���е�ÿ��Ԫ�ض���ɢ�ڲ�ͬ�Ĺ�ϣͰ��ʱ����ôhashMap��һЩ������������O(1)���Ӷȵģ����һ��(get��put)��
�����������ϵĺ�ʱ��HashMap��capacity������size�����ȡ���ˣ�������������ܶ�����˵����Ҫ����ô��Ҫ��initial capacity����̫��(���߸�����������̫��)
��
> �������ԭ��

HashMap������������Ӱ��������: initial capacity�� load factor(��������)
capacity���ǹ�ϣ���Ͱ��������initial capacity���ǹ�ϣ���ڴ���ʱ��capacity(�ϻ�)��
load factor����������ϣ���ˮλ��Ȼ���Զ���������capacity����entry����������`load factor * current capacity`ʱ����ϣ��ͻ�rehash(
���е��ڲ����ݶ����ؽ�)���Թ�ϣ�����2���ĳ��ȡ�

һ����˵��Ĭ�ϵ�load factor(.75)��ʱ��Ϳռ䶼�����ŵġ�������ֵ�ܴ󣬻���ٿռ��˷ѣ����ǻ���߲��ҵ�����(�����HashMap�ķ���������Ӱ�죬����get��put)��
HashMapҪ�������������load factorӦ����map��ʼ��ʱ��Ҫȥ���ǣ��������ܼ���rehash�Ĵ�������Ϊ���Ǻܺķ����ܵġ�
���initial capacity ����entry���ֵ���� load factor(`initial capacity> entry count /load factor`)����ô��Զ�����ᷢ��rehash��

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

## ������

## ����

## Դ�����

## ��������

## ��չ�Ķ�
* LinkedHashMap
* PrinterStateReasons

## �ܽ�

