# WUIF1710-yidong
移动网页项目提交地址

员天伦


https://yuantianlun.github.io/yidong
<script>
    //push
    //参数：一个或者多个值
    //返回值：新数组的长度
    //作用：在数组的末尾添加元素
    var arr = [1, 2, 3, 4, 5, 6];
    arr.push(7, 8, 9);
    console.log(arr);  //[1,2,3,4,5,6，7,8,9];

    //unshift
    //参数：一个或者多个元素
    //返回值：新数组的长度
    //作用：在数组的开始位置添加元素
    var arr = [1, 2, 3, 4, 5, 6];
    arr.unshift(0);
    console.log(arr);  //[0，1,2,3,4,5,'hd'];

    //pop
    //参数：一个
    //返回值：被删除的元素内容
    //作用：在数组的末尾删除一个元素
    var arr = [1, 2, 3, 4, 5, 6];
    arr.pop();
    console.log(arr);//[1,2,3,4,5]
    //shift
    //参数：一个
    //返回值：被删除的元素内容
    //作用：在数组的开始删除一个元素
    var arr = [1, 2, 3, 4, 5, 6];
    arr.shift()
    console.log(arr)//[2,3,4,5,6]
    //splice
    // 参数：第一个参数是操作的位置，第二个参数是删除的个数，后续参数是
    // 要添加的内容，最少2个
    //返回值：被删除元素所组成的数组
    //作用：万能的添加删除方法
    var arr = [1, 2, 3, 4, 5, 6];
    arr.splice(1, 0, 7, 8, 9)
    console.log(arr)//[1, 7, 8, 9, 2, 3, 4, 5, 6]
    //join
    //参数：字符串
    //作用：将数组通过输出的符号连接,将数组转化为字符串
    var arr = [1, 2, 3, 4, 5, 6];
    var str = arr.join();
    console.log(str)//   1,2,3,4,5,6
    //concat
    //作用：将多个数组合并成一个
    //返回值：一个数组
    //参数：多个数组
    var arr = [1, 2, 3, 4, 5, 6]
    var arr1 = ['a', 'b', 'c']
    var str = arr.concat(arr1);
    console.log(str);//[1, 2, 3, 4, 5, 6, 7, "a", "b", "c"]
    //slice
    // 返回值：一个数组
    //参数：任意数组
    //作用：从数组中截取一段指定内容
    var arr = [1, 2, 3, 4, 5, 6, 7];
    var str = arr.slice(2, 6);
    console.log(str); //[3, 4, 5, 6]
    //sort
    //返回值：一个数组
    //参数：数组
    //作用：给数组排序
    var arr = [1, 5, 6, 8, 9, 4, 8, 6];
    var str = arr.sort();
    console.log(str);//[1,4,5,6,6,8,8,9]
    //

    //forEach
    //作用：将数组中的元素遍历
    var arr = [20, 52, 59, 6, 75, 99, 86];
    var newarr = [];
    arr.forEach(function (value, index) {
        if (value > 60) {
            newarr.push(value);
        }
    });
    console.log(newarr);//[75, 86, 99]
    //filter
    //作用：筛选元素
    var arr = [20, 52, 59, 6, 75, 99, 86];
    var newarr = arr.filter(function (value, index) {
        if (value > 60) {
            return true;
        }
    });
    console.log(newarr);//[75, 85, 99]
    //map
    //作用：映射
    var arr = [1, 2, 3, 4, 5];
    var newarr = arr.map(function (v, i) {
        return v * v;

    });
    console.log(newarr);//[1, 4, 9, 16, 25]
    //every
    //作用：判断数组中每一个元素是否都满足条件
    var arr = [15, 75, 62, 84, 95];
    var newarr = arr.every(function (v) {
        if (v < 60) {
            return false;
        }
    })
    console.log(newarr);  //false

    //some
    //作用：判断数组中是否有满足条件的元素
    var arr = [15, 75, 62, 84, 95];
    var newarr = arr.some(function (v) {
        if (v > 90) {
            return true;
        }
    })
    console.log(newarr);  //true

    var arr = [1, 2, 3, 4, 5, 4, 5];
    //indexOf
    //作用：获取数组中某个值第一次出现的下标
    console.log(arr.indexOf(1));//0
    //lastIndexOf
    //作用：获取数组中某个值最后一次出现的下标
    console.log(arr.lastIndexOf(4));//5
    //reverse
    //作用：将数组中的内容反向展示（倒序）
    arr.reverse();
    console.log(arr)//[5, 5, 4, 4, 3, 2, 1]
    //reduce
    //作用：将数组中的元素累加/减/乘···
    var arr = [1, 2, 3, 4];
    var num = arr.reduce(function (a, b) {
        return a + b;
    });
    console.log(num);//10
    //reduceRight
    //作用：将数组中的元素从右向左累加/减/乘···
    var arr = [1, 2, 3, 4];
    var num = arr.reduceRight(function (v, i) {
        return v + i;
    });
    console.log(num)//10
    //find
    //作用：根据我们所设置的条件进行查找，将满足条件的值返回
                var arr=[1,2,3,4,5];
                arr.find(function (v, i) {
                    if (i**2==4){
                       return i;
                    }
                })
    //               console.log(i)
    var arr=[
        {name:"lisi",grade:75},
        {name:"zhanshan",grade:95},
        {name:"wangwu",grade:85}
    ];
    var result = arr.find(function (value) {
        if (value.grade === 85) {
            return true;
        }
    })
    //               console.log(value)
    //findIndex
    //作用：根据我们所设置的条件进行查找，将满足条件的值的位置返回
    var arr=[
                {name:"lisi",grade:75},
                {name:"zhanshan",grade:95},
                {name:"wangwu",grade:85}
            ];
    var result=arr.findIndex(function(value){
               if(value.grade===85){
                        return true;
                    }
            })
            console.log(result);
    //fill
    //作用：对数组进行填充，把数组中的空值填充为某个值
    var arr = new Array(5);
    arr.fill(5)
    console.log(arr);
    [5, 5, 5, 5, 5]

    //copyWithIn
    //用数组中的某一部分代替另一部分
    var arr = [1, 2, 3, 4, 5];
    arr.copyWithin(0, 2);
    console.log(arr);//[3, 4, 5, 4, 5]
    //includes
    //作用：真正判断数组中是否包含某个值的方法
    var arr = [1, 2, 3, 4, 5];
    console.log(arr.includes(1));//true
    //Array.from
    //作用：类似数组(有length属性)的对象中创建一个新的数组
    function fn() {
        console.log(Array.from(arguments))
    }
    fn(1, 2, 3, 4, 5);//[1, 2, 3, 4, 5]

    //Array.of
    //作用:创建一个具有可变数量参数的新数组，而不考虑参数的数量或类型
    var arr = new Array(1,2,3);
    var arr = Array.of(1,2,3);
    console.log(arr);//[1,2,3]

    // isArray
    //作用：确定传递的值是否是一个 Array
      console.log(Array.isArray(111));//false

</script>
