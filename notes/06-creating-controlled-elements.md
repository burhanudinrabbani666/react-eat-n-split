## Creating Controlled elements

```jsx
function FormSplitBill({ selectedFriend }) {
  const [bill, setBill] = useState("");
  const [paidbyUser, setPaidByUser] = useState("");
  const paidByFriend = bill ? bill - paidbyUser : "";
  const [whoIsPaying, setWhoIsPaying] = useState("user");

  return (
    <form className="form-split-bill">
      <h2>Split a bill with {selectedFriend.name} Name</h2>

      <label>💰 Bill value</label>
      <input
        type="text"
        value={bill}
        onChange={(e) => setBill(Number(e.target.value))}
      />

      <label>😄 Your Expense</label>
      <input
        type="text"
        value={paidbyUser}
        onChange={(e) =>
          setPaidByUser(
            Number(e.target.value) > bill ? paidbyUser : Number(e.target.value)
          )
        }
      />

      <label>🧑‍🤝‍🧑 {selectedFriend.name} expense</label>
      <input type="text" disabled value={paidByFriend} />

      <label>🤑 Who is Split a bill</label>
      <select
        value={whoIsPaying}
        onChange={(e) => setWhoIsPaying(e.target.value)}
      >
        <option value="user">You</option>
        <option value="friend">{selectedFriend.name}</option>
      </select>

      <Button>Split bill</Button>
    </form>
  );
}
```

[Next: Spliting Bills](./07-splitting-bills.md)
