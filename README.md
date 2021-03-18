# ListGo
By Tai, Tom, Crystal, Kenneth, & Al.

## ListGo is a personal media journal, where you can search for your favourite films, music, and books to add to your recommendation list.

### How we will work:
We will adopt Agile team principles as a loose guideline for our roles. Each day someone will have the opportunity to step into Scrum Master. Each member has an obligation to communicate regularly and will take on 'Vibes lead'. Tasks will be broken down to small and clear areas of ownership. We will track our tasks via ticketing and assigning fibonacci values to represent their difficulty.

### Getting help:
We have established a system for reaching out to help.

We will use code examples, google searches, and youtube tutorials to help us get to where we need to be.

When we are stuck and our team is unable to help each other we will concisely sum up our area of struggle with a well thought out question, outlining the approaches we have undertaken to efficiently reach a solution. 

We have acknowledged that approaching team members is not considered interrupting. 

### Database Diagram
![Entity Relationship Diagram](docs/erd.png)
[Liszt ERD on dbdiagram.io](https://dbdiagram.io/d/5fce9fbb9a6c525a03ba2a27)

## Git Policy
How to merge (e.g. Feature branch to front-end)
1. On feature-branch, git pull origin front-end
2. If conflicts, deal with them.
3. Commit and push if you've needed to make changes.
4. git checkout front-end
5. git merge feature-branch
6. Once that's successful, git push origin front-end

#### Feature branches
- Roughly aligns to a ticket being worked on solo, or by a pair
- Need to be code reviewed before getting merged into front-end or back-end.

#### front-end, back-end, 
Feature branches get merged into here. The idea of these branches is that if front-end code is working and needs to go to dev and main, it isn't blocked by some back-end changes that aren't working. Or vice versa

#### dev
We really don't want this one broken, but it's better here than in Main.

#### main
Only integrated, working code can go in here. Don't want it broken.

## API Routes

### `GET /api/v1/books/:userId`

Response (200):

```json
{
	"books": [
		{
			"bookApiId": "1bMXAAAAYAAJ",
			"imageUrl": "http://books.google.com/books/content?id=1bMXAAAAYAAJ..."
		}
	]
}
```
### `POST /api/v1/books/`

Adds a book to the user's list of books and returns newly updated list.

Request:


```json
{
	"userId": 1,
	"bookApiId": "1bMXAAAAYAAJ"  
}
```
Response (200):

```json
{
	"books": [
		{
			"bookApiId": "1bMXAAAAYAAJ",
			"imageUrl": "http://books.google.com/books/content?id=1bMXAAAAYAAJ..."
		}
	]
}
```
### DEL /api/v1/books

Removes a book from the user's list of books and returns newly updated list.

Request:

```json
{
	"userId": 1,
	"bookApiId": "1bMXAAAAYAAJ"  
}
```

Response (200):

```json
{
	"books": [
		{
			"bookApiId": "1bMXAAAAYAAJ",
			"imageUrl": "http://books.google.com/books/content?id=1bMXAAAAYAAJ..."
		}
	]
}
```
