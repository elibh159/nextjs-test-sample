This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## setup test 
1- install ts-jest :
`npm install --save-dev jest typescript ts-jest @types/jest`
then config ts-jest : `npx ts-jest config:init`

2- install React Testing Library, builds on top of DOM Testing Library by adding APIs for working with React components.
`npm install --save-dev @testing-library/react @testing-library/dom  @testing-library/jest-dom @testing-library/user-event`

3- create tsconfig.jest.json

`{
    "expands": "./tsconfig.json",
    "compilerOptions": {
        "jsx": "react-jsx"
    }
}`

4- change jest config =>go to site ts-jest => doc => option => add transform in jest.config.js

`transform: {
    '^.+\\.tsx?$': [
      'ts-jest',
      {
        tsconfig: 'tsconfig.test.json',
      },
    ],
  },`

  5- search `setupFilesAfterEnv` in google and find sintax in site `jestjs.io` 
  add `setupFilesAfterEnv: ['<rootDir>/setup-jest.ts'],` to `jest.config.js` 
  create new file in src , called `setup-jest.ts` and import `'@testing-library/jest-dom'` there.

  now render test should be passed.