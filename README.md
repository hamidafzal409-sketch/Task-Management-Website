[front page of website.html](https://github.com/user-attachments/files/33870836/front.page.of.website.html)
<!DOCTYPE html>
0<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Management Dashboard</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="sidebar" id="sidebar">
    <h2 class="logo">Project<span>Hub</span></h2>

    <p class="menu-title">WORKSPACE</p>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/front%20page%20of%20website.html" class="nav-link active">▦ Dashboard</a>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/projects.html" class="nav-link">▣ Projects</a>
    <a href="" class="nav-link">✓ Tasks</a>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/kanban%20board.html" class="nav-link">▤ Kanban Board</a>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/calender.html" class="nav-link">▦ Calendar</a>

    <p class="menu-title">MANAGEMENT</p>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/team%20members%20page.html" class="nav-link">♙ Team Members</a>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/notifications.html" class="nav-link">♧ Notifications</a>
    <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/reports.html" class="nav-link">▥ Reports & Analytics</a>

    <div class="sidebar-bottom">
        <a href="file:///C:/Users/ALNAFIO/Desktop/internship/New%20folder/settings.html" class="nav-link">⚙ Settings</a>
        <div class="user">
            <div class="avatar">HA</div>
            <div>
                <strong>Hamid Afzal</strong>
                <small>Project Manager</small>
            </div>
        </div>
    </div>
</div>

<main class="main-content">
    <header class="topbar">
        <button class="menu-btn" onclick="toggleSidebar()">☰</button>
        <div>
            <h2>Dashboard Overview</h2>
            <p>Welcome back! Here's what's happening with your projects.</p>
        </div>
        <div class="top-actions">
            <input type="text" id="search" placeholder="Search tasks...">
            <button class="theme-btn" onclick="toggleTheme()">☾</button>
            <button class="primary-btn" onclick="addTask()">+ New Task</button>
        </div>
    </header>

    <section class="welcome">
        <div>
            <h1>Good day, Hamid! 👋</h1>
            <p>Manage your projects and keep your team on track.</p>
        </div>
        <div class="date">📅 <span id="today"></span></div>
    </section>

    <section class="stats">
        <div class="stat-card">
            <div class="stat-icon purple">▣</div>
            <p>Total Projects</p>
            <h2 id="totalProjects">4</h2>
            <small>Projects in workspace</small>
        </div>

        <div class="stat-card">
            <div class="stat-icon blue">✓</div>
            <p>Total Tasks</p>
            <h2 id="totalTasks">12</h2>
            <small>Tasks across all projects</small>
        </div>

        <div class="stat-card">
            <div class="stat-icon green">✔</div>
            <p>Completed Tasks</p>
            <h2 id="completedTasks">5</h2>
            <small>Successfully completed</small>
        </div>

        <div class="stat-card">
            <div class="stat-icon orange">◷</div>
            <p>Pending Tasks</p>
            <h2 id="pendingTasks">7</h2>
            <small>Tasks remaining</small>
        </div>
    </section>

    <section class="content-grid">
        <div class="panel" id="projects">
            <div class="panel-heading">
                <div>
                    <h3>My Projects</h3>
                    <p>Track your project progress</p>
                </div>
                <button class="text-btn" onclick="addProject()">+ Add Project</button>
            </div>

            <div id="projectList"></div>
        </div>

        <div class="panel" id="tasks">
            <div class="panel-heading">
                <div>
                    <h3>Recent Tasks</h3>
                    <p>Keep track of your work</p>
                </div>
                <select id="statusFilter" onchange="renderTasks()">
                    <option value="All">All Status</option>
                    <option value="To Do">To Do</option>
                    <option value="In Progress">In Progress</option>
                    <option value="Completed">Completed</option>
                </select>
            </div>

            <div class="task-list" id="taskList"></div>
        </div>
    </section>

    <section class="panel activity" id="reports">
        <div class="panel-heading">
            <div>
                <h3>Weekly Performance</h3>
                <p>Your completed tasks this week</p>
            </div>
            <span class="performance">↗ Productive workspace</span>
        </div>
        <div class="chart" id="chart">
            <div class="bar-item"><div class="bar" style="height:45%"></div><small>Mon</small></div>
            <div class="bar-item"><div class="bar" style="height:70%"></div><small>Tue</small></div>
            <div class="bar-item"><div class="bar" style="height:55%"></div><small>Wed</small></div>
            <div class="bar-item"><div class="bar" style="height:90%"></div><small>Thu</small></div>
            <div class="bar-item"><div class="bar" style="height:65%"></div><small>Fri</small></div>
            <div class="bar-item"><div class="bar" style="height:35%"></div><small>Sat</small></div>
            <div class="bar-item"><div class="bar" style="height:50%"></div><small>Sun</small></div>
        </div>
    </section>

    <footer>© 2026 ProjectHub. Project Management Dashboard.</footer>
</main>

<script src="script.js"></script>
</body>
</html>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --bg: #f5f6fb;
    --panel: #ffffff;
    --text: #252943;
    --muted: #858ba5;
    --border: #e9ebf3;
    --primary: #6558e8;
}

