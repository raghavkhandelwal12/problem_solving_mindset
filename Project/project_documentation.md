# **Project: Problem Solving Mindsets**  

## **Objective Overview**  
The project provides a structured learning path to strengthen programming fundamentals like `variables, data types, control flow, functions, and OOP.` It enables hands-on learning through interactive exercises, progress tracking, and feedback mechanisms to enhance understanding.  

## **Requirement Analysis**  

### **1. Functional Requirements**  
- `**Topic Selection**`: Users select topics (`Variables, Data Types, Control Flow, Functions, OOP`) and receive structured content.  

- `**Progress Tracking**`: User progress is stored in `JSON`. If a score is **≥90%**, the next topic unlocks; otherwise, the current topic must be revisited.

- `**Feedback Mechanism**`: Quizzes assess comprehension, guiding users on whether to proceed or review.  

### **2. Non-Functional Requirements**  
- `**User Experience**`: Simple, clear navigation with intuitive feedback.

- `**Scalability**`: Expandable with more topics and exercises.

- `**Security**`: Secure data storage with validation.

- `**Modularity*`*: Separate modules for topic selection, progress tracking, and feedback.  

### **3. Design Patterns**

- `**DRY (Don't Repeat Yourself)**`: Use functions/modules to avoid code repetition.

- `**Modularity**`: Divide functionalities into independent modules.

- `**Separation of Concerns**`: Keep content, tracking, and feedback separate.  

### **4. Technology Stack**

- `**Python (CLI)**`: Core programming language.  
- `**JSON**`: Store user progress and feedback.  
- `**Quiz Interface**`: Interactive assessment system.  
