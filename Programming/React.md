---
notion-id: 2f4b5e76-7773-80e1-814c-c386f5f8bd4a
---
React: 

- JSX: 
- HTML class = CLASSNAME
- Access from a parent: statel ives 
- Immutable state: Can add properties or increase array

### Interval

![[image 13.png]]

### Props

React Fragment

### Children

Passing children

```javascript
function Card({ children }) {
  return <div className="card">{children}</div>
}

function App() {
  return (
    <Card>
      <h2>Hello</h2>
      <p>This is inside the card</p>
    </Card>
  )
}
```

### Virtual DOM

Change the virtual DOM, “Reconciliates” with the DOM with all the diffs.

Reason for the key modifier

### State shenanigans

```javascript
setCount(count + 1);
```

- Accessing state from Parent to Child: state must live in parent

```javascript
function Parent() {
  const [value, setValue] = React.useState("");

  return <Child value={value} setValue={setValue} />;
}

function Child({ value, setValue }) {
  return (
    <input
      value={value}
      onChange={e => setValue(e.target.value)}
    />
  );
}
```

- Notifying Parent: Callback

```javascript
function Parent() {
  const doSomething = () => console.log("Parent logic");

  return <Child action={doSomething} />;
}

function Child({ action }) {
  return <button onClick={action}>Run</button>;
}

```

### Purity

Same input = same output

Components should only return JSX and not change something that existed before rendering



![[image 14.png]]