# Date
* ## dateFormat

  将日期按照指定格式格式化并返回格式化后的日期。

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    date(number | Date): 预格式化的日期。
    format(string): 日期格式。
  ```
  <b>Returns</b>
  ```
    (string): 返回格式化后的日期。
  ```
  <b>Example</b>
  ```js
    EUtils.dateFormat(1531643785284, 'yyyy-MM-dd');
    // => '2018-07-15';
  ```

* ## now
  
  获取当前时间的时间戳。

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Returns</b>
  ```
    (number): 返回当前时间的时间戳。
  ```
  <b>Example</b>
  ```js
    EUtils.now();
    // => 1537347030735;
  ```

* ## toTimestamp
  
  将日期时间转换成时间戳

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    date(Number | Date | String): 传入的预转换的日期。
  ```
  <b>Returns</b>
  ```
    (number): 返回转换后的时间戳。
  ```
  <b>Example</b>
  ```js
    EUtils.toTimestamp(new Date());
    // => 1536659540425;

    EUtils.toTimestamp('2018-09-09');
    // => 1536451200000;

    EUtils.toTimestamp(1536422400000);
    // => 1536422400000
  ```

* ## isDate

  判断所给参数是否为Date类型

  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    isDate(Number | Date | String): 传入需要判断的值。
  ```
  <b>Returns</b>
  ```
    (boolean): 返回是否为Date。
  ```
  <b>Example</b>
  ```js
    EUtils.isDate(new Date());
    // => true

    EUtils.isDate('2018-09-09');
    // => false

    EUtils.isDate(null);
    // => false
  ```

# Url
* ## setUrlParam

  向当前Url或目标Url添加参数，originUrl不传则默认使用当前Url

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    params(object)：需要添加的参数对象，如果key值再url中已存在，则会进行替换
    originUrl(string)：被操作的Url地址，不传则默认使用window.location.href
  ```
  <b>Returns</b>
  ```
    (string)：返回拼接好后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.setUrlParam({
        id: 2,
        name: 3
    }, 'http://www.ewt360.com?id=1');
    // => http://www.ewt360.com?id=2&name=3
  ```
      
* ## getUrlParam

  从当前Url或目标Url获取参数，originUrl不传则默认使用当前Url

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    key(string)：需要获取的参数key
    originUrl(string)：被操作的Url地址，不传则默认使用window.location.href
  ```
  <b>Returns</b>
  ```
    (string)：返回查找到的参数值value,如果未找到则返回空字符串
  ```
  <b>Example</b>
  ```js
    EUtils.getUrlParam('id', 'http://www.ewt360.com?id=1');
    // => 1
  ```

# String
* ## repalce

  将str字符串中指定的pattern字符替换成replacement字符，惰性匹配，匹配到一个就不会匹配后面的

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    str： 原始串,
    pattern：要替换的字符串或正则,
    replacement：替换的目标字符串
  ```
  <b>Returns</b>
  ```
    (string)：返回替换后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.replace('hello world', /o/, 'hi')

    // => 'hellhi world'
  ```

* ## repalceAll

  将str字符串中指定的sourcement字符全都替换成replacement字符

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    str： 原始串,
    sourcement：要替换的字符串或正则,
    replacement：替换的目标字符串
  ```
  <b>Returns</b>
  ```
    (string)：返回替换后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.replaceAll('hello wOrld', /o/i, 'hi')

    // => 'hellhi whirld'
  ```

* ## toLower

  将str字符串大写全部转成小写

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    str： 原始串
  ```
  <b>Returns</b>
  ```
    (string)：返回小写后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.toLower('hellO-wOrld')

    // => 'hello-world'
  ```

