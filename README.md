# Smart-Hostel-Resource-Management-System
A system-level full-stack application that optimizes hostel room allocation using scheduling concepts, monitors electricity usage, and streamlines complaint management through secure role-based authentication and real-time data processing.


## 👥 User Roles & Permissions

### 🔹 Admin
- Manage students
- Manage rooms
- Assign rooms
- Monitor electricity usage
- View & resolve complaints
- Track payments
- Manage wardens

### 🔹 Warden
- View allocated students
- Monitor complaints
- Approve/reject leave requests
- Update room status

### 🔹 Student
- View profile
- View room details
- Raise complaints
- View payment history
- Submit leave request



## 🗄 Database Design

### Entities

#### 1️⃣ Student
- student_id (Primary Key)
- name
- email
- phone
- course
- year
- room_id (Foreign Key)
- created_at

#### 2️⃣ Room
- room_id (Primary Key)
- room_number
- floor
- capacity (Max 2 students)
- status (Available / Full / Maintenance)

#### 3️⃣ Warden
- warden_id (Primary Key)
- name
- email
- phone

#### 4️⃣ Admin
- admin_id (Primary Key)
- name
- email
- password

#### 5️⃣ Complaint
- complaint_id (Primary Key)
- student_id (Foreign Key)
- room_id (Foreign Key)
- warden_id (Foreign Key)
- description
- status (Pending / Resolved)
- created_at

#### 6️⃣ Payment
- payment_id (Primary Key)
- student_id (Foreign Key)
- amount
- payment_date
- status

#### 7️⃣ LeaveRequest
- leave_id (Primary Key)
- student_id (Foreign Key)
- warden_id (Foreign Key)
- from_date
- to_date
- reason
- status (Pending / Approved / Rejected)

#### 8️⃣ ElectricityUsage
- usage_id (Primary Key)
- room_id (Foreign Key)
- month
- units_consumed
- recorded_at
