AMA Questions & Answers

Adhikya Edammala: Difference between parseInt() and Number()

parseInt() converts a value into an integer and stops parsingwhen it encounters an invalid character.

Number() converts the entire value into a number. If anyinvalid character exists, it generally returns NaN.

parseInt("12.8");   // 12
Number("12.8");     // 12.8

parseInt("20px");   // 20
Number("20px");     // NaN

Number("");         // 0
parseInt("");       // NaN

Use a radix with parseInt():

parseInt("101", 2); // 5

Allanki VV Manikanta Sai: On which app was React first implemented?

React was first implemented in Facebook's News Feed in 2011. It waslater adopted by Instagram in 2012 and open-sourced in 2013.

Arpit Yadav: What are props?

Props (short for properties) are used to pass data from a parentcomponent to a child component in React.

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return <Welcome name="Arpit" />;
}

Props are read-only.

Parlapalli Sulochana: Different types of methods in Python OOP

1. Instance Method

class Student:
    def show(self):
        print("Instance method")

2. Class Method

class Student:
    school = "ABC School"

    @classmethod
    def show_school(cls):
        print(cls.school)

3. Static Method

class Calculator:
    @staticmethod
    def add(a, b):
        return a + b

Rongala Vasu: What is a bundler?

A bundler combines application files and dependencies into optimizedfiles for browsers.

Popular bundlers: - Webpack - Vite - Parcel - Rollup - esbuild

Example:

Input:

App.js
Header.js
Footer.js
styles.css

Output:

bundle.js
bundle.css

Vikas Mehta: What is the dependency array in useEffect()?

No dependency array

useEffect(() => {
  console.log("Runs after every render");
});

Empty dependency array

useEffect(() => {
  console.log("Runs once after mount");
}, []);

With dependencies

useEffect(() => {
  console.log("Count changed");
}, [count]);
