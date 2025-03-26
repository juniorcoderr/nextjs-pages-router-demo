# **Next.js Pages Router Demo**  

This **Next.js Pages Router Demo** project is built for **learning and educational purposes**, providing a hands-on approach to understanding core **Next.js concepts** like **file-based routing**, **dynamic routes**, **catch-all routes**, and **modular component architecture**. The project is designed to showcase how to build scalable, maintainable applications using the **Pages Router** approach in Next.js.  

It covers real-world scenarios by implementing features like **dynamic content rendering**, **nested routing**, and **component reusability**, making it a valuable resource for developers looking to strengthen their knowledge of **Next.js** and **React-based** web applications.  

## **🚀 Features**  
✅ File-based routing with the Next.js Pages Router  
✅ Dynamic route handling (`[eventId].js`)  
✅ Catch-all routes (`[...slug].js`)  
✅ Reusable UI components  
✅ Modular CSS for styling  
✅ Mock data for events  

---

## **📁 Project Structure**  

```
nextjs-pages-router-2/
│── components/           # Reusable UI components
│   ├── event-detail/     # Event detail components
│   ├── events/           # Event listing and search components
│   ├── icons/            # Custom SVG icons
│   ├── layout/           # Page layout and header
│   ├── ui/               # Common UI elements (buttons, alerts)
│
│── pages/                # Next.js file-based routing
│   ├── events/           # Events pages
│   │   ├── index.js      # List of all events
│   │   ├── [eventId].js  # Dynamic route for individual events
│   │   ├── [...slug].js  # Catch-all route for event filtering
│   ├── index.js          # Home page
│   ├── _app.js           # Custom App component
│
│── public/               # Static assets (images, icons)
│── styles/               # Global styles
│── dummy-data.js         # Mock data for events
│── package.json          # Project dependencies
│── README.md             # Project documentation
```

---

## **🛠️ Installation & Running Locally**  

1️⃣ Clone the repository:  
```bash
git clone https://github.com/juniorcoderr/nextjs-pages-router-demo.git
cd nextjs-pages-router-demo
```

2️⃣ Install dependencies:  
```bash
npm install
```

3️⃣ Start the development server:  
```bash
npm run dev
```