* ## toUpper

  将str字符串小写全部转成大写

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    str： 原始串
  ```
  <b>Returns</b>
  ```
    (string)：返回大写后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.toUpper('hello-world')

    // => 'HELLO-WORLD'
  ```

* ## trim

  将str字符串前后空格

  <b>Since</b>
  ```
    1.0.0
  ```
  <b>Arguments</b>
  ```
    str： 原始串
    chars: 去除后的替换成字符（省略此参数，就空格）
  ```
  <b>Returns</b>
  ```
    (string)：返回去除后的字符串
  ```
  <b>Example</b>
  ```js
    EUtils.trim(' abbb ')
    // => 'abbb'
  ```

* ## generateUUID

  生成唯一的通用标识符（UUID），可用于生成react的列表渲染时所需的key

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Returns</b>
  ```
    (string)：返回唯一的UUID
  ```
  <b>Example</b>
  ```js
    EUtils.generateUUID()

    // => 'af22-3fa8-4028-8dea-30a2'
  ```

* ## getStylePrefix

  获取指定值的浏览器前缀
  
  <b>Arguments</b>
  ```
  propertyKey(string): 需要获取前缀的样式值，如transform
  isConcat(boolean): 是否需要返回拼接后的字符串，默认为true，如只需要前缀则传false
  ```
  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Returns</b>
  ```
    (string)：默认返回样式前缀+该样式本身
  ```
  <b>Example</b>
  ```js
    EUtils.getStylePrefix('transform')
    // => '-ms-transform'

    EUtils.getStylePrefix('transform', false)
    // => '-ms-'
  ```

# Array
* ## indexOf

  数组中查找指定字符

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Returns</b>
  ```
    (number)：指定字符再数组中索引
  ```
  <b>Example</b>
  ```
    EUtils.indexOf([1, 2, 1, 2], 2)
    // => 1

    EUtils.indexOf([1, 2, 1, 2], 2, 2)
    // => 3
  ```

* ## includes

  从fromIndex索引开始查找collection集合中是否存在value，惰性匹配，匹配到一个就不会匹配后面的，返回Boolean类型值
  注意：fromIndex不支持负数，出现问题后果自负

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    collection： 集合|字符串|字面量对象,
    value：要查找的值,
    fromIndex：从指定索引开始查找
  ```
  <b>Returns</b>
  ```
    (boolean)：返回布尔值true|false
  ```
  <b>Example</b>
  ```js
    EUtils.includes('abccdd', 'cc')
    // => true

    EUtils.includes({cc: 222}, 'cc')
    // => true

    EUtils.includes(true, 'cc')
    // => false

    EUtils.includes([1, 3, [1,2], {1:3}], {1:3})
    // => true

    EUtils.includes([1, 3, [1,2], {1:3}], {1:3}, 4)
    // => false
  ```

* ## unique

  将arr中重复元素过滤，返回唯一元素新数组，支持对象的判断

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    arr： 数组,
    iterator：过滤器方法,
  ```
  <b>Returns</b>
  ```
    (array)：返回不重复元素的数组
  ```
  <b>Example</b>
  ```js
    EUtils.unique([1, 3, 5, 6, 8, 8, 6, 3, [1,2], [1,2], {item: 1, 2: 3}, {item: 1, 2: 3}])
    // => [1, 3, 5, 6, 8, [1,2], {item: 1, 2: 3}]
  ```

* ## union

  将firstArr和secondArr数组合并，并过滤重复的元素，返回一个新的数组。

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    firstArr: 第一个数组
    secondArr: 第二个数组
  ```
  <b>Returns</b>
  ```
    (array)：返回一个新的数组
  ```
  <b>Example</b>
  ```js
    EUtils.union([1, 3, 5],  [6, 8, 8, 6, 3])
    // => [1, 3, 5, 6, 8]
  ```

* ## minus

  将firstArr与secondArr数组做差集，返回一个差集后的数组

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    firstArr: 第一个数组
    secondArr: 第二个数组
  ```
  <b>Returns</b>
  ```
    (array)：返回一个新的数组
  ```
  <b>Example</b>
  ```js
    EUtils.minus([1, 3, 5, 6], [8, 8, 6, 3, 2])
    // => [1, 5]
  ```

* ## intersection

  将firstArr与secondArr数组做交集，返回一个交集后的数组

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    firstArr: 第一个数组
    secondArr: 第二个数组
  ```
  <b>Returns</b>
  ```
    (array)：返回一个新的数组
  ```
  <b>Example</b>
  ```js
    EUtils.intersection([1, 3, 5, 6], [8, 8, 6, 3])
    // => [3, 6]
  ```

