keybindings.json# Interfaces

### Interface with many methods
> Using unique interface to many methods

```tsx 
interface UserData {
  id: string
  name: string
  email: string
  password: string
  created_at: Date
}

type ListUserData = Omit<UserData, 'password'>
type CreateUserArgs = Pick<UserData, 'name' | 'email' | 'password'>
type CreateUserAdminArgs = Pick<UserData, 'name' | 'email' | 'password'> & {
	code_admin: string
}
type UpdateUserArgs = Partial<Pick<UserData, 'name' | 'email' | 'password'>>

export type { ListUserData, CreateUserArgs, CreateUserAdminArgs, UpdateUserArgs }
```

### Adapt data type
> If receive data from API and need adapt data type to custom type

```tsx
interface AccountMongoData {
  _id: string
  name: string
  age: number
}

const accountMongo: AccountMongoData = {
  _id: 'as76da67sd5as7d7',
  name: 'Leandro Cruz',
  age: 25,
}

type AccountData = Omit<AccountMongoData, '_id'> & {
  id: AccountMongoData['_id']
}

function transformAccountData(accountMongoData: AccountMongoData): AccountData {
  const { _id, ...rest } = accountMongoData

  return { id: _id, ...rest }
}

const accountApi = transformAccountData(accountMongo)

console.log(accountApi)
```

### Using type to validate function
> Using type to validate function

```tsx
function multiplyNumbers(x: unknown): number | null {
  if (typeof x === 'number') return x * x

  return null
}

const result = multiplyNumbers(2)

if (typeof result === 'number') {
  console.log(result)
} else {
  console.log('Invalid calculation')
}
```

### Literal types
> Using literal types

```tsx
type Roles = 'Client' | 'Employer' | 'Admin'

function selectRole(role: Roles): string {
  return role
}

console.log(selectRole('Employer'))
```



### Type guard
> Using type guard

```tsx
type Person = {
  name: string
  enabled: boolean
}

type Animal = {
  breed: string
  size: 'small' | 'medium' | 'large'
}

type PersonOrAnimal = Person | Animal

function showPersonOrAnimal(obj: PersonOrAnimal): PersonOrAnimal | null {
  if ('name' in obj && 'enabled' in obj) {
    return {
      name: obj.name,
      enabled: obj.enabled,
    }
  } else if ('breed' in obj && 'size' in obj) {
    return {
      breed: obj.breed,
      size: obj.size,
    }
  }

  return null
}

console.log(
  showPersonOrAnimal({
    name: 'Leh',
    enabled: true,
    breed: 'Pinscher',
    size: 'large',
  }),
)
```

### Pick and Partial
> Using Pick and Partial

```tsx
interface User {
	id: string
	name: string
	password: string
	gender: string
	created_at: string
}

export type UserCreate = Pick<User, 'name' | 'password'> & Partial<Pick<User, 'gender'>>
```
