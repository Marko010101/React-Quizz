# React Quiz

React Quiz is an application where users can participate in a quiz consisting of 15 questions within a set time frame. Each question carries a specific number of points, which are calculated based on the correctness of the answers. At the end of the quiz, users can view their total points and the percentage earned out of the total points available.

## How the Project Works

The project utilizes the `useReducer` hook to manage state. Here's an outline of its functionality:

- **Data Handling**: Data is fetched using JSON-formatted objects stored within the project. This data is retrieved by setting up a local server using JSON Server and fetching it within the project. Error handling is in place for cases where data retrieval fails.

- **Quiz Interaction**: Once the data is successfully received, the quiz becomes ready to start. Users can then progress through the quiz, one question at a time. The progress bar indicates the current question number out of 15, along with the points earned from correct answers.

- **Question Rendering**: Each question is displayed sequentially, with the number of points varying based on the question's difficulty. Conditional rendering ensures that the next question button is only available after answering the current question.

- **Answer Handling**: Upon selecting an answer, the chosen option is visually highlighted. The user's points are updated based on the correctness of their selection.

- **Quiz Completion**: After answering all questions, users can finish the quiz. The user's score is compared with the high score, and if applicable, the high score is updated. An emoji representing performance (e.g., 🎉 for high scores) is displayed based on the percentage of points earned.

- **Restarting**: Users have the option to restart the quiz, resetting the state to its initial values while retaining the high score.

## Component Overview

The `<Main>` component manages the main content display based on the current status of the quiz. Here's a breakdown of its functionality:

- **Loading Screen**: If the status is "loading," a loader component (`<Loader />`) is displayed to indicate that data is being fetched.

- **Error Handling**: If an error occurs during data retrieval (`status === "error"`), an error component (`<Error />`) is rendered to inform the user.

- **Start Screen**: When the status is "ready," the start screen (`<StartScreen />`) is shown, allowing users to begin the quiz by indicating the number of questions and initiating the quiz.

- **Active Quiz**: During the quiz (`status === "active"`), the main content area displays the progress bar (`<Progress />`), the current question (`<Question />`), and navigation elements (`<Footer />`) including a timer and a button to proceed to the next question.

- **Finished Quiz**: After completing all questions (`status === "finished"`), the finish screen (`<FinishScreen />`) is presented, showing the user's final score, the maximum possible points, and the high score achieved. Users also have the option to restart the quiz from this screen.

## How to Start the Project

To start the project, follow these steps:

1. Clone the repository to your local machine:

   git clone https://github.com/Marko010101/React-quizz

2. Navigate to the project directory:

   cd React-quizz

3. Install dependencies:

   npm install

4. Start the JSON server to serve the quiz data:

   npm run server

5. Open a new terminal window/tab, and start the React app:

   npm start

6. The React Quiz should now be running in your browser. You can access it at http://localhost:3000.
