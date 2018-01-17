# js-every-filter-forEach-map-some-reduce-reduceRight
 js的every()-filter()-forEach()-map()-some()-reduce-reduceRight用法





          every()对数组中任何一项不满足就返回false

                           第一个参数，表示Array的某个元素。
                           第二个参数表示元素下标，
                           第三个参数代表数组本身：
       
      
                            var arrays=[1,2,3,4,5];

                              var bun=arrays.every(function(key,index,arr){
                                         return key>2;
                              })
                              console.log(bun) //false
                              
                              
         some()只要是满足其中一项就返回true 
                              		
                        var arrays=[1,2,3,4,5];

                        var bun=arrays.some(function(key,index,arr){
                          return key>2;
                        })
			
                           console.log(bun)		 //true	
                              
                              
                              
         filter()接收的回调函数，

                  其实可以有多个参数。
                   通常我们仅使用
                   第一个参数，表示Array的某个元素。
                   第二个参数表示元素下标，
                   第三个参数代表数组本身：
       
      

                           例子：过滤掉数组相同的元素

                               var array1=[10,6,2,3,4,5,6,4,5];
                                var filters=array1.filter(function(itm,index,arrs){

                                     return arrs.indexOf(itm)==index; 

                                      })

                                  console.log(filters)     输出    [10, 6, 2, 3, 4, 5]



                              把一个Array中的空字符串删掉，可以这么写：

                                  var arr = ['A', '', 'B', null, undefined, 'C', '  '];
                                  var r = arr.filter(function (s) {
                                      return s && s.trim(); // 注意：IE9以下的版本没有trim()方法
                                  });

                                   console.log(r)       输出  ['A', 'B', 'C']
                              
                              可见用filter()这个高阶函数，关键在于正确实现一个“筛选”函数。


                             例如，在一个Array中，删掉偶数，只保留奇数，可以这么写：

                                  var arr = [1, 2, 4, 5, 6, 9, 10, 15];
                                  var r = arr.filter(function (x) {
                                      return x % 2 !== 0;
                                  });
                                  r; // [1, 5, 9, 15]
                                  
                                  
                                  
                                  
           forEach()循环    
           
           
                         
                                 var arrays=[1,2,3,4,5];

                                    arrays.forEach(function(key,index,arr){
                                           console.log(key)
                                    })           // 1 2 3 4 5
                                    
                                    
                                    
                                    
     map()在原来的数组基础上，返回一个新的数组


                  var arrays=[1,2,3,4,5];

                  var bun=arrays.map(function(key,index,arr){
                    return key*2;
                  })
                         console.log(bun)  	 // [2, 4, 6, 8, 10]




     两个归并数组的方法reduce()与reduceRight()这两个方法都会迭代数组的所有项，然后构建一个最终返回的值

                   reduce()方法从数组的第一项开始，琢个遍历到最后
                   reduceRight()则从数组的最后一项开始向前遍历到第一项
                      第一个参数：前一个值  
                      第二个参数：当前值  
                      第三个参数：索引   
                      第四个参数：代表数组本身(数组对象)

                     var arrays=[1,2,3,4,5];

                      var bun=arrays.reduce(function(prev,key,index,arr){
                        return prev+key;
                      })
                                       console.log(bun)  //15



                                       var arrays=[1,2,3,4,5];

                      var bun=arrays.reduceRight(function(prev,key,index,arr){
                        return prev+key;
                      })
                       console.log(bun)  //15	





