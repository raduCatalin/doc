# Javascript

**Object** 

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

let module = {
  x: 81,
  getX: function() { return this.x; }
};
module.getX();
>81

const myObj = {
  owner: {
    path: '/',
    account: {
      get path() {
        return myObj.owner.path + 'account/';
      },
      pack: {
        get path() {
          return myObj.owner.account.path + 'pack/';
        }
      }
    }
  }
};

myObj.owner.path
>"/"

myObj.owner.account.path
>"/account/"

myObj.owner.account.pack.path
>"/account/pack/"
```


**Array** 
* **Remove duplicate items**
```
const myFunction = arr => [...new Set(arr)];
myFunction([12, 163, 15, 15, 163, 100, 2, 8]);

>[12, 163, 15, 100, 2, 8]
```

**Conditionals**
```
const obj = {a: 1, b: 2};
let myValue;

myValue = obj.d ? obj.d : null;

//can be write

myValue = (obj.a || null);
```



**General JS** 

* typeof : a JavaScript unary operator used to  return a string that represents the primitive type of a variable,  don’t forget that typeof null will return “object”, and for the majority of object types (Array, Date, and others) will return also “object”.
* constructor : is a property of the internal prototype property, which could be overridden by code.
* instanceof : is another JavaScript operator that check in all the prototypes chain the constructor it returns true if it’s found and false if not.


* var arr = ["a", "b", "c"];
* typeof arr;   // return "object" 
* arr  instanceof Array // true
* arr.constructor();  //[]


**bind()**
* bind() crée une nouvelle fonction
this.x = 9; // en dehors de tout contexte,
            // pour un navigateur, this est
            // l'objet window
var module = {
  x: 81,
  getX: function() { return this.x; }
};

module.getX(); // 81

var getX = module.getX;
getX(); // 9, car ici, this fait référence à l'objet global

// On crée une nouvelle fonction à laquelle on lie module en
// tant que 'this'
var boundGetX = getX.bind(module);
boundGetX(); // 81





**Difference between var, let and const**

* LET 
- la portée est limité à celle du bloc courant.
- il n’est pas obligatoire de déclarer une variable avec sa valeur initiale
- let maVar;

* CONST 
- La portée de const est celle du bloc, comme la déclaration let.
- a besoin d’être déclaré avec une valeur initiale.
- const CONFIG = 'maConfig';

* VAR
- la portée de la variable est celle du contexte dans lequel elle est déclarée (ex: contexte d'une fonction).
- il n’est pas obligatoire de déclarer une variable avec sa valeur initiale
- var maVar;

**difference between "" and ''**

**fonction generatrice**
```
const input = "951484596541141557316984781494999179677191938727971366274357874252166721759"
const circularInput = `${input}${input.charAt(0)}`
```
