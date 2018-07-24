# scan-vs-reduce-in-RxJS

A reduction means all processors get the same value while scan returns the partial operation results on each processor

Please find the below code </br>

var observable = Rx.Observable.of(1,2,3,4,5);

--reduce </br>

observable
.reduce((total, currentValue) => {
	return total + currentValue;
}, 0)
.subscribe({
	next: function(value) {
  	console.log(value);
  }
});
</br>

--console out will be </br>
15

--scan() </br>

observable
.scan((total, currentValue) => {
	return total + currentValue;
}, 0)
.subscribe({
	next: function(value) {
  	console.log(value);
  }
});
</br>

--console out will be</br>

1 </br>
3 </br>
6 </br>
10 </br>
15 </br>

