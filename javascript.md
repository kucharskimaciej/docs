## 1.

```javascript
console.log('a');
setTimeout(() => console.log('b'), 1000);
setTimeout(() => console.log('c'), 0);
console.log('d');
```
## 2.
```javascript
for(var i = 0; i < N; i++) {
  setTimeout(function() {
    console.log(i);
  }, i * 1000);
}
```

## 3.

```javascript
const obj = {
    bar: 12,
    foo() {
        setTimeout(function() {
            console.log(this.bar)
        })
    }
}
```

## 4.

```javascript
request(URL)
    .then(() => { ...callback1 })
    .catch(() => { ...callback2 })
    .then(() => { ...callback3 })
```

## 5.
```javascript
request(URL_1)
    .then(response1 => {
        return request(URL_2)
            .then(response2 => response2)
            .catch(() => response1)
            .then(value => console.log(value))
    })
    .catch(err => {
        console.error(err)
        return request(URL_3);
    })
    .then(response => { ...callback });
```

## 6.
```javascript
async function fetchFiles() {
  const file1 = await request(URL_1);
  const file2 = await request(URL_2);
  const file3 = await request(URL_3);
}
```

## 6a.
```javascript
async function fetchFiles(URLS) {
  // ???
}
```
