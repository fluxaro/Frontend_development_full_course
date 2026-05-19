# Notes — Data Types: String, Number, Boolean

## typeof Quick Reference

```javascript
typeof 'hello'    // 'string'
typeof 42         // 'number'
typeof true       // 'boolean'
typeof undefined  // 'undefined'
typeof null       // 'object' ← JS bug
typeof {}         // 'object'
typeof []         // 'object'
```

## String Methods

```javascript
str.length
str.toUpperCase() / str.toLowerCase()
str.trim() / str.trimStart() / str.trimEnd()
str.includes('x')
str.startsWith('x') / str.endsWith('x')
str.indexOf('x')
str.slice(start, end)
str.split(separator)
str.replace('old', 'new')
str.replaceAll('old', 'new')
str.padStart(n, '0') / str.padEnd(n, '0')
str.repeat(n)
```

## Number Methods

```javascript
num.toFixed(2)          // '3.14'
num.toString()          // '42'
Number.isInteger(n)     // true/false
Number.isNaN(n)         // true/false
Number.isFinite(n)      // true/false
parseInt('42px')        // 42
parseFloat('3.14abc')   // 3.14
```

## Math Object

```javascript
Math.round(4.5)   // 5
Math.floor(4.9)   // 4
Math.ceil(4.1)    // 5
Math.abs(-5)      // 5
Math.max(1,2,3)   // 3
Math.min(1,2,3)   // 1
Math.random()     // 0–0.999
Math.sqrt(16)     // 4
Math.pow(2, 8)    // 256
```

## Falsy Values (only 6)

```javascript
false  0  ''  null  undefined  NaN
```

## Common Mistakes

- `NaN !== NaN` — use `Number.isNaN()`
- `0.1 + 0.2 !== 0.3` — floating point precision
- `typeof null === 'object'` — JS historical bug
- `'0'` is truthy, `0` is falsy
