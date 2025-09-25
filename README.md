## **Modifying Data through API – Hospital Patient Management System**

This live practical session focuses on designing real backend APIs for managing patient records. You’ll define Express routes, map them to Mongoose methods, and test the APIs using an API client like Postman or Bruno.

Instead of a student app, we’ll work with a basic **Patient Record System**.

### **1. Scenario Overview**

You're developing the backend for a **hospital patient management system**. The system should allow:

- Adding new patient records
- Updating patient information (like contact or health history)
- Discharging (deleting) patient records

Each patient record contains:

- `name` (String, required)
- `age` (Number, required)
- `contact` (String, optional)
- `medicalHistory` (Array of Strings, optional)

### **2. Plan Your API Endpoints**

Define the routes needed to modify patient data:

| Endpoint               | Description                      |
| ---------------------- | -------------------------------- |
| POST `/patients`       | Add a new patient                |
| PUT `/patients/:id`    | Update patient details by ID     |
| DELETE `/patients/:id` | Discharge/delete a patient by ID |

Stick to RESTful API conventions for clarity and consistency.

### **3. Choose the Right Mongoose Methods**

Use these Mongoose methods for interacting with the MongoDB database:

| Action | Mongoose Method               |
| ------ | ----------------------------- |
| Create | `Patient.create()`            |
| Update | `Patient.findByIdAndUpdate()` |
| Delete | `Patient.findByIdAndDelete()` |

Ensure proper validation and error handling in your implementation.

### **4. Testing with API Client**

Use **Postman** or **Bruno** to test each API route:

- **POST**:
  Request Body:

  ```json
  {
    "name": "John Doe",
    "age": 45,
    "contact": "9876543210",
    "medicalHistory": ["diabetes", "hypertension"]
  }
  ```

  Expected: `201 Created` with patient data

- **PUT**:
  Update patient's contact:

  ```json
  {
    "contact": "9998887770"
  }
  ```

  Expected: `200 OK` with updated patient info

- **DELETE**:
  Remove a patient by ID
  Expected: `204 No Content`

✅ Also test for edge cases:

- Invalid or missing fields
- Non-existent IDs
- Incomplete updates

### **5. Repository and Setup Instructions**

**Fork the StackBlitz Project:**

- Use the provided [starter template](https://stackblitz.com/edit/stackblitz-starters-8qztiv4a)
- Fork and customize it as required

**Push to GitHub:**

```bash
git init
git remote add origin <your_repo_url>
git add .
git commit -m "Set up patient API endpoints"
git push -u origin main
```

### **6. Submission Format**

Submit a **PDF** that includes:

- GitHub repository link
- Google Drive demo video link (visibility: `kalvium.community`)
- A short explanation of your API design

**Example Naming Format:**
`patient_api_<yourname>.pdf`

**Example Content:**

- GitHub: `https://github.com/<your_username>/patient_api`
- Video: Google Drive link
- Note: “Created and tested patient API endpoints using Mongoose methods for real-world hospital data operations.”
