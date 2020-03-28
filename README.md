# About

> Code examples based on Alura's MongoDB course.

## Getting started with Docker

**Creating a container**

```
$ sudo docker run --name mongo-container-name -d mongo
```

**Starting a existing container**

```
$ sudo docker start mongo-container-name
```

**Acessing MongoDB CLI in a container**

```
$ sudo docker exec -it mongo-container-name bash
```

## MongoDB Statements

**createCollection**

```
$ db.createCollection('student')
```

**insert**

```
$ db.student.insert({
  name: 'John Doe',
  date_of_birth: new Date(1990, 6, 11),
  languages: [
    {
      description: 'Portuguese',
      level: 'Fluent'
    },
    {
      description: 'English',
      level: 'Intermediate'
    }
  ]
})
```

**find**

```
$ db.student.find()
```

Getting by a specific attribute:

```
$ db.student.find({ name: 'John Doe' })
```

Getting by a specific attribute in a list:

```
$ db.student.find({ 'languages.description': 'Portuguese' })
```

Getting by multiple attributes:

```
$ db.student.find({ name: 'John Doe', languages.description': 'Portuguese' })
```

Using `$or`:

```
$ db.student.find({ $or: [{ name: 'John' }, { name: 'Ana' }] })
```

Using `$in`:

```
$ db.student.find({ 'languages.level': { $in: ['Intermediate', 'Fluent'] } })
```

**remove**

```
$ db.student.remove({ '_id': ObjectId('5e7c1e0c37e168cf1dabbf16') })
```
