# catched-error-message

`npm i catched-error-message`

## Why

Because you would like to run the code as below:

```typescript
try {
  throw new Error("some crazy stuff");
} catch (error) {
  doSomethingWithErrorMessage({ message: error.message });
}
```

But TypeScript defaults the error type to `unknown`. And this is correct since you can throw literally anything:

```typescript
throw 'message'
throw 123
throw {but: 'why?'}
throw null
throw undefined
...
```

## Solution

This little package is a solution to this problem. Just use it as below:

```typescript
try {
  throw new Error("some crazy stuff");
} catch (error) {
  doSomethingWithErrorMessage({ message: getErrorMessage(error) });
}
```

And here you go. You get your message, and there is no TS error.

### Package name
I know it should be caught, catched isn't a word. Oh well.
