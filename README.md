AIM:

To Develop a complete Todo application with all features using React

ALGORITHM:

1.Set up your React project.

2.Create the main component.

3.Create the input form.

4.Display the todo list.

5.Add functionality to mark items as complete.

6.Add functionality to delete items.

PROGRAM:
```
App.js:
java import React, { useState } from 'react'; import './App.css';

function App() { const [tasks, setTasks] = useState([]); const [newTask, setNewTask] = useState(''); const [editTaskId, setEditTaskId] = useState(null);

const handleAddTask = () => { if (newTask.trim() !== '') { const newTaskItem = { id: Date.now(), text: newTask, completed: false, }; setTasks([...tasks, newTaskItem]); setNewTask(''); } };

const handleEditTask = (id, newText) => { const updatedTasks = tasks.map((task) => { if (task.id === id) { return { ...task, text: newText, }; } return task; }); setTasks(updatedTasks); setEditTaskId(null); };

const handleDeleteTask = (id) => { const updatedTasks = tasks.filter((task) => task.id !== id); setTasks(updatedTasks); };

const handleToggleComplete = (id) => { const updatedTasks = tasks.map((task) => { if (task.id === id) { return { ...task, completed: !task.completed, }; } return task; }); setTasks(updatedTasks); };

return (

<h1 style={{textAlign:"center"}}>TO-DO LIST
<input type="text" value={newTask} onChange={(e) => setNewTask(e.target.value)} placeholder="Enter a new task" /> Add
{tasks.map((task) => ( <li key={task.id} className={task.completed ? 'completed' : ''}> <input type="checkbox" checked={task.completed} onChange={() => handleToggleComplete(task.id)} /> {editTaskId === task.id ? ( <input type="text" value={task.text} onChange={(e) => handleEditTask(task.id, e.target.value)} /> ) : ( {task.text} )}
{editTaskId === task.id ? ( <button onClick={() => handleEditTask(task.id, task.text)}>Save ) : ( <button onClick={() => setEditTaskId(task.id)}>Edit )} <button onClick={() => handleDeleteTask(task.id)}>Delete
))}
); } export default App;
App.css:
java .todo-app { width: 400px; margin: 50px auto; background-color:rgb(231, 238, 143); padding:20px; }

.task-input { display: flex; margin-bottom: 10px; }

.task-input input[type='text'] { flex-grow: 1; height: 30px; font-size: 16px; padding: 5px; }

.task-input button { height: 30px; margin-left: 10px; background-color: #d29a51; color: #fff; border: none; cursor: pointer; }

.task-list { list-style: none; padding: 0; }

.task-list li { display: flex; align-items: center; padding: 10px; background-color: #f1f1f1; margin-bottom: 5px; text-decoration: none; }

.task-list li.completed span { text-decoration: line-through; }

.task-list li input[type='checkbox'] { margin-right: 10px; }

.task-list li input[type='text'] { flex-grow: 1; height: 25px; font-size: 14px; padding: 3px; }

.task-list li button { margin-left: 10px; background-color: #ff4d4d; color: #fff; border: none; cursor: pointer; } .task-actions { display: flex; }

.task-actions button { margin-left: 5px; }
  ```

OUTPUT:

<img width="411" alt="to do" src="https://github.com/mehanthyka/to-do-application/assets/127507580/26497c76-1b7a-41ed-b644-c9fd4fc5b40c">


<img width="413" alt="to do list" src="https://github.com/mehanthyka/to-do-application/assets/127507580/fade293f-3dfa-4693-b18c-4b342e074042">



RESULT:
  
Thus,a todo application is created using react.