body {
    font-family: Arial, sans-serif;
    background: var(--bg);
    color: var(--text);
    display: flex;
    transition: 0.3s;
}

.sidebar {
    width: 250px;
    height: 100vh;
    background: var(--panel);
    border-right: 1px solid var(--border);
    padding: 28px 18px;
    position: fixed;
    display: flex;
    flex-direction: column;
    z-index: 10;
}

.logo {
    font-size: 25px;
    margin-bottom: 38px;
}

.logo span {
    color: var(--primary);
}

.menu-title {
    color: var(--muted);
    font-size: 11px;
    font-weight: bold;
    margin: 20px 10px 12px;
    letter-spacing: 1px;
}

.nav-link {
    display: block;
    text-decoration: none;
    color: var(--muted);
    padding: 13px 12px;
    margin: 3px 0;
    border-radius: 9px;
    font-size: 14px;
    transition: 0.2s;
}

.nav-link:hover,
.nav-link.active {
    background: #efedff;
    color: var(--primary);
}

.sidebar-bottom {
    margin-top: auto;
}

.user {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 18px 5px 0;
    border-top: 1px solid var(--border);
    font-size: 13px;
}

.user small {
    display: block;
    color: var(--muted);
    margin-top: 5px;
}

.avatar {
    background: #e9e5ff;
    color: var(--primary);
    padding: 12px;
    border-radius: 50%;
    font-weight: bold;
}

.main-content {
    margin-left: 250px;
    width: calc(100% - 250px);
    padding: 28px 32px;
}

.topbar,
.panel-heading,
.welcome {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
}

.topbar h2 {
    font-size: 23px;
}

.topbar p,
.welcome p,
.panel-heading p {
    color: var(--muted);
    font-size: 13px;
    margin-top: 7px;
}

.top-actions {
    display: flex;
    align-items: center;
    gap: 10px;
}

input,
select {
    padding: 12px;
    border: 1px solid var(--border);
    background: var(--panel);
    color: var(--text);
    border-radius: 8px;
    outline: none;
    max-width: 100%;
}

.primary-btn,
.text-btn,
.theme-btn,
.menu-btn {
    border: none;
    cursor: pointer;
    border-radius: 8px;
    padding: 12px 15px;
    font-weight: bold;
}

.primary-btn {
    background: var(--primary);
    color: white;
}

.text-btn {
    color: var(--primary);
    background: transparent;
}

.theme-btn,
.menu-btn {
    background: var(--panel);
    color: var(--text);
    border: 1px solid var(--border);
}

.menu-btn {
    display: none;
}

