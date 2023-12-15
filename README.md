# catched-error-message

`npm i catched-error-message`

## Why

Because you would like to run code as below:

```typescript
try {
  throw new Error("some crazy stuff");
} catch (error) {
  doSomethingWithErrorMessage({ message: error.message });
}
```

But TypeScript defaults error type to `unknown`. And this is actually correct, since you can throw literally anything:

```typescript
throw 'messgae'
throw 123
throw {but: 'why?'}
throw null
throw undefined
...
```

## Solution

This little package is a solution for thi problem. Just use it as below:

```typescript
try {
  throw new Error("some crazy stuff");
} catch (error) {
  doSomethingWithErrorMessage({ message: getErrorMessage(error) });
}
```

And voilà, you get your message, no TS error.
