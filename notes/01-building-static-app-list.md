## Building Static App: Friend List

as usual render list using map and props data to target component

```jsx
function FriendList() {
  const friends = initialFriends;

  return (
    <ul>
      {friends.map((friend) => (
        <Friend key={friend.id} friend={friend} />
      ))}
    </ul>
  );
}
```

[Next: Form](./02-building-static-app-form.md)
