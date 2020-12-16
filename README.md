# API Documentation

## Introduction

This API allows users find information about people in the neighbourhood.
Users can:

- store people, houses and addresses
- look up a house, its address and owner
- look up people in our neighbourhood within certain age brackets and with specific household sizes

## Database schema

This database uses relational data.
![alt text](https://github.com/derejmi/API-Design/blob/master/apischema.png)

## RESTful Routes

Methods available in the API

| HTTP verb | Path          | Action                 |
| --------- | ------------- | ---------------------- |
| GET       | `/people/new` | new entry for a person |
| POST      | `/people`     | create new entry       |
| GET       | `/people/:id` | show individual entry  |

---

## **Store People**

Provide interface for storing new people.

- **URL**

  /people/new

- **Method:**

  `GET`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />

* **Error Response:**

  - **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Page doesn't exist" }`

---

## **Store People**

Store new people.

- **URL**

  /people/

- **Method:**

  `POST`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 201 <br />
    **Content:** `{ id : 1, firstName:'John' , lastName:'Smith', Age: 50, peopleInHousehold: 2 }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript
  const options = {
      method: "POST",
      body: JSON.stringify(post),
      headers: {
        "content-type": "application/json",
      },
    };

    fetch(`${domain}/posts
    `,options)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

---

## **Store Houses**

Provide interface for storing new houses.

- **URL**

  /houses/new

- **Method:**

  `GET`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />

* **Error Response:**

  - **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Page doesn't exist" }`

---

## **Store Houses**

Store new houses.

- **URL**

  /houses/

- **Method:**

  `POST`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 201 <br />
    **Content:** `{ id : 1, Address: 1 Nowhere Avenue, lastName:'Smith', Age: 50, peopleInHousehold: 2 }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript
  const options = {
      method: "POST",
      body: JSON.stringify(post),
      headers: {
        "content-type": "application/json",
      },
    };

    fetch(`${domain}/houses
    `,options)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

---

## **Store Addresses**

Provide interface for storing new address.

- **URL**

  /address/new

- **Method:**

  `GET`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />

* **Error Response:**

  - **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Page doesn't exist" }`

---

## **Store Houses**

Store new houses.

- **URL**

  /addresses/

- **Method:**

  `POST`

- **URL Params**

  None

* **Data Params**

  None

* **Success Response:**

  - **Code:** 201 <br />
    **Content:** `{ Postcode: 'N15 2XY', StreetAddress: 'Green Lanes' }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript
  const options = {
      method: "POST",
      body: JSON.stringify(post),
      headers: {
        "content-type": "application/json",
      },
    };

    fetch(`${domain}/addresses
    `,options)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

---

## **Get Houses**

Get houses.

- **URL**

  /houses/:id

- **Method:**

  `GET`

- **URL Params**

  None

  **Required:**

  `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />
    **Content:** `{ id : 1, Address: 1 Nowhere Avenue, lastName:'Smith', Age: 50, peopleInHousehold: 2 }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript


    fetch(`${domain}/${URL}
    `)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

---

## **Get the address of a house**

Get the address of a house.

- **URL**

  /houses/:id/address

- **Method:**

  `GET`

- **URL Params**

  None

  **Required:**

  `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />
    **Content:** `{ Address: 1 Nowhere Avenue, lastName:'Smith' }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript


    fetch(`${domain}/${URL}
    `)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

  ---

## **Get the owner of a house**

Get the owner of a house.

- **URL**

  /houses/:id/owner

- **Method:**

  `GET`

- **URL Params**

  None

  **Required:**

  `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />
    **Content:** `{ Owner: 'John Smith'}`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript


    fetch(`${domain}/${URL}
    `)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

---

## Look up people with certain age brackets and specific household sizes

Query example for people over 25 with a household size of over 2

- **URL**

`/people:id?minAge=25&houshold?minSize=2`

- **Method:**

  `GET`

- **URL Params**

  None

  **Required:**

  `id=[integer]`
  `minAge=[integer]`
  `household?minSize = [integer]`

* **Data Params**

  None

* **Success Response:**

  - **Code:** 200 <br />
    **Content:**`{ id : 1, firstName:'John' , lastName:'Smith', Age: 50, peopleInHousehold: 3 }`

* **Error Response:**

  - **Code:** 400 Bad Request <br />
    **Content:** `{ error : "Bad Request" }`

* **Sample Call:**

  ```javascript


    fetch(`${domain}/${URL}
    `)
    .then((r)=>r.json())
    .then((message) => {console.log(message)})

  });
  ```

  ---
