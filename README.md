IdeaHaven

IdeaHaven is a modern and intuitive note-taking app designed to help you capture, organize, and store your ideas seamlessly. With support for rich media (text, images, video, and audio) and speech-to-text functionality, IdeaHaven provides an innovative way to manage your creative thoughts and notes.

Features
Create Notes: Add text, images, audio, and video to your notes.
Speech-to-Text: Dictate your notes with built-in speech recognition.
Rich Media Support: Upload and manage media files alongside text.
Organized Notes: Display notes in a clean, responsive layout.
Persistent Storage: Save your notes securely using Sanity.io.


**Tech Stack**

**Frontend**
React.js: For building dynamic and interactive user interfaces.
Tailwind CSS: For responsive and modern styling.

**Backend**
Sanity.io: For storing and retrieving notes and media.

**Additional Libraries**
React Router: For navigation and routing.
React Media Recorder: For recording audio and video.
React Speech Recognition: For speech-to-text functionality.
UUID: For generating unique IDs for notes.


**Installation and Setup**

**Clone the Repository:**
git clone https://github.com/your-username/idea-haven.git
cd idea-haven


**Install Dependencies:**
npm install
Set Up Sanity.io:

Create a Sanity project:

sanity init

Add the note schema in sanity/schemas/note.js:

export default {
  name: "note",
  title: "Note",
  type: "document",
  fields: [
    { name: "title", title: "Title", type: "string" },
    { name: "content", title: "Content", type: "text" },
    { name: "image", title: "Image", type: "image" },
    { name: "video", title: "Video", type: "file" },
    { name: "audio", title: "Audio", type: "file" },
  ],
};

**Deploy the schema:**
sanity deploy

**Configure Sanity Client:**
Create a file src/sanityClient.js:

import sanityClient from "@sanity/client";

const client = sanityClient({
  projectId: "your_project_id", // Replace with your Sanity project ID
  dataset: "production",       // Replace with your dataset name
  useCdn: true,
  apiVersion: "2023-01-01",
});

export default client;

**Start the App:**

npm start


**How to Use**
**Create a New Note:**
Navigate to the "Add Note" page.
Enter a title and optional content.
Use the upload buttons to attach media files.
Optionally, use the speech-to-text feature to dictate your notes.


**View Notes:**
Navigate to the home page to see all saved notes.

**Manage Notes:**
Edit or delete notes as needed.

Folder Structure
src/
  components/
    NoteForm.js    // Component for creating notes
    NoteList.js    // Component for listing all notes
    NoteCard.js    // Component for displaying individual notes
  pages/
    Home.js        // Main page for displaying notes
    AddNote.js     // Page for creating new notes
  context/
    NoteContext.js // Global state management
  sanityClient.js  // Sanity configuration


**Deploying to Netlify**
Build the App for Production:

Run the following command to generate the production build of your app:
npm run build

**Sign Up/Log In to Netlify:**
Go to Netlify and create an account or log in.

**Create a New Site:**
In your Netlify dashboard, click "Add New Site" and choose "Deploy manually".

**Upload Build Folder:**
Drag and drop the build folder generated in Step 1 into the upload area in Netlify.

**Configure Site:**
Once uploaded, Netlify will deploy your app and provide a live URL.
You can customize the site name if desired.

**Set Up Continuous Deployment (Optional):**

Connect your GitHub repository to Netlify for automatic deployments with every push.
Navigate to "Sites" → Your Site → Deploy Settings → Build & Deploy.
Add your repository and follow the prompts.

**Future Enhancements**
Add support for note categorization and tags.
Implement user authentication for personalized note management.
Enhance media previews for uploaded files.


**Contributing**
Contributions are welcome! Please follow these steps:

**Fork the repository.**

**Create a new branch for your feature:
**
git checkout -b feature-name

**Commit your changes:**
git commit -m "Add feature name"

**Push your branch and submit a pull request.**

**License**
This project is licensed under the MIT License. See the LICENSE file for details.

**Acknowledgements**
React.js
Sanity.io
Tailwind CSS
React Speech Recognition
React Media Recorder
