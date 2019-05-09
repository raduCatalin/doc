#titltWORKSHOP Pack Com

**Obj** text

* **[Track 1]** 
* **[Track 2]** 

**Agenda Jour 1**
* toto: tutu
```
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
