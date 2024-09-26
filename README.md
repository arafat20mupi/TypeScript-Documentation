# TypeScript-Documentation

TypeScript এর 30টি মূল বৈশিষ্ট্য এবং সুবিধা নিচে উল্লেখ করা হলো:

### TypeScript এর মূল বৈশিষ্ট্য

1. **স্ট্যাটিক টাইপিং**: TypeScript স্ট্যাটিক টাইপিং সাপোর্ট করে, যা কোড লেখার সময় টাইপ ত্রুটি ধরতে সাহায্য করে।
   ```typescript
   let num: number = 10; // সঠিক টাইপ নির্ধারণ
   ```

2. **ক্লাস**: TypeScript ক্লাস ভিত্তিক প্রোগ্রামিংকে সমর্থন করে, যা অবজেক্ট ওরিয়েন্টেড পদ্ধতির সুবিধা দেয়।
   ```typescript
   class Person {
     constructor(public name: string) {}
   }
   ```

3. **ইন্টারফেস**: ইন্টারফেস ব্যবহার করে টাইপ নির্ধারণ করা যায়, যা কোডের পাঠযোগ্যতা বাড়ায়।
   ```typescript
   interface User {
     id: number;
     name: string;
   }
   ```

4. **ডেকোরেটর**: ক্লাস এবং মেথডে ডেকোরেটর ব্যবহার করা যায়, যা কোডের পুনঃব্যবহারযোগ্যতা বাড়ায়।
   ```typescript
   function Log(target: any, key: string) {
     console.log(`${key} is called`);
   }
   ```

5. **জেনেরিক্স**: জেনেরিক টাইপ সাপোর্ট করে, যা কোডের পুনঃব্যবহারযোগ্যতা বাড়ায়।
   ```typescript
   function identity<T>(arg: T): T {
     return arg;
   }
   ```

6. **নালেবল টাইপস**: নাল ও undefined এর জন্য আলাদা টাইপ নির্ধারণ করা যায়।
   ```typescript
   let value: string | null = null;
   ```

7. **টাইপ গার্ডস**: টাইপ যাচাই করতে টাইপ গার্ড ব্যবহার করা যায়।
   ```typescript
   function printId(id: string | number) {
     if (typeof id === "string") {
       console.log(`String ID: ${id}`);
     }
   }
   ```

8. **এনাম**: কোডে এনাম ব্যবহার করে নির্দিষ্ট মানের জন্য নাম দেওয়া যায়।
   ```typescript
   enum Direction {
     Up,
     Down,
     Left,
     Right
   }
   ```

9. **অবজেক্টের জন্য টাইপস**: অবজেক্ট টাইপ নির্ধারণ করা যায়, যা কোডের স্থায়িত্ব বাড়ায়।
   ```typescript
   type Point = { x: number; y: number };
   ```

10. **এপিআই ডিফিনিশন**: টাইপ সংজ্ঞায়িত করে কোডের জন্য উন্নত ডকুমেন্টেশন প্রদান করা যায়।
    ```typescript
    /**
     * Calculates sum
     * @param a - First number
     * @param b - Second number
     * @returns Sum of a and b
     */
    function sum(a: number, b: number): number {
      return a + b;
    }
    ```

11. **টপ-লেভেল অ্যাওয়েট**: অ্যাওয়েট টপ-লেভেল কোডে ব্যবহার করা যায়।
    ```typescript
    const data = await fetchData();
    ```

12. **অপশনাল প্রোপার্টিজ**: অবজেক্টে প্রোপার্টি অপশনাল নির্ধারণ করা যায়।
    ```typescript
    interface User {
      id: number;
      name: string;
      age?: number; // অপশনাল প্রোপার্টি
    }
    ```

13. **রিড-অনলি প্রোপার্টি**: অবজেক্টে রিড-অনলি প্রোপার্টি তৈরি করা যায়।
    ```typescript
    interface User {
      readonly id: number;
      name: string;
    }
    ```

14. **অ্যানোটেশনস**: কোডের উপর মন্তব্য যোগ করতে সাহায্য করে।
    ```typescript
    let username: string = "Arafat"; // ইউজারনেম
    ```

