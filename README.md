# Next.js 15 Server Component Data Race Condition

This repository demonstrates a potential race condition in Next.js 15 when using server components with `async/await` within a `useEffect` hook in a client component.  The client component may render before the asynchronous data from the server component is available, leading to incorrect or incomplete rendering.

## Problem Description

When fetching data asynchronously in a server component and using this data in a client component's `useEffect` hook, there's a risk of a race condition. The client component might mount and render before the server component's data is ready, causing stale or missing data to be displayed. This is often more visible with dynamic routes where data fetching can be slower.

## Solution

The solution involves using appropriate loading states and ensuring the client component only renders after the server component data is fully fetched and processed.  We utilize a loading state variable and conditional rendering to solve this problem. 

## Setup

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install`.
4. Run `npm run dev` to start the development server.
