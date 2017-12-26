

    push
    参数:一个或多个元素;
    返回值:构建的新数组的长度
   作用:在数组的末尾插入元素;
        var arr=[1,5,2,"bbb"];
        var newarr=[];
        for(var i=0;i<arr.length;i++){
            if(typeof arr[i]==="number"){
                newarr.push(arr[i]);
            }
        }
        console.log(newarr);
        var arr=[1,5,7,"abc"];
        var  r=arr.push(9);
        console.log(arr);
        console.log(r);

    pop
    参数:无
    返回值:被删除的元素
作用:删除数组的最后一个元素
        var arr=[1,5,7,"abc"];
        var  r=arr.pop();
        console.log(arr);
        console.log(r);

    unshift
   参数:一个或多个元素
   返回值:新数组的长度
   作用:在数组的开头插入元素
        var arr=[1,5,7,"abc"];
        var r=arr.unshift(9,5);
        console.log(r);
        console.log(arr);

    shift
参数:无;
返回值:删除的元素;
作用:在数组的开头删除元素;

    var arr=[5,8,7,"bcs"];
    var r=arr.shift();
    console.log(r);
    console.log(arr);

    splice
   参数:第一个:删除或添加的位置；第二个:删除的元素个数；第三个(及后面的元素):添加的元素
返回值:删除的元素；
作用:删除现有元素或添加新元素来更改一个数组的内容 。
       var arr=[5,8,7,"bcs"];
    var r=arr.splice(1,1,"x","y");
    console.log(arr);
    console.log(r);
    join
参数:指定一个符号来分隔数组的每个元素;
返回值:转化后的新的字符串；
作用:将数组或类数组对象的所有元素连接到一个字符串；
    var arr=[5,8,7,"bcs"];
    var newarr=arr.join("-");
    console.log(newarr);


    concat
参数:一个或多个字符串
返回值：构成的新数组
作用:将一个或多个数组与原数组连接
var arr=[5,8,7,"bcs"];
    var arr1=[1,5,8,"afss"];
    var newarr=arr1.concat(arr);
    console.log(arr)
    console.log(newarr);

    sort
 参数:可传入函数，在函数规定其排序规则；
返回值:构成的新数组；
作用:对数组中的元素进行排序；
    var arrays=[1,5,81,42,1,21,3,9];
    var newarr=arrays.sort(function(a,b){
        if(a>b){
            return 1;
        }else if(a<b){
            return -1;
        }
 });
    console.log(arrays);
    console.log(newarr);

    slice
  参数:第一个:起始的位置；第二个：结束的位置；注:-1表示最后一个元素，-x从后往前数
返回值:构成的新数组；
作用:在指定的位置进行截取，形成新数组；
var arrays=[1,5,8,4,1,2,3,9];
var newarr=arrays.slice(0,-2);
    console.log(arrays);
    console.log(newarr);


    封装
   forEach
   参数:函数可传入一个参数:当前值，索引，操作的数组
  返回值:undefined;
  作用:遍历数组的每一个元素；
    var arr=[
        {name:"lisi",grade:80},{name:"zhanshan",grade:50},{name:"rs",grade:85}
    ]
    Array.prototype.myforEach=function(callback){
        for(var i=0;i<this.length;i++){
            callback(this[i],i);
        }
    }
    arr.myforEach(function(value,index){
        console.table(value);
        console.log(index)
    })

    var arrays=[7,8,1,7,20,40,10,30];
    var newarr=new Array();
    arrays.forEach(function(value){
        if(value<10){
            newarr.push(value);
        }
    })
    console.log(newarr);

筛选
 参数:同forEach一样传入函数，函数中的参数相同；
 返回值:构成的新数组；
作用；通过函数制定的规则筛选下来的元素并形成新数组；
    var arr=[1,8,7,5,3,4];
    var newarr=arr.filter(function(value){
        return value >3;
    })
    console.log(newarr);
    Array.prototype.myfilter=function(callback){
        var newarr=[];
        for(var i=0;i<this.length;i++){
            var r=callback(this[i]);
            if(r){
                newarr.push(this[i]);
            }
        }
        return newarr;
    }
    var result=arr.myfilter(function(value){
        if(value>3){
            return true;
        }
    })
 console.log(result);


map
参数:同forEach;
返回值:构成的新数组；
作用：调用数组中的每个元素上调用一个提供的函数，并构成新函数；
  var arr=[2,5,8,7,4];
  var newarr=arr.map(function(value){
      return value*9;
  })
  console.log(newarr);
  some
参数:相似forEach
返回值:布尔值，true或false；
作用:测试数组的某些元素是否通过函数制定的规则的测试；
  var arr=[2,5,8,7,4];
