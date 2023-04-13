# Filters

```tsx
interface UserProps {
  id: number;
  name: string;
  email: string;
  createdAt: Date;
}

export default function Users() {
  const [users, setUsers] = useState<UserProps[]>([]);
  const [search, setSearch] = useState<string>("");

  useEffect(() => {
    setUsers([
      {
        id: 1,
        name: "Kevin",
        email: "kevin@email.com",
        createdAt: new Date(),
      },
      {
        id: 2,
        name: "Leandro",
        email: "leo@email.com",
        createdAt: new Date(),
      },
      {
        id: 3,
        name: "Jonathan",
        email: "jona@email.com",
        createdAt: new Date(),
      },
    ]);
  }, []);

  const usersFiltered = React.useMemo(() => {
    const lowerSearch = search.toLowerCase();

    return users.filter(
      (user) =>
        user.name.toLowerCase().includes(lowerSearch) ||
        user.email.toLowerCase().includes(lowerSearch)
    );
  }, [search, users]);

  return (
    <>
      <input
        type="text"
        id="text"
        placeholder="Search..."
        value={search}
        onChange={(e) => setSearch(e.target.value)}
      />
      <table>
        <thead>
          <tr>
            <th>NAME</th>
            <th>EMAIL</th>
            <th>CREATED AT</th>
          </tr>
        </thead>
        <tbody>
          {usersFiltered.map((user) => (
            <tr key={user.id}>
              <th>{user.name}</th>
              <th>{user.email}</th>
              <th>{user.createdAt.getFullYear()}</th>
            </tr>
          ))}
        </tbody>
      </table>
    </>
  );
}
```

### useMemo

##### useMemo is a hook that returns a memoized value. Pass a “create” function and an array of dependencies. useMemo will only recompute the memoized value when one of the dependencies has changed. This optimization helps to avoid expensive calculations on every render.

```tsx
const usersFiltered = React.useMemo(() => {
  const lowerSearch = search.toLowerCase();

  return users.filter(
    (user) =>
      user.name.toLowerCase().includes(lowerSearch) ||
      user.email.toLowerCase().includes(lowerSearch)
  );
}, [search, users]);
```
