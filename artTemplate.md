artTemplate JS模板引擎 嵌套循环详解
----------------------------------------
#####先看下官方给出的使用方式#####

#####渲染模板#####
	var data = {
		title: '标签',
		list: ['文艺', '博客', '摄影', '民谣', '旅行', '吉他', '电影']
	}；
	var html = template('test', data);
	document.getElementById('content').innerHTML = html;
#####循环语句#####
	<script id='test' type='text/html'>
		<h1>{{title}}</h1>
		<ul>
			{each list as value i}
				<li>索引{{i+1}}：{{value}}</li>
			{{/each}}
		</ul>
	</script>

>关于嵌套循环-----个人理解
>>嵌套循环的数据格式应该是 
>>
	对象：{
		其他数据：'我是其他数据',
		要循环的数据：{
			数组:[
				{对象1},
				{对象2}，
				.............
			]
		}
	};

>这里给出一个artTemplate嵌套循环的例子(原文链接[戳这里](http://www.daxueit.com/article/8664.html "artTemplate子模板include"))
>>①
>>
	<script type='text/html' id='temp1'>
	{{each list}}
		<div>
			<h2>{{$value.title}}</h2>
			{{include 'temp2' $value.a}}
		</div>
	{{/each}}
	</script>
	<script type='text/html' id='temp2'>
		<div>
			<ul>
				{{each contents}}
					<li>{{$value.content}}</li>
				{{/each}}
			</ul>	
		</div>
	</script>
	<script type='text/javascript'>
		$(function(){
			var data = {
				list:[
					{
		                        title:"这是一个测试标题1",
		                        a:{
		                            contents:[
		                                {"content":"这是一段内容1"},
		                                {"content":"这是一段内容1"},
		                                {"content":"这是一段内容1"}
		                            ]
		                        }
		                  },
		                  {
		                        title:"这是一个测试标题2",
		                        a:{
		                            contents:[
		                                {"content":"这是一段内容2"},
		                                {"content":"这是一段内容2"},
		                                {"content":"这是一段内容2"}
		                            ]
		                        }
		                  }
				]
			};
		var html = template('temp1', data);
          	$("#main").html(html);
		})
	</script>

>>②
>>
	<script type="text/html" id="temp2">
            <div>
                <ul>
                {{each}}
                      <li>{{$index+1}} / {{$value.image}}</li>
                {{/each}}               
                </ul>
            </div>
        </script>   
        <script type="text/html" id="temp1">
        {{each list}}
            <div>
                <h2>{{$value.title}}</h2>
                {{include 'temp2' $value.images}}
            </div>
        {{/each}}
        </script>
        <script type="text/javascript">
            $(function(){
                  var data = {
                      list:[
                          {
                                title:"这是一个测试标题1",
                                contents:[
                                    {"content":"这是一段内容11"},
                                    {"content":"这是一段内容12"},
                                    {"content":"这是一段内容13"}
                                ],
                                images:[
                                    {"image":"这是一张图片11"},
                                    {"image":"这是一张图片12"},
                                    {"image":"这是一张图片13"}
                                ]
                          },
                          {
                                title:"这是一个测试标题2",
                                contents:[
                                    {"content":"这是一段内容21"},
                                    {"content":"这是一段内容22"},
                                    {"content":"这是一段内容23"}
                                ],
                                images:[
                                    {"image":"这是一张图片21"},
                                    {"image":"这是一张图片22"},
                                    {"image":"这是一张图片23"}
                                ]
                          }
                      ]
                  };
                  var html = template('temp1', data);
                  $("#main").html(html);
            });
        </script>	
	
***	
待完善
***

artTemplate官方文档   [查看](https://github.com/aui/artTemplate "性能卓越的 js 模板引擎")