####JS构造函数与原型####
文章转载于IT农夫的博客[戳我看原文](http://blog.csdn.net/kkdelta/article/details/8456879 "JS构造函数与原型")

>JavaScript 中定义“类”的时候可以通过构造函数和原型的方式来实现，他们之间的区别和利弊？
>>首先来看一个通过构造函数来实现类定义的例子：
>
	function Car(color,model.driver){
		this.color = color;
		this.model = model;
		this.drivers = drivers;
		this.blar = function(){
			alert("I am a car :"+model+"in"+color+"."+drivers+"can drive me");
		}
	}
	var car 1 = new Car("red","BMW",['Mike','Kevin']);
	car1.blar();
>>在上面的例子中，每一个实例中，函数blar都会拷贝到实例中，弊端就是浪费内存。在来看一个通过利用prototype来定义类的例子：
>
	function Drivers(){
		var names = "";
		this.addDriver = function(name){
			names = name+" "+name;
		}
		this.toString = function(){
			return names;
		}
	}
	function Car(){}
	Car.prototype.color = "red";
	Car.prototype.model = "BMW";
	Car.protytype.drivers = newDrivers();
	Car.prototype.blar = function(){
		alert("I am car:"+this.model+"in"+this.color+"."+this.drivers+"can drivers me");
	};
	var car1 = new Car();
	car1.color = "Blue";
	car1.drivers.addDriver("Mike");
	car1.drivers.addDriver("Kevin");
	car1.drivers.addDriver("Liuos");
	car1.blar();
	var car2 = new Car();
	car2.blar();
>prototype定义的方式，函数不会拷贝到每一个实例中，所有的实例共享prototype中的定义，节省了内存。但是属性如果是对象的话，所有实例也是共享同一个对象，如上例中的drivers使用自定义对象或者数组的时候，如果其中每一个实例改变了其中的值，所有的实例的值都会被改变。因为所有的实例属性指向的都是同一个对象的引用，如果上面的例子中

>	
	car2.drivers = ['lili','yuyu'];
来改变实例car2的属性内容，相对于car2.drivers指向了另一个对象（这个时候car2有一个实例属性，有一个prototype属性都是drivers）。

>JavaScript是一种动态语言，实例创建之后可以动态添加属性和方法，在“构造函数”的定义之外也可以添加属性和方法。其实，下面例子中的sayHi本身也是一个全局的Function的实例。
>
	var obj  = {};
	obj.prop = "value";
	obj.test = function(){
		alert("test function:"+this.prop);
	}
	obj.test();
	function sayHi(){
		alert("Hi");
	}
	sayHi.sayHello = function(){
		alert("hello");
	}
	sayHi.sayHello();
> 注意如果想让添加的属性或者方法能够实例使用，要使用prototype添加，下面的例子说明了这一点：
> 
	function sayHi(){
		alert("hi");
	}
	sayHi.sayHello = function(){
		alert("hello");
	};
	sayHi.sayHello();
	var osayHi = new sayHi();
	osayHi.sayHello();
	//TypeError:osayHi.sayHello is not a function
>因为不是通过在prototype中已这样的方式添加的（sayHi.prototype.sayHello），实例是不能访问sayHello方法的，只能通过sayHi.sayHello(类似静态方法)的方式访问。同样如果添加的时候是通过prototype方式，则不能用静态访问；
>
	function sayHi(){
		alert("hi");
	}
	sayHi.prototype.sayHello = function(){
		alert("hello");
	};
	var osayHi - new sayHi();
	osayHi.sayHello();
	sayHi.sayHello();
	//TypeError:sayHi.sayHello is not a function