15. **মডিউল সিস্টেম**: মডিউল সিস্টেম ব্যবহার করে কোডকে সংগঠিত করা যায়।
    ```typescript
    import { User } from './User';
    ```

16. **ডিফল্ট আর্গুমেন্টস**: ফাংশনে ডিফল্ট আর্গুমেন্ট নির্ধারণ করা যায়।
    ```typescript
    function greet(name: string = "Guest") {
      console.log(`Hello, ${name}`);
    }
    ```

17. **অ্যাসিনক্রোনাস ফাংশন**: অ্যাসিনক্রোনাস ফাংশন তৈরি করা যায়।
    ```typescript
    async function fetchData() {
      const response = await fetch('url');
      return response.json();
    }
    ```

18. **টার্গেটিং**: কম্পাইলার অপশন দিয়ে ES মডিউল বা সাধারণ ফাংশন নিয়ে কাজ করা যায়।
    ```json
    {
      "compilerOptions": {
        "target": "ES6"
      }
    }
    ```

19. **ফাংশন ওভারলোডিং**: একই ফাংশনের বিভিন্ন টাইপের জন্য আলাদা সিগনেচার ব্যবহার করা যায়।
    ```typescript
    function overload(value: string): string;
    function overload(value: number): number;
    function overload(value: any): any {
      return value;
    }
    ```

20. **এশিনক্রোনাস/অবজারভেবল টাইপস**: এশিনক্রোনাস কোডের জন্য নতুন টাইপ ব্যবহার করা যায়।
    ```typescript
    type Observable<T> = {
      subscribe(callback: (value: T) => void): void;
    };
    ```

21. **প্লাগইন সাপোর্ট**: টুলিং উন্নতির জন্য প্লাগইন সাপোর্ট করে।
    ```bash
    npm install typescript --save-dev
    ```

22. **ইনফারেন্স**: টাইপ ইনফারেন্সের মাধ্যমে কোড লেখার সময় টাইপ নির্ধারণ করা হয়।
    ```typescript
    let str = "Hello"; // টাইপ স্বয়ংক্রিয়ভাবে string নির্ধারণ
    ```

23. **জাভাস্ক্রিপ্টের উপর বেসড**: JavaScript এর সমস্ত বৈশিষ্ট্য TypeScript-এ পাওয়া যায়।
    ```javascript
    let x = 5; // JavaScript কোড TypeScript-এ চলে
    ```

24. **লাইব্রেরি সমর্থন**: বড় লাইব্রেরির জন্য টাইপ ডিফিনিশন ব্যবহার করা যায়।
    ```typescript
    import * as React from 'react';
    ```

25. **অ্যালিয়াস**: টাইপ অ্যালিয়াস ব্যবহার করে কোডের গঠন তৈরি করা যায়।
    ```typescript
    type ID = string | number;
    ```

26. **উন্নত ডেবাগিং**: ডেবাগিংয়ের সময় উন্নত তথ্য প্রদান করে।
    ```typescript
    let user = { name: "Arafat", age: 25 };
    ```

27. **প্রজেক্ট কনফিগারেশন**: টিপিএস বা টাস্ক রানার ব্যবহার করে প্রজেক্ট কনফিগারেশন করা যায়।
    ```json
    {
      "include": ["src/**/*"],
      "exclude": ["node_modules"]
    }
    ```

28. **স্ট্রাকচারাল টাইপিং**: টাইপ তৈরি এবং যাচাইয়ের জন্য স্ট্রাকচারাল টাইপিং ব্যবহার করা যায়।
    ```typescript
    interface A { x: number; }
    interface B { x: number; y: number; }
    let b: B = { x: 1, y: 2 };
    let a: A = b; // OK
    ```

29. **টাইপ নির্ধারণ**: যেকোনো সময় টাইপ পরিবর্তন করা যায়।
    ```typescript
    let value: number | string;
    value = 5; // OK
    value = "Hello"; // OK
    ```

30. **দ্রুত উন্নয়ন**: টাইপ নিরাপত্তা এবং উন্নত টুলিংয়ের কারণে দ্রুত কোড উন্নয়ন সম্ভব।
    ```typescript
    function add(x: number, y: number): number {
      return x + y;
    }
    ```
