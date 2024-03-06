<h3 align="center">API Polls</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()

</div>

---

<p align="center">A polls API where each vote is recorded and returned in real-time to the user using WebSockets.
    <br> 
</p>

## 📝 Index

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Built Using](#built_using)
- [Authors](#authors)

## 🧐 About <a name = "about"></a>

I created this API with the purpose of learning the use of WebSockets for real-time information exchange. It was a very interesting project and highly beneficial for personal growth, where I was able to grasp the usage well and learned a new pattern, which is the Pub/Sub pattern.

## 🏁 Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Requirements

Before you begin, you'll need to have the following tools installed on your machine: [Git](https://git-scm.com), [Node.js](https://nodejs.org/en/), [Docker](https://www.docker.com/). 

### Installing

```bash
# Clone this repository
$ git clone <https://github.com/geraldofrz/API-Polls>

# Access the project folder in the terminal/cmd.
$ cd polls

# Install dependencies
$ npm install

# Setup PostgreSQL and Redis 
$ docker compose up -d

# Copy .env.example
$  file cp .env.example .env

# Run application
$ npm run dev

# Test it (i tested it whit insomnia)
```



## 🎈 Usage <a name="usage"></a>

### POST /polls
Create a new poll.

### Request Body
```
{
  "title": "Qual a melhor linguagem de programação?",
  "options": [
    "JavaScript",
    "Java",
    "PHP",
    "C#"
  ]
}
```
### Response body
```
{
  "pollId": "142fac23-2cca-19a3-eed1-aa10b2dc99d0"
}
```

## POST /polls/:pollId/votes
Add a vote to specific poll.

### Request Body
```
{
  "pollOptionId": "11dda9ef-23ad-22d3-ba9f-12b73310de18"
}
```

## WebSockets
### ws /polls/:pollId/results
```
{
  "pollOptionId": "ac4821dc-1b37-2398-2213-109cbfa12299",
  "votes": 2
}
```

## ⛏️ Built Using <a name = "built_using"></a>

- [PostgreeSQL](https://www.postgresql.org/) - Database
- [Fastify](https://fastify.dev/) - Server Framework
- [NodeJs](https://nodejs.org/en/) - Server Environment

## ✍️ Authors <a name = "authors"></a>

- [@geraldofrz](https://github.com/geraldofrz) 



