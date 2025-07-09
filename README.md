# Employee-Portal
The  Employee-Portal uses a React front-end architecture with component-based design. It follows a state management pattern using React Context API, where the AuthContext provides global access to user data. Data persistence is handled through localStorage, and the UI is created using Tailwind CSS for responsive design. The system has role-based access (admin/employee) and features a Kanban-style task management board.
 
The Employee-Portal implements two distinct roles:
1. **Admin Role**: Can create tasks, assign them to employees, view all tasks across employees, and add new employees to the system.
2. **Employee Role**: Can view their assigned tasks, accept new tasks, mark tasks as complete or failed, and track their task statistics.
Authentication is managed through the login process and session persistence via localStorage.

Tasks follow a workflow similar to a Kanban board with four status columns:
1. **New Tasks**: Recently assigned tasks waiting for employee acceptance
2. **In Progress**: Tasks accepted by employees that are being worked on
3. **Completed**: Successfully finished tasks
4. **Failed**: Tasks that couldn't be completed
Each status change updates the task counts for proper metrics and statistics. The admin dashboard receives real-time notifications when task statuses change.


The application uses localStorage for data persistence:
1. User authentication data is stored in 'loggedInUser' key
2. Employee and task data is stored in 'userData' key
3. Task state history is tracked in 'previousTaskState' for notifications
4. Each component that modifies data updates both the React state and localStorage
5. When the application loads, it retrieves data from localStorage and populates the state
