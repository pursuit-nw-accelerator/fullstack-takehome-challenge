[![Pursuit Logo](https://avatars1.githubusercontent.com/u/5825944?s=200&v=4)](https://pursuit.org)

# Raffle-Takehome-Coding-Challenge

Coding challenge where you build a Raffle App including a RestAPI and connected Web Client (React)

## Getting Started

1. Create separate GitHub repos for your **front end** and **back end**. You must submit **two separate repos** (not one).
2. Create a new Node + Express app for your API
3. Create a front end client using React.
   - You may use `create-react-app` or any other starter app
4. Complete all Technical Requirements listed below
   a. Create an API with all routes listed below (this will require database tables, the database structure is up to you)
   b. Create a Front-end that allows the user to view & create Raffles, as well as, select winners 
5. Each repo should have a README with complete instructions on how to set up and run the application locally. **Make sure your instructions work!**

## Technical Requirements

Create a client for a Raffle application. Users are able to:

- Create raffles
- List all raffles
- Add participants users to raffles
- Draw a winner from a raffle, etc.

**Notes**:

- You may use any 3rd-party libraries or packages for functionality or styling.
  - We recommend you use something like Bootstrap or Material UI or others to style you app.
  - Your app does not have to look fancy, but it must look **finished**.

### API

Use the details and endpoints of the API below to guide the development of your API. This API should accept and return JSON payloads.
   - For `PUT` and `POST` endpoints, an example **request** body is given.
   - The server response should have a top-level key of `data` (for 200s) and `error` (for non-200s)

Follow best practices for validation and error handling.

| Method | Endpoint                        | Description                                                | Example JSON Request Body Payload                                                                              |
| ------ | ------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| `GET`  | `/`                             | Health check                                               | n/a |
| `GET`  | `/api/raffles`                  | List all raffles                                           | n/a                                                                                                    |
| `POST` | `/api/raffles`                  | Create a raffle                                            | `{ "name": "My first Raffle", "secret_token": "s3CrE7" }`                                              |
| `GET`  | `/api/raffles/:id`              | Retrieve a raffle by id                                    | n/a                                                                                                    |
| `GET`  | `/api/raffles/:id/participants` | Retrieve all participants of a raffle                      | n/a                                                                                                    |
| `POST` | `/api/raffles/:id/participants` | Sign up a participant for a raffle                         | `{ "firstname": "Jane", "lastname": "Doe", "email": "jdoe@email.com", "phone": "+1 (917) 555-1234", }` |
| `PUT`  | `/api/raffles/:id/winner`       | Pick a winner from the participants at random for a raffle | `{ "secret_token": "s3CrE7" }`                                                                         |
| `GET`  | `/api/raffles/:id/winner`       | Retrieve the winner of a raffle                            |                                                                                                        |

#### Notes

- A `secret_token` must be provided when creating a raffle. This token can be any random string and will be used when picking a winner for the raffle. Only if the creation token matches the one in the PUT request to pick a winner the raffle will be performed and a winner will be awarded.
- When adding a participant to a raffle all fields are required but `phone`

### Wireframes

Your application doesn't have to look exactly as the wireframes below, however it should have all the main components, accomplish all the functionality and be visually pleasing.

- Web Wireframes can be found [here](./Web-Raffle-App-Wireframes.pdf)

### App Pages/Views

As a guide for your work, you may use the wireframes above and follow the directions below to create your Front-end.

#### Home `/`

Display a form to add a new raffle with name and token fields and a submit button. Show a success message upon successful raffle creation and an error message otherwise.

Should also display a list of all raffles and when you click in one of the raffles of the list it should take the user to that raffle's page/view.

#### Single Raffle `/raffles/:id`

Displays a nav bar or navigation menu that would take the user to **All Raffles**, **Participants** and **Pick Winner** pages/views.

Below the navbar display a form to add a new participant to the Raffle. The form must include First Name, Last Name, Email and Phone inputs. The phone input should be optional and all others required. Include two buttons one to submit and another to reset the form.

#### Raffle Participants `/raffles/:id/participants`

Display the total number of participants and a list of all users and their information.

#### Pick Winner `/raffles/:id/winner`

Displays a form where a user (the raffle admin) can input their secret token and pick a winner at random for the raffle. If a winner has already been picked this page/view should display a card with the user information and a celebratory image and never show the form again.

## Submission Guidelines

- Submit the links to your front end and back end repos [in the Takehome tab of this spreadsheet](https://docs.google.com/spreadsheets/d/12TLdRWqWCKCtn5gSEn1YgMawqseIpw4kcO6EBG_9DWo/edit?usp=sharing)
- You will have two weeks for this challenge.
- You must submit your solution no later than **Sunday, April 7, 11:59 pm**
