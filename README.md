# UltimateNO.1
function Parent() {
			this.name = "html";
			this.friends = ["html","html5"];
		}
		Parent.prototype.showInfo = function() {
			console.log(this.friends);
		}
		function Son(age) {
			// 属性继承
			Parent.call(this);
			this.age = age;
		}
		// 方法的继承
		for(var i in Parent.prototype) {
			Son.prototype[i] = Parent.prototype[i];
			console.log(i);
		}
		Son.prototype.showInfo = function() {
			console.log("我是" + this.friends);
		}
		var peo1 = new Son(22);
		var peo2 = new Son(33);
		peo1.friends.push("55");
		peo1.showInfo();
		peo2.showInfo();
		console.log(peo1.showInfo == peo2.showInfo);
