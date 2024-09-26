# TypeScript-Documentation

নিচে TypeScript-এর 50টি গুরুত্বপূর্ণ বৈশিষ্ট্য এবং তাদের সাথে সংশ্লিষ্ট কোড উদাহরণ দেয়া হলো:

### 1-10: মৌলিক বৈশিষ্ট্য

1. **স্ট্যাটিক টাইপিং**
   ```typescript
   let age: number = 25; // টাইপ নির্ধারণ
   ```

2. **টাইপ ইনফারেন্স**
   ```typescript
   let name = "John"; // TypeScript স্বয়ংক্রিয়ভাবে টাইপ নির্ধারণ করবে
   ```

3. **ইন্টারফেস**
   ```typescript
   interface User {
       id: number;
       name: string;
   }
   const user: User = { id: 1, name: "Alice" };
   ```

4. **জেনেরিক্স**
   ```typescript
   function identity<T>(arg: T): T {
       return arg;
   }
   const result = identity<number>(5);
   ```

5. **মডিউল সিস্টেম**
   ```typescript
   // utils.ts
   export function add(x: number, y: number): number {
       return x + y;
   }
   // main.ts
   import { add } from './utils';
   console.log(add(5, 3));
   ```

6. **এনামস**
   ```typescript
   enum Color {
       Red,
       Green,
       Blue
   }
   let c: Color = Color.Green;
   ```

7. **অভ্যন্তরীণ টাইপ**
   ```typescript
   let isActive: boolean = true; // প্রিমিটিভ টাইপ
   ```

8. **নাল এবং আনডিফাইন্ড**
   ```typescript
   let value: string | null = null; // নাল টাইপ সমর্থন
   ```

9. **ক্লাস**
   ```typescript
   class Person {
       name: string;
       constructor(name: string) {
           this.name = name;
       }
   }
   const person = new Person("John");
   ```

10. **সুপার ক্লাস**
    ```typescript
    class Animal {
        makeSound() {
            console.log("Animal sound");
        }
    }
    class Dog extends Animal {
        makeSound() {
            console.log("Bark");
        }
    }
    ```

### 11-20: উন্নত বৈশিষ্ট্য

11. **অপশনাল প্রোপার্টিজ**
    ```typescript
    interface User {
        id: number;
        name: string;
        age?: number; // অপশনাল প্রোপার্টি
    }
    ```

12. **রিড-অনলি প্রোপার্টি**
    ```typescript
    interface Point {
        readonly x: number;
        readonly y: number;
    }
    ```

13. **ফাংশন টাইপ**
    ```typescript
    type Greet = (name: string) => void;
    const greet: Greet = (name) => {
        console.log(`Hello, ${name}`);
    };
    ```

14. **ইউনিয়ন টাইপ**
    ```typescript
    function printId(id: number | string) {
        console.log(`Your ID is: ${id}`);
    }
    ```

15. **ইন্টারসেকশন টাইপ**
    ```typescript
    interface Admin {
        admin: boolean;
    }
    interface User {
        name: string;
    }
    type AdminUser = Admin & User;
    ```

16. **টাইপ গার্ড**
    ```typescript
    function isNumber(value: any): value is number {
        return typeof value === "number";
    }
    ```

17. **অ্যাসার্টস**
    ```typescript
    let unknownValue: any = "Hello";
    let strLength: number = (unknownValue as string).length;
    ```

18. **মেপস এবং সেটস**
    ```typescript
    let map: Map<string, number> = new Map();
    map.set("one", 1);
    ```

19. **ফাংশন ওভারলোডিং**
    ```typescript
    function combine(a: string, b: string): string;
    function combine(a: number, b: number): number;
    function combine(a: any, b: any): any {
        return a + b;
    }
    ```

20. **ডেকোরেটরস**
    ```typescript
    function log(target: any, propertyName: string, descriptor: PropertyDescriptor) {
        console.log(`${propertyName} has been called`);
    }

    class Example {
        @log
        sayHello() {
            console.log("Hello");
        }
    }
    ```

### 21-30: অন্যান্য গুরুত্বপূর্ণ বৈশিষ্ট্য

21. **এনামস**
    ```typescript
    enum Direction {
        Up,
        Down,
        Left,
        Right
    }
    ```

22. **নেস্টেড অবজেক্ট**
    ```typescript
    interface User {
        name: string;
        address: {
            street: string;
            city: string;
        };
    }
    ```

23. **স্ট্যাটিক টাইপস**
    ```typescript
    class Circle {
        static pi: number = 3.14;
        radius: number;
        constructor(radius: number) {
            this.radius = radius;
        }
    }
    ```

24. **জেনেরিক ক্লাস**
    ```typescript
    class Box<T> {
        private contents: T;
        constructor(value: T) {
            this.contents = value;
        }
        getContents(): T {
            return this.contents;
        }
    }
    ```

