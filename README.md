# REACT END PAPER TASK

### AIM :
         To create a birthday react application which displays birthdays on a particular day.

### ALGORITHM :
        Step 1 : Start the program.
        Step 2 : Install the required packages and create a react application
        Step 3 : Create a folder routes and include the necessary components for all three pages.
        Step 4 : Import the components required in the app.js page.
        Step 5 : To run the application type npm start in the terminal.
        Step 6 : Open the browser and enter the url as localhost:3500 
        Step 7 : Stop the program.
        
 ### PROGRAM :
 
      app.js
           import "./App.css";
           import Calendar from "./component/Calendar";

           function App() {
           return (
           <div className="App">
           <Calendar></Calendar>
           </div>
           );
           }

          export default App;
          
      calender.jsx
           import React from "react";

           export default function Birthdays({ info, upcoming }) {
           return <ul>{iterate(info, upcoming)}</ul>;
           }

           function iterate(data, flag) {
           if (!data) return;
           const bgColor = flag ? { backgroundColor: "#ffe66d" } : {};
           return (
           <>
          {data.map((person, index) => {
          return (
          <li key={index}>
          <div className="flex" style={bgColor}>
           <img src={person.img} alt="img" />
           <div className="title">
           <h3 className="name">{person.name}</h3>
           <h5 className="age">{Old(person.birthday)} years</h5>
           </div>
           </div>
           </li>
           );
           } )}
          </>
          );
          }

           //  Age
          function Old(personAge) {
          let year = new Date(personAge).getFullYear();
          let currentYear = new Date().getFullYear();

          let age = currentYear - year;
          return age;
          }

     birthday.jsx
          import React, { useState } from "react";
          import "./Calendar.css";
          import Birthdays from "./Birthdays";

           const Info = [
           {
           img: "https://nationaltoday.com/wp-content/uploads/2022/04/Albert-Einstein-Birthday.jpg",
           name: "Albert Einstein",
           birthday: "1887-0-14",
            },
           {
           img: "https://www.india.com/wp-content/uploads/2020/06/sundar-pichai.jpg",
           name: "Sundar Picha",
           birthday: "1972-06-10",
           },
           {
           img: "https://www.india.com/wp-content/uploads/2020/05/Facebook-clear-history-tool.jpg",
           name: "Mark Zuckerberg",
           birthday: "1984-04-17",
           },
           {
           img: "https://akm-img-a-in.tosshub.com/indiatoday/images/story/202109/narendra-modi-pti010721_1_1200x768.jpeg?size=1200:675",
           name: "Narendra Modi",
           birthday: "1950-09-17",
           },
           {
           img: "https://st1.bollywoodlife.com/wp-content/uploads/2023/01/9-52.png",
           name: "A R Rahman",
           birthday: "1967-01-06",
           },
           {
           img: "https://i.zoomtventertainment.com/story/thala_ajith_birthday.jpg",
            name: "Ajith Kumar",
           birthday: "1971-05-01",
           },
           ];

           export default function Calendar() {
            const [date, setDate] = useState();

          console.log(" Date", date);
          return (
          <main id="site-main">
          <div className="calendar">
          <h1 className="text-dark title">Pick a Date</h1>
          <input type="date" onChange={(e) => setDate(e.target.value)}></input>
          <h2>Selected Date: {date}</h2>
          {/* <h2 className="today text-dark">Display</h2> */}
          {/* <Birthdays info={Display(Info)}></Birthdays> */}
          <h2 className="today text-dark">Today</h2>
          <Birthdays info={Today(Info)}></Birthdays>
          <h2 className="upcoming text-dark">Upcoming</h2>
         <Birthdays info={Upcoming(Info, 4)} upcoming={true}></Birthdays>
         </div>
        </main>
        );
        }

        function Today(person) {
        let currentDay = new Date().getDate();
        let currentMonth = new Date().getMonth();

        let filter = person.filter((data) => {
        let day = new Date(data.birthday).getDate();
        let month = new Date(data.birthday).getMonth();

        return currentDay === day && currentMonth === month;
        });
        return filter;
        }

       // upcoming birthdays
        function Upcoming(person, toMonth) {
        let currentMonth = new Date().getMonth();
        let currentDay = new Date().getDate();

         let filter = person.filter((data) => {
         let month = new Date(data.birthday).getMonth();
         let day = new Date(data.birthday).getDate();

         if (currentDay === day) return;
         return month >= currentMonth && month <= currentMonth + toMonth;
        });

       return filter;
         }
### OUTPUT :
     
![Screenshot (388)1](https://github.com/JANANI0210/react-birthday-calender/assets/86832944/2918ac3a-ea49-4df2-b8a3-96accbac79ff)


### RESULT :
        Thus, to  create a birthday react application which displays birthdays on a particular day is created and implemented successfully.
