Full Stack Skill Gap Analyzer:

This project is a full-stack web application that helps users understand their skill gaps, generate a career roadmap, and view the latest technology news. It contains a React frontend and a Spring Boot backend.

Features:

1. Career Goal Input Page (Frontend)

Users can enter:

Target role

Current skills

Click “Analyze My Career Path”


2. Skill Gap Analyzer API (Backend – POST /api/skill-gap)

The backend compares:

User's skills

Predefined skill requirements for selected roles


The API returns:

Matched skills

Missing skills

Recommendations

Suggested learning order


3. Career Roadmap API (Backend – POST /api/roadmap):

Based on the selected target role, the backend returns a 3-phase roadmap such as:

Phase 1: Core basics

Phase 2: Domain-specific tools

Phase 3: Projects, deployment, advanced topics


4. HackerNews Integration (Frontend):

Shows the latest 5 technology-related news stories with:

Title

URL

Score

Author

Time


5. Combined Dashboard:

After analysis, the dashboard displays:

Skill gap results (left side)

Career roadmap (right side)

Latest tech news (bottom section)

Tech Stack

Frontend

React

Axios

CSS or Tailwind


Backend:

Java

Spring Boot

Spring Web

Spring Data JPA

PostgreSQL

pgAdmin

Lombok

Project Structure:

/backend
   ├── controllers
   ├── services
   ├── models
   ├── utils
   └── application.properties

/frontend
   ├── src
   │    ├── components
   │    ├── services
   │    └── App.jsx
   └── package.json

Backend Setup (Spring Boot):

1. Clone the repository

git clone <repo-link>
cd backend

2. Configure PostgreSQL

Update application.properties:

spring.datasource.url=jdbc:postgresql://localhost:5432/skilldb
spring.datasource.username=postgres
spring.datasource.password=yourpassword

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

3. Start the backend

Using Spring Tool Suite or:

mvn spring-boot:run

4. Test APIs in Postman

POST /api/skill-gap

{
  "targetRole": "Backend Developer",
  "currentSkills": ["Java", "SQL"]
}

POST /api/roadmap

{
  "targetRole": "Backend Developer"
}


Frontend Setup (React):

1. Go to frontend folder

cd frontend

2. Install dependencies

npm install

3. Add environment file

Create .env:

REACT_APP_API_BASE=http://localhost:8080

4. Start frontend

npm start
.....

API Endpoints:

Method	Endpoint	Purpose

POST	/api/skill-gap	Performs skill comparison
POST	/api/roadmap	Returns role-based roadmap
GET	HackerNews API	Displays top 5 news stories

---

Deployment (Optional):

Frontend:

Deploy using Vercel or Netlify:

npm run build

Backend:

Deploy using Render, Railway, or any Spring Boot hosting service.

Include links if hosted:

Frontend: https://example.vercel.app
Backend: https://example.onrender.com


---

Assumptions:

Roadmaps are predefined and static.

Skills for each target role come from a fixed JSON list.

The application does not require user login.

Only the latest 5 HackerNews stories are fetched.

---

How to Use:

1. Enter career role and skills

2. Click “Analyze My Career Path”

3. View skill results + roadmap

4. Scroll down to see tech news


---

Testing:

Tested backend using Postman

Tested frontend by verifying API responses

Console messages added to handle errors