* ## max

  计算数组中的最大值

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    array: 数字或字母的数组
  ```
  <b>Returns</b>
  ```
    (Number ｜ String)：返回数组中的最大值
  ```
  <b>Example</b>
  ```js
    EUtils.max([1, 3, 5, 6])
    // => 6

    EUtils.max(['a', 'b', 'c'])
    // => c
  ```

* ## min

  计算数组中的最小值

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    array: 数字或字母的数组
  ```
  <b>Returns</b>
  ```
    (Number ｜ String)：返回数组中的最小值
  ```
  <b>Example</b>
  ```js
    EUtils.min([1, 3, 5, 6])
    // => 1

    EUtils.max(['a', 'b', 'c'])
    // => a
  ```

* ## sum

  计算数组中值的和

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    array: 数字或字母的数组
  ```
  <b>Returns</b>
  ```
    (Number ｜ String)：返回数组中的和
  ```
  <b>Example</b>
  ```js
    EUtils.sum([1, 3, 5, 6])
    // => 15

    EUtils.sum(['a', 'b', 'c']) 
    // => 'abc'
  ```

* ## isArray

  判断入参是否为数组

  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Returns</b>
  ```
    (boolean)：true | false
  ```
  <b>Arguments</b>
  ```
    obj: Array类型
  ```
  <b>Example</b>
  ```js
    EUtils.isArray([1, 2, 3])
    // => true

    EUtils.isArray(document.body.children)
    // => false

    EUtils.isArray('abc')
    // => false
  ```

* ## rest

  返回剩余数组元素集合

  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Returns</b>
  ```
    (Array)：[]
  ```
  <b>Arguments</b>
  ```
    sourceArr: Array类型
    index: 索引位置，默认0
  ```
  <b>Example</b>
  ```js
    EUtils.rest([1, 2, 3]);
    // => [2,3]

    EUtils.rest([]);
    // => []

    EUtils.rest([1, 2, 3], 2);
    // => [3]

    EUtils.rest([1, 2, 3], -2);
    // => [2,3]
  ```

# Storage
* ## setCookie

  往当前域(可设置)的cookie里写值

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    name:cookie的名称,string类型
    value:cookie的值，string/object类型。若为对象会被转化为JSON
    config:对该cookie的额外配置, object类型。可作如下配置:{
        expires:7                       int类型, 指定该cookie过期的天数
        domain:'www.domain.com',        string类型, 指定cookie的域，可以指定为子域
        path:'/cookie/path',            string类型, 指定cookie的路径
        secure:true                     boolean类型,指定cookie是否只能在https协议下才可以读取
    }
  ```
  <b>Example</b>
  ```js
    setCookie('name','value');
  ```

* ## getCookie

  读取cookie的值

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    name:cookie的名称,string类型
    isObject:是否以对象的形式读取该cookie，返回的值会被转化成对象，若转化失败则返回null
  ```
  <b>Returns</b>
  ```
    返回该cookie的值
  ```
  <b>Example</b>
  ```js
    getCookie('name')
    //=>'value'
  ```

* ## removeCookie

  删除cookie的值

  <b>Since</b>
  ```
    1.1.0
  ```
  <b>Arguments</b>
  ```
    name:cookie的名称,string类型
    config:cookie的设置，必须与setCookie时的domain和path一致，该cookie才会被正确删除
  ```
  <b>Example</b>
  ```js
    removeCookie('name')
  ```

# DOM
* ## isElement

  判断给定的值是否为dom元素
  
  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    element
  ```
  <b>example</b>
  ```js
    EUtils.isElement(1);
    //=> false 

    EUtils.isElement(document.crateElement('div'));
    //=> true
  ```

* ## position

  元素距离页面顶端的距离

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    elem：DOM元素对象
    type：距离页面的距离，默认值'' => {left: ..., top: ...}
  ```
  <b>example</b>
  ```js
    EUtils.position(document.getElementById('domJS')))
    //=> {top: 20, left: 200}

    EUtils.position(document.getElementById('domJS')), 'left')
    //=> 200

    EUtils.position(document.getElementById('domJS')), 'top')
    //=> 20
  ```

* ## scrollTop

  元素的滚动条位置

  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    elem：DOM元素对象
    target：移动到目标位置
  ```
  <b>example</b>
  ```js
    EUtils.scrollTop(window)
    //=> 20

    EUtils.scrollTop(document)
    //=> 20

    document.getElementById('domJS').onscroll = function(){
      console.log('domJS -> scrollTop: ', EUtils.scrollTop(this));
    };
    //=> domJS -> scrollTop: 20
  ```