25. **ম্যাপ এবং ফিল্টার**
    ```typescript
    const numbers: number[] = [1, 2, 3];
    const doubled = numbers.map(n => n * 2);
    ```

26. **অ্যাসিং এবং অপেক্ষা**
    ```typescript
    async function fetchData(url: string): Promise<any> {
        const response = await fetch(url);
        return response.json();
    }
    ```

27. **ইন্টারফেসের প্রসারণ**
    ```typescript
    interface Vehicle {
        wheels: number;
    }
    interface Car extends Vehicle {
        brand: string;
    }
    ```

28. **ব্রাউজার এনভায়রনমেন্ট**
    ```typescript
    if (typeof window !== "undefined") {
        console.log("This is a browser environment");
    }
    ```

29. **ব্ল্যাকবক্স টাইপস**
    ```typescript
    type UserID = string & { readonly brand: unique symbol };
    ```

30. **প্যারামিটার ডিকনস্ট্রাকশন**
    ```typescript
    function greet({ name, age }: { name: string; age: number }) {
        console.log(`Hello, my name is ${name} and I am ${age} years old.`);
    }
    ```

### 31-40: উন্নত টেকনিক

31. **এনভায়রনমেন্ট ভেরিয়েবলস**
    ```typescript
    const apiKey: string = process.env.API_KEY as string;
    ```

32. **ইম্পোর্ট এবং এক্সপোর্ট**
    ```typescript
    export const PI = 3.14;
    import { PI } from './math';
    ```

33. **টাইপ শেথিং**
    ```typescript
    interface User {
        name: string;
    }
    type Admin = User & { admin: true };
    ```

34. **থার্ড-পার্টি লাইব্রেরি টাইপস**
    ```typescript
    // @types/express ইনস্টল করা থাকতে হবে
    import express from 'express';
    ```

35. **ফাংশন অ্যানোনিমাস**
    ```typescript
    const multiply = (x: number, y: number): number => x * y;
    ```

36. **রিটান টাইপ**
    ```typescript
    function add(x: number, y: number): number {
        return x + y;
    }
    ```

37. **টাইপ এন্ড টাস্ক**
    ```typescript
    type Task = {
        title: string;
        completed: boolean;
    };
    ```

38. **মুডিফায়ারস**
    ```typescript
    class Base {
        protected x: number;
        constructor() {
            this.x = 10;
        }
    }
    ```

39. **ভ্যারিয়েন্ট টাইপ**
    ```typescript
    type Variant = 'small' | 'medium' | 'large';
    ```

40. **টাইপ স্ট্রিং**
    ```typescript
    type StringMap = { [key: string]: string };
    ```

### 41-50: অন্যান্য বৈশিষ্ট্য

41. **ডিফল্ট প্যারামিটার**
    ```typescript
    function greet(name: string = "Guest") {
        console.log(`Hello, ${name}`);
    }
    ```

42. **শর্তাধীন টাইপ**
    ```typescript
    type Response<T> = T extends string ? string : number;
    ```

43. **ম্যাপিং টাইপস**
    ```typescript
    type ReadOnly<T> = {
        readonly [K in keyof T]: T[K];
    };
    ```

44. **ক্রিয়েট টাইপ**
    ```typescript
    type Point = {
        x: number;
        y: number;
    };
    ```

45. **এশিনক্রনাস**
    ```typescript
    async function fetchUser(userId: number): Promise<User>

 {
        const response = await fetch(`/api/users/${userId}`);
        return response.json();
    }
    ```

46. **রিটার্ন টাইপ**
    ```typescript
    function calculateArea(radius: number): number {
        return Math.PI * radius * radius;
    }
    ```

47. **ডিক্লেয়ারেশন মার্জিং**
    ```typescript
    interface Window {
        myCustomFunction: () => void;
    }
    ```

48. **সাবটাইপিং**
    ```typescript
    type Animal = { name: string };
    type Dog = Animal & { breed: string };
    ```

49. **অভ্যন্তরীণ ফাংশন**
    ```typescript
    class Example {
        private internalFunction() {
            console.log("This is a private function");
        }
    }
    ```

50. **কাস্টম টাইপ গার্ড**
    ```typescript
    function isString(value: any): value is string {
        return typeof value === "string";
    }
    ```

### উপসংহার
TypeScript কোড লেখার জন্য একটি শক্তিশালী টুল, যা জাভাস্ক্রিপ্টের উপর স্ট্যাটিক টাইপিং, উন্নত গঠন এবং উন্নত টুলিংয়ের মাধ্যমে কোডের গুণমান উন্নত করে। এই 50টি পয়েন্ট আপনাকে TypeScript-এ আপনার দক্ষতা বৃদ্ধিতে সহায়তা করবে।