var result=arr.some(function(value){
    if(value>1){
        return true;
    }
})
console.log(result);


   every
参数:相似forEach
返回值:布尔值，true或false；
作用:测试数组的全部元素是否通过函数制定的规则的测试；
var result=arr.every(function(value){
    if(value>0){
        return true;
    }
})
console.log(result);

  indexOf
参数:一个元素
返回值:元素在数组中的下标，当元素在数组中不存在时，则返回-1；
作用:在数组中找到元素第一个出现的位置；
var arr=[2,5,4,7,4,1,4,5];
var num=arr.indexOf(9);//返回-1;无值的时候
var num1=arr.indexOf(5)
console.log(num1);
  //lastIndexOf
参数:一个元素
返回值:元素在数组中的下标，当元素在数组中不存在时，则返回-1；
作用:在数组中找到元素最后一个出现的位置；
var arr=[2,5,8,7,4,4,8,4];
var num=arr.lastIndexOf(9)
console.log(num);
  reverse
参数:无
返回值:构造的函数；改变原数组
作用:数组中元素的位置颠倒；
  var arr=[2,5,4,7,4,1,4,5];
  var newarr=arr.reverse();
  console.log(newarr);
  console.log(arr);

    reduce
参数:callback(a,b,c,d)
返回值:单值，累加器得到的结果
作用:累加器和数组中的每个元素（从左到右）应用一个函数，将其减少为单个值；
    var arr=[
        {name:"lisi",grade:80},{name:"zhanshan",grade:50},{name:"rs",grade:85}
    ]
    var he=arr.reduce(function(a,b){
        return {grade:a.grade+b.grade};
    })
    console.log(he)
    var  arr1=[2,5,7];
    var arr=[[1,2,3],[4,5,6],[7,8,9]];
    var xx=arr.reduce(function(a,b){
        return a.concat(b);
    },arr1)

    console.log(xx)
    reduceRight
参数:callback(a,b,c,d)
返回值:单值，累加器得到的结果
作用:累加器和数组中的每个元素（从右到左）应用一个函数，将其减少为单个值；
var  arr1=[2,5,7];
    var arr=[[1,2,3],[4,5,6],[7,8,9]];
    var xx=arr.reduceRight(function(a,b){
        return a.concat(b);
    },arr1)

    console.log(xx);

    find
参数:callback(value,index,array);
返回值:第一个元素的值，不存在就返回undefined；
作用:返回数组中满足提供的测试函数的第一个元素的值。；
    var arr=[
        {name:"lisi",grade:80},{name:"zhanshan",grade:50},{name:"rs",grade:85}
    ]
    var result=arr.find(function(value){
        if(value.grade===85){
            return true;
        }
    })
findIndex
参数:callback(value,index,array);
返回值:第一个元素的值，不存在就返回-1；
作用:返回数组中满足提供的测试函数的第一个元素的索引(下标)；
var result=arr.findIndex(function(value){
    if(value.grade===85){
        return true;
    }
})
    console.log(result);


fill
参数:值；值，开始的位置；值,开始的位置，结束的位置(-1);
返回值:构成的数组，改变原数组；
作用:将数组的空值填充上某个固定的值；
  var arr=new Array(5);
  arr.fill(5)
  console.log(arr);

copyWithin
参数:目标索引, [源开始索引], [结束源索引];
返回值:构成的数组；
作用:浅拷贝数组的一部分到同一数组中的另一个位置，并返回它，而不修改其大小。；
  var arr=[2,5,7,7,8,9];
//  arr.copyWithin(1,3,6);//2,7,8,9,8,9
  arr.copyWithin(0,2);//7,7,8,9,8,9
  console.log(arr);

includes
参数:查找的元素值，开始的索引;
返回值:布尔值，true或false；
作用:用来判断一个数组是否包含一个指定的值；
var arr=[5,8,7,7];
var r=arr.includes(8);
    console.log(r);
Array构造函数里的
    isArray
参数:需要判断的值;
返回值:布尔值，true或false；
作用:确定传递的值是否是一个 Array
    var r1=Array.isArray([1,5,4]);
    console.log(r1)
    var r2=Array.isArray("zaijia");
    console.log(r2)

    form
参数:;
返回值:布尔值，true或false；
作用:一个类似数组(有length属性)或可迭代对象中创建一个新的数组实例
    console.log(Array.isArray("foo"))
    var r="foo";
    console.log(Array.from(r));

    of
参数:任意个元素;
返回值:数组；
作用:创建一个具有可变数量参数的新数组实例，而不考虑参数的数量或类型
console.log(Array.of(7));       // [7]
console.log(Array.of(1, 2, 3)); // [1, 2, 3]
