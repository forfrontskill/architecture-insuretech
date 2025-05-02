# Объекты
```javascript
type Query {
  client(id: ID!): Client
}

type Client {
  id: ID!
  name: String
  age: Int
  documents: [Document]
  relatives: [Relative]
}

type Document {
  id: ID!
  type: String
  number: String
  issueDate: String
  expiryDate: String
}

type Relative {
  id: ID!
  relationType: String
  name: String
  age: Int
}
```

# Запросы

```
Получить клиента по ID

query GetClientById {
  client(id: "123") {
    id
    name
    age
  }
}

Получить только документы клиента

query GetClientDocuments {
  client(id: "123") {
    documents {
      id
      type
      number
      issueDate
      expiryDate
    }
  }
}

Получить только родственников клиента

query GetClientRelatives {
  client(id: "123") {
    relatives {
      id
      relationType
      name
      age
    }
  }
}

Объединённый запрос — клиент, документы и родственники

query GetFullClientInfo {
  client(id: "123") {
    id
    name
    age
    documents {
      id
      type
      number
      issueDate
      expiryDate
    }
    relatives {
      id
      relationType
      name
      age
    }
  }
}



```