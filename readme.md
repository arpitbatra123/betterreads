# Betterreads

Goodreads has a bad API, so I had to build my own abstraction on top of it.

## What does this API do?

It fetches the data of books you've read and reviewed on goodreads and reformats it into JSON.

## How to use this API?

- Read and review some books on goodreads. 🤷
- Get a goodreads api key from [here](https://www.goodreads.com/api/keys).
- Put that api key into an `.env` file in the root of this project like this:

```
goodreads_key=<your-key-here>
```

- Install project's dependencies by running `npm i`
- Start the server by running `npx now dev`
- Send a `GET` request to `http://localhost:3000/api`
- You'll get something like this as the response:

```json
{
    "data": [
        {
            "book": {
                "title": "The Google Story: Inside the Hottest Business, Media, and Technology Success of Our Time",
                "isbn": "9780553383669"
            },
            "review": {
                "body": "The book starts out really great with the intriguing story of the utter genius that the google founders possessed and the kind of hard work they did through which they turned a wild thought to the money making machine that google today has become.Google’s keen focus for innovation and the brilliant business acumen of the founders fascinated me a lot. The chapter on how google hired a chef via a competition to help make healthy food for google employees was the one that I enjoyed a lot.The middle sections of the book turn a little boring in my opinion. The book’s ending is also abrupt and thus the book does not feel complete. An average read. ",
                "rating": "3"
            }
        },
    ]
```    

## Deploying to zeit now
- Add the goodreads api key as a secret by running `now secret add goodreads_key <your-key>`
- Deploy to zeit by running `now -e goodreads_key=@goodreads_key --prod` ( omit --prod if you want to do a test deployment)}

## Built with

- [zeit now](https://zeit.co/)
- blood, sweat and tears