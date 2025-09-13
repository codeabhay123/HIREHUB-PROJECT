🌐 HireHub – A Modern MERN Recruitment Platform

HireHub is a full-stack MERN (MongoDB, Express.js, React, Node.js) application designed to modernize the recruitment ecosystem.
It connects Students (aspiring professionals) with Recruiters through a seamless, real-time, and secure hiring experience.

⚡ HireHub goes beyond a simple job board by providing tools to post jobs, apply for positions, track applications, and manage recruitment workflows — all within a clean, responsive, and user-friendly interface.

🚀 Features
👩‍🎓 For Students

🔐 Secure signup & login with JWT-based authentication.

🔍 Explore and filter jobs by title, location, or requirements.

📄 Upload resumes directly (stored via Cloudinary).

📝 Apply for jobs in one click, with status tracking (Pending, Accepted, Rejected).

📊 Personal dashboard showing profile, skills, applied jobs, and resume.

🏢 For Recruiters

🔐 Role-based access to a secure Recruiter Dashboard.

🏬 Manage companies and their profiles.

📢 Create and manage job postings.

👥 Track applicants with a built-in Application Tracking System (ATS).

✅ Accept/Reject applications with instant status updates visible to students.

🌟 General Highlights

🖥️ Single-Page Application (SPA) with React & Redux Toolkit.

🎨 Sleek UI powered by Tailwind CSS + Shadcn/UI components.

⚡ Real-time interactions with RESTful API.

🔒 Secure authentication with JWT & password hashing via bcrypt.js.

📦 Media uploads handled via Multer + Cloudinary.

🎬 Smooth animations with Framer Motion.

🛠️ Tech Stack
Layer	Technology
Frontend	React.js, Redux Toolkit, Redux Persist, React Router DOM, Tailwind CSS, Shadcn/UI, Axios, Framer Motion
Backend	Node.js, Express.js, RESTful API
Database	MongoDB + Mongoose ODM
Auth	JSON Web Token (JWT), bcrypt.js
Media	Cloudinary, Multer
Tooling	Vite, Postman


🗄️ Database Models
{
  fullName: String,
  email: String,
  password: String, // Hashed
  phoneNumber: String,
  role: { type: String, enum: ['Student', 'Recruiter'] },
  profile: {
    bio: String,
    skills: [String],
    resume: String, // Cloudinary URL
    profilePhoto: String
  }
  
}


🏬 Company

{
  name: String,
  description: String,
  website: String,
  location: String,
  logo: String, // Cloudinary URL
  userId: { type: ObjectId, ref: 'User' }
}

💼 Job

{
  title: String,
  description: String,
  requirements: [String],
  salary: Number,
  location: String,
  jobType: String,
  experience: String,
  company: { type: ObjectId, ref: 'Company' },
  createdBy: { type: ObjectId, ref: 'User' },
  applications: [{ type: ObjectId, ref: 'Application' }]
}
📩 Application
{
  job: { type: ObjectId, ref: 'Job' },
  applicant: { type: ObjectId, ref: 'User' },
  status: { type: String, enum: ['Pending', 'Accepted', 'Rejected'], default: 'Pending' }
}

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/HireHub.git
cd HireHub


2️⃣ Install Dependencies
# Install server dependencies
cd backend
npm install

# Install client dependencies
cd ../frontend
npm install

3️⃣ Configure Environment Variables
MONGO_URI=your_mongo_connection_string
JWT_SECRET=your_secret_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

4️⃣ Run the Application
# Run backend
cd backend
npm run dev

# Run frontend
cd ../frontend
npm run dev

🛣️ Future Roadmap

We’re continuously working to make HireHub more powerful and user-friendly.

🔮 Upcoming Features

📝 Resume Maker – A built-in resume builder that allows students to create professional resumes directly within HireHub.

🤖 AI Resume Analyzer – AI-powered resume analysis to provide personalized feedback, keyword optimization, and ATS (Applicant Tracking System) compatibility scoring.

