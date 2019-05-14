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

obj = { ...obj, ...(null && {zipCode: 0123}) }
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris"}

obj = { ...obj, ...("toto" && {zipCode: 0123}) }
console.log(obj);
>{firstName: "John", lastName: "Anderson", age: 35, city: "Paris", zipCode: 0123}





toto = (start, end, setClear) => {
  this.setState(({ event }) => ({
    event: {
      ...event,
      ...(start && { highlight_begin_at: start }),
      ...(end && { highlight_end_at: end }),
      ...(setClear && { highlight_begin_at: null, highlight_end_at: null })
    }
  }));
};
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
      
      },
      invitation: {
        get path() {
          return obj2.owner.account.path + 'invitations/';
        },
   
      },
      users: {
        get path() {
          return obj2.owner.account.path + 'users/';
        },
        single: {
          get path() {
            return obj2.owner.account.users.path + ':id/';
          },
        }
      }
    }
