```
export type Person = User | Admin;
```

```
if ("role" in person) {
    additionalInformation = person.role;
  } else {
    additionalInformation = person.occupation;
  }
```

## The standard fix: type predicates

You tell TypeScript what the function proves by using `person is Admin` and `person is User`.
```
export function isAdmin(person: Person): person is Admin {
  return person.type === 'admin';
}

export function isUser(person: Person): person is User {
  return person.type === 'user';
}
```
