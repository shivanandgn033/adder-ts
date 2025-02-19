```typescript
// math-adder.ts (or src/index.ts - better for a package)

/**
 * Adds two numbers.
 * @param a The first number.
 * @param b The second number.
 * @returns The sum of a and b.
 */
export function add(a: number, b: number): number {
  return a + b;
}

// ... (subtract, multiply, divide functions - same as before)
// ... (Make sure these are also exported)


// Example usage (in a separate file, e.g., test/math-adder.test.ts)
// (This would be in your test file, NOT in the main library file)
import { add, subtract, multiply, divide } from '../src/index'; // Adjust path

describe('Math Adder', () => { // Example using Jest (you can use other testing frameworks)
    it('should add two numbers', () => {
        expect(add(5, 3)).toBe(8);
    });

    // ... (tests for subtract, multiply, divide)
    it('should handle division by zero', () => {
        expect(divide(10, 0)).toBeNaN();
    });
});




// ----------------------------------------------------------------------
// Project Setup (for GitHub and npm):
// ----------------------------------------------------------------------

// 1. Initialize a Git repository:
//    git init

// 2. Create a package.json:
//    npm init -y  (or yarn init -y)

// 3. Install TypeScript and Jest (or your testing framework):
//    npm install --save-dev typescript jest @types/jest

// 4. Create tsconfig.json (as provided in the previous response - very important!)

// 5. Create a folder `src` and move `math-adder.ts` into it (renaming it `index.ts` is a common practice for the main entry point of a package).

// 6. Create the `test` folder and add a file named `math-adder.test.ts`.  Put your test code there.

// 7. Configure package.json:
//    "main": "dist/index.js", // Compiled output
//    "types": "dist/index.d.ts", // Type definitions
//    "scripts": {
//        "build": "tsc",
//        "test": "jest", // Run tests
//        "prepublishOnly": "npm run build && npm run test" // Build and test before publishing
//    },
//    "files": [ // Include only necessary files in the published package
//        "dist/**/*"
//    ],
//    "devDependencies": { // Update devDependencies
//        "typescript": "^5.0.0", // Or your version
//        "jest": "^29.0.0",  // Or your version
//        "@types/jest": "^29.0.0" // Or your version
//    }

// 8. Compile:
//    npm run build

// 9. Commit to Git:
//    git add .
//    git commit -m "Initial commit"

// 10. Create a repository on GitHub.

// 11. Push to GitHub:
//     git remote add origin <your_github_repository_url>
//     git branch -M main
//     git push -u origin main

// 12. Publish to npm (after building and testing):
//     npm publish


// .gitignore (Create this file and add):
// node_modules
// dist


// Example test (test/math-adder.test.ts):
import { add, subtract, multiply, divide } from '../src/index';

describe('Math Adder', () => {
    it('should add two numbers', () => {
        expect(add(5, 3)).toBe(8);
    });

    // ... (tests for other functions)
});

```
#### Key Changes and Explanations for GitHub and npm:

1) src Directory: It's best practice to put your source code in a src directory.
2) index.ts: The main entry point of your package should usually be src/index.ts.
3) test Directory: Put your tests in a test directory. This keeps your source code separate from your tests.
4) Jest: I've added Jest as a testing framework. You'll need to install it: npm install --save-dev jest @types/jest. Jest is very popular for testing TypeScript.
5) Test File: The example shows a basic test using Jest. Good tests are essential!
6) prepublishOnly Script: This script ensures that your code is built and tested before you publish to npm, preventing you from accidentally publishing broken code.
7) files in package.json: The files array tells npm which files to include in the published package. This keeps the package size small and prevents unnecessary files (like your tests) from being included.
8) .gitignore: This file is crucial. It tells Git which files to ignore (like node_modules and dist). Never commit your node_modules folder!
9) GitHub: The steps to create a GitHub repository and push your code are included.
10) npm Publish: The npm publish command is used to publish your package to the npm registry. You'll need an npm account.
11) Test Example: I've added a basic test example using Jest. Make sure you write thorough tests for all your functions!


#### Workflow:

1) Develop: Write your code in src/index.ts.
2) Test: Write your tests in test/math-adder.test.ts. Run the tests with npm run test.
3) Build: When you're ready to publish, run npm run build. This will compile your TypeScript code into JavaScript and put it in the dist folder.
4) Commit: Commit your changes to Git.
5) Publish: Run npm publish. This will publish the contents of the dist folder (and other files specified in files in package.json) to npm.

This complete example provides a much better structure for a professional TypeScript package, including testing and publishing.  Remember to replace the placeholder information (like your GitHub repository URL and package name) with your actual information.
