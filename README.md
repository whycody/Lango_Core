# Lango_Core

**Lango_Core** is the central repository that integrates all the key components of the Lango platform.  
It serves as a monorepo, connecting different technologies and simplifying project management, environment setup, and deployment.

---

## Repository Structure

```
Lango_Core/
│
├── Lango/                → Mobile application (React Native)
├── Lango_NodeAPI/        → Node.js backend
├── Lango_FastAPI/        → Python backend (FastAPI)
├── docker-compose.yml    → Configuration for running all modules
├── .gitmodules           → Submodule configuration
└── README.md             → Documentation
```

---

## Submodules

The repository uses **Git submodules** to track all major components.  
Each submodule keeps its own commit history and can be developed independently.

---

### Cloning the Repository

To clone the repository along with all submodules:

```bash
git clone --recurse-submodules git@github.com:whycody/Lango_Core.git
```

If the repository was cloned without submodules:

```bash
git submodule update --init --recursive
```

---

### Updating Submodules

To update submodules to the latest commits on the `main` branch:

```bash
git submodule update --remote --merge
```

---

### Docker

The repository includes a shared `docker-compose.yml` file, allowing you to run all modules simultaneously:

```bash
docker-compose up --build
```

---

### Branch and Workflow

- Main branch: `main`  
- Each submodule tracks its own `main` branch.  
- Recommended workflow:  
  1. Update submodules (`git submodule update --remote --merge`)  
  2. Develop locally in the submodule  
  3. Commit changes in the submodule  
  4. Commit in Lango_Core to update the submodule reference
