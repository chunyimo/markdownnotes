# History Key Points
## 三种环境的兼容性
- Browser history
- Hash history
- Memory histry

## 底层的简单原理
使用history.listen 去监听history.location 和history.action

## API
- 改变location：
>- push
>- replace
>- go
>- back
>- forward
- 组织location改变
> block

## Reference
### Action
> Action 提供了描述location改变的三种状态，分别是Action.Pop, Action.Push, Action.Replace
### Listen
> history.listen(listener:Listener)
```ts
interface Listener<S extends State = State> {
  (update: Update<S>): void;
}

interface Update<S extends State = State> {
  action: Action;
  location: Location<S>;
}
```

### Loaction
```ts
interface Location<S extends State = State> {
  pathname: string;
  search: string;
  hash: string;
  state: S;
  key: string;
}
```