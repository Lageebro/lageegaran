# Project: "Lagee Garan" 3D Personal Portfolio Roadmap

## 1. Project Vision
Create a high-performance, dark-mode personal website using a **Glassmorphism** (transparent) design aesthetic. [cite_start]The site will feature 3D depth, smooth scroll animations, and a modern "Electric Green" accent color.

---

## 2. Technical Requirements
* **Framework**: Vanilla HTML5, CSS3, and JavaScript (ES6+).
* **Styling**: **Tailwind CSS** for rapid UI development and utility-first styling.
* **Database**: **Dexie.js** for local storage (used to save contact form messages or user-specific theme preferences).
* **3D Elements**: **Three.js** or **Atropos.js** for touch/mouse-parallax 3D effects on images and cards.
* **Animations**: **Framer Motion** (if using a framework) or **GSAP** (GreenSock) for high-end scroll and entrance animations.

---

## 3. Design Specification
* **Background**: Deep Dark/Charcoal (#0A0A0A).
* **Primary Accent**: Electric/Lime Green (#39FF14).
* **UI Style**: Glassmorphism (Background blur, semi-transparent borders).
* **Typography**: Bold sans-serif for headings (e.g., Montserrat or Syne).
* **Main Visual**: Use **"My Photo.jpg"** as the primary hero image with background removal for a floating 3D effect.

---

## 4. Site Structure (4 Core Pages)

### Page 1: Home (The Hook)
* **Hero Section**: 3D floating avatar (using "My Photo.jpg").
* [cite_start]**Tagline**: "Empowering Digital Solutions Through Creative Thinking"[cite: 5, 35].
* [cite_start]**Intro**: Motivated ICT enthusiast with a solid foundation in computer skills and teamwork[cite: 5, 6, 7].
* **CTA**: "Let's Collaborate" button linking to the contact page.

### Page 2: About & Expertise
* [cite_start]**Profile**: Detailed bio mentioning a commitment to learning new tools and adapting quickly[cite: 7, 8].
* **Education Timeline**:
    * [cite_start]Jayanthi Vidyalaya Ja ela (G.C.E. O/L, 2011-2022)[cite: 9, 10, 11].
    * [cite_start]Nalanda Central College Minuwangoda (G.C.E. A/L Engineering Technology, 2023-2025)[cite: 12, 13].
    * [cite_start]ESOFT Metro Campus (Diploma in IT, 2023-2024)[cite: 14, 15].
* [cite_start]**Languages**: Proficient in English, Sinhala, and Tamil[cite: 21, 22, 23].

### Page 3: Technical Skills & Services
* [cite_start]**Software Stack**: Python, Java, and JavaScript programming[cite: 24].
* [cite_start]**Creative Suite**: Expert in Adobe Photoshop, Illustrator, Premiere Pro, and Audition.
* [cite_start]**Web & DB**: HTML, CSS, and MySQL database management[cite: 27, 28].
* [cite_start]**Hardware Expertise**: Specialist in hardware troubleshooting, repair, and PC assembly/dismantling[cite: 39, 40, 41].
* [cite_start]**OS Knowledge**: Proficient across Windows, macOS, and Linux[cite: 29].

### Page 4: Contact & Interaction
* **Form**: Interactive glassmorphism form.
* **Logic**: Use **Dexie.js** to store form submissions locally so you never lose a lead even if offline.
* [cite_start]**Details**: Display Location (Ja ela, Sri Lanka), Email (lageegaran12@gmail.com), and Phone (+94 789080880)[cite: 16, 18, 19].

---

## 5. Development Milestones
1.  **Phase 1**: Set up Tailwind CSS and global dark theme variables.
2.  **Phase 2**: Implement the hero section with the 3D "tilt" effect on your main photo.
3.  [cite_start]**Phase 3**: Populate About and Skills sections using the CV data[cite: 1, 2, 17].
4.  **Phase 4**: Integrate Dexie.js for the contact form functionality.
5.  **Phase 5**: Final polish with GSAP animations for smooth page transitions.