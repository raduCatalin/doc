#Javascript

**Object** 

* **[Track 1]** 
* **[Track 2]** 
```
let obj = { firstName: "John"};
```

* **add new parameter**
```
obj.lastName = "Anderson"
console.log(obj);
>{firstName: "John", lastName: "Anderson"}

obj.sex = obj.sex || "M";
>"M"
console.log(obj);
{firstName: "John", lastName: "Anderson", age: 35, sex: "M"}

obj["age"] = 35;
>35
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35}

obj1 = { ...obj, ...{city: "Paris"} }
console.log(obj);
{firstName: "John", lastName: "Anderson", age: 35, sex: "M", city: "Paris"}
```

* **add new parameter (if)**
```
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris"}

let code = null;

obj = { 
  ...obj, 
  ...(code && {zipCode: code}) 
}
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris"}

code = 0123;

obj = { 
  ...obj, 
  ...(code && {zipCode: code}) 
}
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris", zipCode: 0123}

```

* **delete a parameter**
```
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris", zipCode: 0123}

delete obj.zipCode;
>true
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris"}


const { age, ...objWithoutAge} = obj;
console.log(objWithoutAge);
>{firstName: "John", lastName: "Anderson", city: "Paris"}
```

* **get in object (Getter)**
```
let item = { x:2, y:3, get z(){ return this.x +this.y}};
console.log(item);
>{x: 2, y: 3}
item.z
>5

```

```
const input = "951484596541141557316984781494999179677191938727971366274357874252166721759"
const circularInput = `${input}${input.charAt(0)}`
```

const obj2 = {
  owner: {
    path: '/',
    account: {
      get path() {
        return obj2.owner.path + 'account/';
      },
      pack: {
        get path() {
          return obj2.owner.account.path + 'pack/';
        },