# Object
* ## keys

  获取object所有键值

  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    obj(Object): 需要获取所有key的对象。
  ```
  <b>Returns</b>
  ```
    (array): 返回所有键值的数组。
  ```
  <b>Example</b>
  ```js
    EUtils.keys({one: '1', two: 'two'});
    // => ['one', 'two']
    
    EUtils.keys({one: '1', two: 'two'});
    // => ['one', 'two']
  ```

* ## isObject

  检测入参是否为对象

  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    obj(Object): 需要检测的参数。
  ```
  <b>Returns</b>
  ```
    (boolean): 返回true|false。
  ```
  <b>Example</b>
  ```js
    EUtils.isObject({});
    // => true

    EUtils.isObject(document.body.children);
    // => true

    EUtils.isObject([]);
    // => true

    EUtils.isObject(null);
    // => false

    EUtils.isObject(Object.toString);
    // => false
  ```
    
* ## get

  获取对象指定路径的属性（路径用.分隔）
  
  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    object:对象
    path:路径
    defaultValue:属性不存在时返回的默认值
  ```
  <b>example</b>
  ```js
    EUtils.get({a:{b:1}},'a.b');
    // => 1
  ```

* ## clone

  浅拷贝一个对象
  
  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    object:要拷贝的对象
  ```
  <b>example</b>
  ```js
    EUtils.clone({a:{b:1}});
    // => {a:{b:1}}
  ```

* ## debounce

  函数防抖，指的是多次触发事件后，事件处理函数只执行一次，而且是在事件触发操作停止的时候。
  
  <b>Since</b>
  ```
    1.3.0
  ```
  <b>Arguments</b>
  ```
    func:要去抖的函数
    wait:毫秒数
  ```
  <b>description</b>
  ```
    函数去抖即在调用函数时先等待一段时间（比如1秒钟），若在1秒内没有对该函数再一次调用则执行函数；
    反之，则需要重新计时1秒。日常生活中，坐电梯就是一个很好去抖的例子。函数去抖可以规避在短时间内
    对某个函数的大量执行，经常用在scroll等DOM事件中。
  ```
  <b>example</b>
  ```js
    //generate the debounce function
    let debounced = EUtils.debounce(()=>{console.log(123)}, 500);
    //cancel the debounce function

    EUtils.debounced.cancel();
  ```
* ## throttle

  函数节流
  
  <b>Since</b>
  ```
    1.3.0
  ```
  <b>description</b>
  ```
    函数节流与函数去抖类似。区别在于，如果在等待时间内一直有调用，函数去抖会一直等待下去；
    而函数节流则会在等待指定的时间满时强制执行一次函数，从而保证在每个等待时间里至少执行一次函数。
  ```
  <b>Arguments</b>
  ```
    func:要节流的函数
    wait:毫秒数
  ```
  <b>example</b>
  ```js
    //generate the throttle function
    let throttled = EUtils.throttle(()=>{console.log(123)}, 500);
    //cancel the throttle function
  
    EUtils.throttled.cancel();
  ```

# Others
* ## has

  判断对象是否存在路径指定的属性
  
  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    object:对象
    path:路径
  ```
  <b>example</b>
  ```js
    EUtils.has({a:{b:1}},'a.b');
    // => true
  ```

* ## isEmpty

  判断给定的值是否为空（null/undefined/''/0/[]/{}/空迭代器对象）
  
  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    target:任意值
  ```
  <b>example</b>
  ```js
    EUtils.isEmpty([]);
    // => true
  ```

* ## isEqual

  判断给定的两个值值是否相等
  
  <b>Since</b>
  ```
    1.2.0
  ```
  <b>Arguments</b>
  ```
    value:任意值
    other:任意值
  ```
  <b>example</b>
  ```js
    EUtils.isEqual(1, '1');
    //=> false 
  ```