.welcome {
    margin: 35px 0 25px;
    background: linear-gradient(120deg, #6558e8, #9286ff);
    color: white;
    padding: 27px;
    border-radius: 15px;
}

.welcome h1 {
    font-size: 23px;
}

.welcome p {
    color: #eeebff;
}

.date {
    font-size: 13px;
    white-space: nowrap;
}

.stats {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 18px;
    margin-bottom: 25px;
}

.stat-card,
.panel {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 13px;
    padding: 21px;
}

.stat-icon {
    width: 39px;
    height: 39px;
    border-radius: 10px;
    display: grid;
    place-items: center;
    font-size: 20px;
    margin-bottom: 17px;
}

.purple { background: #efedff; color: #6558e8; }
.blue { background: #e7f2ff; color: #3184dd; }
.green { background: #e2f8ed; color: #20a66a; }
.orange { background: #fff0df; color: #ec9533; }

.stat-card p {
    color: var(--muted);
    font-size: 13px;
}

.stat-card h2 {
    font-size: 29px;
    margin: 10px 0;
}

.stat-card small {
    color: var(--muted);
    font-size: 11px;
}

.content-grid {
    display: grid;
    grid-template-columns: 1fr 1.25fr;
    gap: 20px;
}

.panel-heading {
    margin-bottom: 24px;
}

.panel-heading h3 {
    font-size: 17px;
}

.project {
    margin: 24px 0;
}

.project-info,
.task-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
}

.project-info strong {
    font-size: 13px;
}

.project-info span,
.task-row small {
    color: var(--muted);
    font-size: 12px;
}

.progress {
    height: 7px;
    background: var(--border);
    border-radius: 10px;
    overflow: hidden;
    margin-top: 13px;
}

.progress div {
    height: 100%;
    background: var(--primary);
    border-radius: 10px;
}

.task-row {
    padding: 15px 0;
    border-bottom: 1px solid var(--border);
}

.task-row:last-child {
    border-bottom: none;
}

.task-row strong {
    font-size: 13px;
    display: block;
    margin-bottom: 7px;
}

.task-row select {
    font-size: 11px;
    padding: 7px;
    width: 125px;
}

.activity {
    margin-top: 22px;
}

.performance {
    font-size: 12px;
    color: #20a66a;
}

.chart {
    height: 180px;
    display: flex;
    justify-content: space-around;
    align-items: end;
    border-bottom: 1px solid var(--border);
    padding: 10px 10px 0;
    gap: 15px;
}

.bar-item {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: end;
    align-items: center;
    gap: 10px;
    flex: 1;
}

.bar {
    width: 65%;
    max-width: 40px;
    min-height: 8px;
    background: #8c80f2;
    border-radius: 6px 6px 0 0;
    transition: 0.3s;
}

.bar:hover {
    background: var(--primary);
}

.bar-item small {
    color: var(--muted);
    padding-bottom: 8px;
}

footer {
    text-align: center;
    padding: 25px;
    color: var(--muted);
    font-size: 12px;
}

body.dark {
    --bg: #171827;
    --panel: #222438;
    --text: #f1f1fa;
    --muted: #a6abc2;
    --border: #35374d;
}

body.dark .nav-link:hover,
body.dark .nav-link.active {
    background: #34304f;
}

body.dark .stat-icon {
    background: #35334b;
}

body.dark .bar {
    background: #9185ff;
}

@media (max-width: 1100px) {
    .stats {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .content-grid {
        grid-template-columns: 1fr;
    }

    .topbar {
        flex-wrap: wrap;
    }

    .top-actions {
        flex-wrap: wrap;
    }
}

@media (max-width: 700px) {
    .sidebar {
        transform: translateX(-100%);
        transition: transform 0.3s;
        box-shadow: none;
    }

    .sidebar.show {
        transform: translateX(0);
        box-shadow: 5px 0 25px #0002;
    }

    .main-content {
        margin-left: 0;
        width: 100%;
        padding: 18px 14px;
    }

    .menu-btn {
        display: block;
    }

    .topbar {
        align-items: flex-start;
    }

    .topbar h2 {
        font-size: 19px;
    }

    .topbar p {
        line-height: 1.5;
    }

    .top-actions {
        width: 100%;
    }

    .top-actions input {
        flex: 1;
        min-width: 100px;
    }

    .welcome {
        align-items: flex-start;
        flex-direction: column;
        padding: 22px;
    }

    .welcome h1 {
        font-size: 20px;
    }

    .stats {
        gap: 10px;
    }

    .stat-card {
        padding: 15px;
    }

    .stat-card h2 {
        font-size: 24px;
    }

    .stat-card small {
        line-height: 1.5;
    }

    .panel {
        padding: 15px;
    }

    .panel-heading {
        flex-wrap: wrap;
    }

    .task-row {
        align-items: flex-start;
        flex-wrap: wrap;
    }

    .task-row select {
        width: auto;
    }

    .date {
        white-space: normal;
    }
}
</style>
<script>
const defaultProjects = [
    { name: "Website Development", progress: 75 },
    { name: "Mobile App Design", progress: 50 },
    { name: "Marketing Campaign", progress: 90 },
    { name: "Dashboard UI Design", progress: 35 }
];

const defaultTasks = [
    { id: 1, name: "Design homepage", project: "Website Development", status: "Completed" },
    { id: 2, name: "Create login page", project: "Website Development", status: "In Progress" },
    { id: 3, name: "Build dashboard UI", project: "Dashboard UI Design", status: "To Do" },
    { id: 4, name: "Prepare marketing plan", project: "Marketing Campaign", status: "In Progress" },
    { id: 5, name: "Test mobile layout", project: "Mobile App Design", status: "To Do" },
    { id: 6, name: "Review final design", project: "Dashboard UI Design", status: "Completed" }
];

let projects = JSON.parse(localStorage.getItem("pmProjects")) || defaultProjects;
let tasks = JSON.parse(localStorage.getItem("pmTasks")) || defaultTasks;

function saveData() {
    localStorage.setItem("pmProjects", JSON.stringify(projects));
    localStorage.setItem("pmTasks", JSON.stringify(tasks));
}

function renderProjects() {
    const list = document.getElementById("projectList");

    list.innerHTML = projects.map((project, index) => `
        <div class="project">
            <div class="project-info">
                <strong>${escapeHTML(project.name)}</strong>
                <span>${project.progress}%</span>
            </div>
            <div class="progress">
                <div style="width:${project.progress}%"></div>
            </div>
            <button class="text-btn" onclick="editProject(${index})">Edit</button>
            <button class="text-btn" onclick="deleteProject(${index})">Delete</button>
        </div>
    `).join("");

    document.getElementById("totalProjects").textContent = projects.length;
}

function renderTasks() {
    const list = document.getElementById("taskList");
    const filter = document.getElementById("statusFilter").value;
    const search = document.getElementById("search").value.toLowerCase();

    const filteredTasks = tasks.filter(task =>
        (filter === "All" || task.status === filter) &&
        (task.name.toLowerCase().includes(search) ||
         task.project.toLowerCase().includes(search))
    );

    list.innerHTML = filteredTasks.map(task => `
        <div class="task-row">
            <div>
                <strong>${escapeHTML(task.name)}</strong>
                <small>${escapeHTML(task.project)}</small>
            </div>
            <div>
                <select aria-label="Status for ${escapeHTML(task.name)}"
                    onchange="changeStatus(${task.id}, this.value)">
                    ${["To Do", "In Progress", "Completed"].map(status =>
                        `<option value="${status}" ${task.status === status ? "selected" : ""}>${status}</option>`
                    ).join("")}
                </select>
                <button class="text-btn" onclick="editTask(${task.id})">Edit</button>
                <button class="text-btn" onclick="deleteTask(${task.id})">×</button>
            </div>
        </div>
    `).join("") || "<p>No tasks found.</p>";

    document.getElementById("totalTasks").textContent = tasks.length;
    document.getElementById("completedTasks").textContent =
        tasks.filter(task => task.status === "Completed").length;
    document.getElementById("pendingTasks").textContent =
        tasks.filter(task => task.status !== "Completed").length;

    saveData();
}

function addTask() {
    const name = prompt("Enter task name:");
    if (!name || !name.trim()) return;

    const project = prompt("Enter project name:", projects[0]?.name || "General");
    if (project === null) return;

    tasks.unshift({
        id: Date.now(),
        name: name.trim(),
        project: project.trim() || "General",
        status: "To Do"
    });

    saveData();
    renderTasks();
}

function editTask(id) {
    const task = tasks.find(item => item.id === id);
    if (!task) return;

    const name = prompt("Edit task name:", task.name);
    if (name === null || !name.trim()) return;

    task.name = name.trim();

    const project = prompt("Edit project name:", task.project);
    if (project !== null && project.trim()) task.project = project.trim();

    renderTasks();
}

function deleteTask(id) {
    if (!confirm("Are you sure you want to delete this task?")) return;
    tasks = tasks.filter(task => task.id !== id);
    renderTasks();
}

function changeStatus(id, status) {
    const task = tasks.find(item => item.id === id);
    if (task) task.status = status;
    renderTasks();
}

function addProject() {
    const name = prompt("Enter new project name:");
    if (!name || !name.trim()) return;

    projects.push({ name: name.trim(), progress: 0 });
    saveData();
    renderProjects();
}

function editProject(index) {
    const project = projects[index];
    const name = prompt("Edit project name:", project.name);
    if (name === null || !name.trim()) return;

    const progress = prompt("Enter progress (0-100):", project.progress);
    if (progress === null) return;

    const value = Number(progress);
    if (!Number.isFinite(value) || value < 0 || value > 100) {
        alert("Progress must be between 0 and 100.");
        return;
    }

    project.name = name.trim();
    project.progress = value;
    renderProjects();
    renderTasks();
}

function deleteProject(index) {
    if (!confirm("Delete this project? Tasks will not be deleted.")) return;
    projects.splice(index, 1);
    saveData();
    renderProjects();
}

function toggleTheme() {
    document.body.classList.toggle("dark");
    localStorage.setItem(
        "pmTheme",
        document.body.classList.contains("dark") ? "dark" : "light"
    );
}

function toggleSidebar() {
    document.getElementById("sidebar").classList.toggle("show");
}

function escapeHTML(value) {
    return String(value).replace(/[&<>"']/g, char => ({
        "&": "&amp;",
        "<": "&lt;",
        ">": "&gt;",
        '"': "&quot;",
        "'": "&#39;"
    })[char]);
}

document.getElementById("search").addEventListener("input", renderTasks);

document.getElementById("today").textContent =
    new Date().toLocaleDateString("en-PK", {
        day: "numeric",
        month: "short",
        year: "numeric"
    });

if (localStorage.getItem("pmTheme") === "dark") {
    document.body.classList.add("dark");
}

renderProjects();
renderTasks();
</script>
