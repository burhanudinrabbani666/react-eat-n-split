## Selecting Friend

use method chaining if the initial state is **null** and needs to be verified in the submitted component

```jsx
const [selectedFriend, setSelectedFriend] = useState(null);

function handleSelection(friend) {
  // setSelectedFriend(friend);
  setSelectedFriend(
    (currSelected) => (currSelected?.id === friend.id ? "" : friend) // Chaining methods
  );
  setShowAddFriend(false);
}

function Friend({ friend, onSelection, selectedFriend }) {
  // Chaining
  const isSelected = selectedFriend?.id === friend.id;

  return; // ....
}
```

[Next: Creating Controlled Elements](./06-creating-controlled-elements.md)
