opefully this can help someone. I had a fundamental misunderstanding of the difference between subjects and observers. See here.

I solved it by creating an observer instead of a subject within the getSomething function.

getSomething(): Observable<MyObject[]> {
  var result: Observable<MyObject[]>;
  this.callApi('hello-world').subscribe(data => {
      console.log('hello-world data: ', data);
      result = of(this._mapToMyObjectArray(data));
  });
  return result;
}
