# Frontend Developer Interview Preparation Guide

## JavaScript Questions

### Basic JavaScript Concepts
1. **Explain the difference between `var`, `let`, and `const`.**
2. **What is hoisting in JavaScript?**
3. **Explain the concept of closures.**
4. **What are the different data types in JavaScript?**
5. **Explain prototypal inheritance.**

### Advanced JavaScript Concepts
1. **What is the difference between `==` and `===`?**
2. **How does the `this` keyword work in JavaScript?**
3. **Explain event delegation.**
4. **What is the event loop?**
5. **Describe the concept of promises and async/await.**

### JavaScript Code Challenges
1. **Write a function to reverse a string.**

    ```javascript
    function reverseString(str) {
        return str.split('').reverse().join('');
    }
    ```

2. **Implement a debounce function.**

    ```javascript
    function debounce(func, delay) {
        let debounceTimer;
        return function() {
            const context = this;
            const args = arguments;
            clearTimeout(debounceTimer);
            debounceTimer = setTimeout(() => func.apply(context, args), delay);
        };
    }
    ```

3. **Write a function to find the common elements between two arrays.**

    ```javascript
    function findCommonElements(arr1, arr2) {
        return arr1.filter(value => arr2.includes(value));
    }
    ```

4. **Implement a function to flatten a nested array.**

    ```javascript
    function flattenArray(arr) {
        return arr.reduce((flat, toFlatten) => {
            return flat.concat(Array.isArray(toFlatten) ? flattenArray(toFlatten) : toFlatten);
        }, []);
    }
    ```

5. **Write a function to check if a string is a palindrome.**

    ```javascript
    function isPalindrome(str) {
        const reversed = str.split('').reverse().join('');
        return str === reversed;
    }
    ```

## React.js Questions

### React Basics
1. **What is React?**
2. **Explain the virtual DOM.**
3. **What are components in React?**
4. **What is JSX?**
5. **What are props and state in React?**

### React Advanced
1. **What are hooks in React? Give examples.**
2. **Explain the context API in React.**
3. **What is the difference between functional and class components?**
4. **What are higher-order components (HOCs)?**
5. **Explain the lifecycle methods of a React class component.**

### React Code Challenges
1. **Build a simple to-do list application.**
2. **Implement a counter component with increment and decrement buttons.**
3. **Create a form with validation in React.**
4. **Build a modal component that opens on a button click and closes when clicking outside the modal or on a close button.**
5. **Create a reusable dropdown component in React.**

## Redux and State Management

### Redux Basics
1. **What is Redux and why is it used?**
2. **Explain the three principles of Redux.**
3. **What are actions, reducers, and the store in Redux?**
4. **How do you connect a React component to a Redux store?**

### Advanced Redux
1. **What are middleware in Redux? Give examples.**
2. **Explain the concept of thunks in Redux.**
3. **How do you handle asynchronous actions in Redux?**
4. **What is the difference between Redux and Context API?**

### Redux Code Challenges
1. **Implement a simple counter using Redux.**
2. **Create a Redux store and connect it to a React application.**
3. **Write a Redux reducer to manage a list of items (add, remove, update).**
4. **Implement a login flow using Redux for state management.**

## REST API and Integration

### REST API Basics
1. **What is REST API?**
2. **Explain the common HTTP methods used in REST APIs (GET, POST, PUT, DELETE).**
3. **What are status codes and what do they signify?**

### Advanced REST API
1. **How do you handle authentication in REST APIs?**
2. **Explain CORS and how to handle it.**
3. **What is the difference between REST and GraphQL?**

### REST API Integration in React
1. **Write a function to fetch data from an API and display it in a React component.**

    ```javascript
    import React, { useState, useEffect } from 'react';
    import axios from 'axios';

    function FetchDataComponent() {
        const [data, setData] = useState([]);

        useEffect(() => {
            axios.get('https://api.example.com/data')
                .then(response => {
                    setData(response.data);
                })
                .catch(error => {
                    console.error('Error fetching data:', error);
                });
        }, []);

        return (
            <div>
                <h1>Data from API</h1>
                <ul>
                    {data.map(item => (
                        <li key={item.id}>{item.name}</li>
                    ))}
                </ul>
            </div>
        );
    }

    export default FetchDataComponent;
    ```

2. **Implement error handling when fetching data from an API.**
3. **Create a form in React that submits data to an API and displays the response.**

## Scenario-Based Questions
1. **How would you optimize the performance of a large React application?**
2. **Describe a challenging bug you faced in React and how you solved it.**
3. **Explain how you would implement dark mode in a React application.**
4. **How do you manage state in a large application with complex state requirements?**
5. **Describe the process you would take to migrate a class component to a functional component with hooks.**

## Managerial and Behavioral Questions
1. **Describe a project where you implemented a significant feature.**
2. **How do you handle tight deadlines and multiple tasks?**
3. **Explain a time when you had to work with a difficult team member.**
4. **How do you stay updated with the latest trends and technologies in frontend development?**
5. **What do you do when you receive negative feedback on your work?**

## Practical Coding Exercises

### To-Do List Application
1. **Create a to-do list where users can add, delete, and mark tasks as completed.**

### Counter Component
1. **Build a counter with increment, decrement, and reset functionality.**

### Form Validation
1. **Create a form with fields for name, email, and password. Implement validation for each field.**

### Modal Component
1. **Build a modal that opens on button click and closes on clicking outside or on a close button.**

### Dropdown Component
1. **Create a reusable dropdown component that can be used with different options.**