4️⃣ Open [http://localhost:3000](http://localhost:3000) in your browser.  

---

## **📌 Key Files Explained**  

### **📄 `pages/` (Next.js Routing System)**  
- **`index.js`** – Home page  
- **`events/index.js`** – Displays all events  
- **`events/[eventId].js`** – Dynamic route for individual event pages  
- **`events/[...slug].js`** – Catch-all route for filtering events  

### **📂 `components/` (Reusable UI Components)**  
- **`event-detail/`** – Components for event details  
- **`events/`** – Components for event listing and search  
- **`icons/`** – Custom icons (SVG-based)  
- **`layout/`** – Page layout with `main-header.js`  
- **`ui/`** – Buttons, alerts, and other common UI elements  

### **📂 `public/` (Static Assets)**  
- Stores images and icons used in the project  

### **📄 `dummy-data.js`**  
- Contains mock event data used throughout the project  

---

## **🛠️ Technologies Used**  
🚀 **Next.js** – React framework with built-in routing  
🎨 **CSS Modules** – Component-scoped styling  
📂 **File-based Routing** – Simplified navigation with Next.js pages  

--- 

## **📚 Concepts and Features Explained in Detail**  

### 1. ✅ **File-Based Routing**  
Next.js uses a **file-based routing system** where each file inside the `pages` directory automatically becomes a route. This eliminates the need for external routing libraries (e.g., React Router) and simplifies navigation.  

- **How it works in this project:**  
  - `/pages/index.js` – Renders the homepage at `/`  
  - `/pages/events/index.js` – Renders the event listing page at `/events`  
  - Routing is automatic—just add a file, and it becomes accessible as a URL path.  

This structure helps organize and maintain routes efficiently as the application scales.  

---

### 2. 🔀 **Dynamic Routes**  
Dynamic routes in Next.js allow you to create **routes with variables**, enabling you to display data for unique content (e.g., individual events or user profiles). These are defined by enclosing route parameters in square brackets (`[param].js`).  

- **How it's implemented:**  
  - `/pages/events/[eventId].js` – Dynamic route for displaying individual event details.  
  - Uses the `useRouter` hook to access the `eventId` from the URL:  
    ```js
    const router = useRouter();
    const eventId = router.query.eventId;
    ```  
  - Example URLs:  
    - `/events/1` (for Event 1)  
    - `/events/coding-bootcamp` (for a coding event)  

Dynamic routes enhance user experience by allowing unique, data-driven content without manual page creation.  

---

### 3. 📊 **Catch-All Routes**  
Catch-all routes allow the application to match multiple dynamic path segments, making them perfect for handling flexible and nested paths.  

- **How it's implemented:**  
  - `/pages/events/[...slug].js` – Handles advanced event filtering and search.  
  - Access multiple path parameters as an array:  
    ```js
    const { slug } = router.query;
    ```  
  - Example URLs:  
    - `/events/2024/special` (for events in 2024)  
    - `/events/category/technology` (for tech events)  

Catch-all routes are useful for handling deeply nested dynamic URLs and improve navigation flexibility.  

---

### 4. 📦 **Component Reusability & Modular Structure**  
This project follows a **component-driven architecture**, where common UI and page sections are extracted into reusable components. This approach improves code organization, scalability, and reusability.  

- **Key Component Directories:**  
  - **`components/event-detail/`** – Displays event information (summary, logistics).  
  - **`components/events/`** – Event-related components (event list, search form).  
  - **`components/layout/`** – Application-wide layout (header, navigation).  
  - **`components/ui/`** – Reusable UI elements (buttons, alerts).  

- **Example Component:**  
  The `EventItem` component displays a single event with details and a button:  
  ```js
  import Link from 'next/link';
  const EventItem = ({ title, date, location, id }) => (
    <div>
      <h2>{title}</h2>
      <p>{location}</p>
      <Link href={`/events/${id}`}>View Details</Link>
    </div>
  );
  export default EventItem;
  ```  

---

### 5. 🎨 **CSS Modules for Scoped Styling**  
Each component has its own CSS module file (e.g., `event-item.module.css`), ensuring styles are locally scoped to that component. This prevents global class conflicts and enhances maintainability.  

- **How it's used:**  
  - Example:  
    - `components/events/event-item.module.css` – Contains styles for the event card.  
  - Usage in the component:  
    ```js
    import styles from './event-item.module.css';
    <div className={styles.item}>Event Content</div>;
    ```  

CSS Modules improve style encapsulation, making the project easier to maintain and extend.  

---

### 6. 📊 **Mock Data Integration**  
The project includes a `dummy-data.js` file to simulate backend data. This is useful for prototyping and allows users to work with mock events without needing an actual API.  

- **Example Data Structure:**  
  ```js
  const DUMMY_EVENTS = [
    { id: 'e1', title: 'Coding Bootcamp', location: 'New York', date: '2024-05-01' },
  ];
  export default DUMMY_EVENTS;
  ```  

This provides a **realistic development environment** while keeping the setup simple.  

---

### 7. 🌐 **Custom Layout with `_app.js`**  
The `pages/_app.js` file customizes the default **Next.js app structure**. This project uses it to wrap all pages with a consistent layout, such as the header navigation.  

- **How it's implemented:**  
  ```js
  import Layout from '../components/layout/layout';
  function MyApp({ Component, pageProps }) {
    return (
      <Layout>
        <Component {...pageProps} />
      </Layout>
    );
  }
  export default MyApp;
  ```  

---

## **🎯 Learning Outcomes**  
By exploring this project, you will:  
✅ Understand the **Next.js Pages Router** and how to structure an application.  
✅ Implement **dynamic** and **catch-all** routes for flexible page generation.  
✅ Create **reusable components** for consistent UI and improved maintainability.  
✅ Use **CSS Modules** to apply scoped and maintainable styling.  
✅ Simulate backend data with **mock datasets** for development and testing.  

---

## **💡 Contributions & Feedback**  
Feel free to **fork**, **open issues**, or submit **pull requests**! 🚀 
