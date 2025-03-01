# 🚀 Git Assignment Guide

## 📋 Project Description
This repository contains a step-by-step implementation of various Git workflows and features. The project includes a basic calculator application with arithmetic operations, a geometry calculator for calculating areas of different shapes, and demonstrates Git LFS for handling large files. This assignment showcases best practices for branching, merging, collaboration, and version control.

## 🛠️ Prerequisites
- ✨ Git installed on your local machine
- 🌐 GitHub account
- 🐍 Basic knowledge of Python
- 📦 Git LFS installed (for Question 2)
- 💻 Access to terminal or command prompt

## 📁 Project Structure
```
git_assignment_HeroVired/
├── .git/                  # Git repository data
├── .gitattributes         # Git LFS configuration file
├── calculator.py          # Basic calculator implementation
├── geometry_calculator.py # Geometry calculator implementation
└── README.md              # Project documentation
```

## 🌿 Branches
- 🟢 `main` (default)
- 🛠️ `dev`
- 🔴 `feature/circle-area`
- 📏 `feature/rectangle-area`
- 🧮 `feature/sqrt`
- 📐 `geometry-calculator`
- 📦 `lfs`

## ✅ Question 1: Setup & Basic Git Workflow

### 📝 Create a GitHub Repository
1. **🔑 Login to GitHub**
   - Navigate to GitHub.com and sign in
   - Click the "+" in top-right corner → "New repository"

2. **⚙️ Configure Repository**
   - Name: `git_assignment_HeroVired`
   - Visibility: Private
   - ✅ Initialize with README

3. **📥 Clone to Local Machine**
   ```
   git clone https://github.com/yourusername/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   ```

4. **🌱 Create Development Branch**
   ```
   git checkout -b dev
   ```

5. **💻 Add Calculator Code**
   I've created `calculator.py`:
   ```python
   import math
   class Calculator:
       def add(self, a, b):
           return a + b

       def subtract(self, a, b):
           return a - b

       def multiply(self, a, b):
           return a * b

       def divide(self, a, b):
           return a / b

   if __name__ == "__main__":
       calculator = Calculator()
       num1 = 16
       num2 = 4
       
       print(f"{num1} + {num2} = {calculator.add(num1, num2)}")
       print(f"{num1} - {num2} = {calculator.subtract(num1, num2)}")
       print(f"{num1} * {num2} = {calculator.multiply(num1, num2)}")
       print(f"{num1} / {num2} = {calculator.divide(num1, num2)}")
   ```

6. **📤 Commit & Push Changes**
   ```
   git add .
   git commit -m "Added initial calculator code"
   git push origin dev
   ```

7. **🔄 Merge & Tag Release v1.0**
   ```
   git checkout main
   git merge dev
   git push origin main
   git tag v1.0
   git push origin v1.0
   ```

### 👥 Add a Collaborator

1. I've gone to repository → Settings → Collaborators ⚙️
2. I've clicked "Add people" and entered Jasmine's GitHub username 👩‍💻
3. I've sent an invitation with a message: "In collaboration with Jasmine for the Git assignment" 📨
4. I've waited for Jasmine to accept the invitation ✅

### 🧮 Add Square Root Feature

1. **🌱 Create Feature Branch**
   ```
   git checkout -b feature/sqrt
   ```

2. **➕ Add Square Root Method**
   I've added the square root method:
   ```python
   def square_root(self, x):
       return math.sqrt(x)
   
   # Add to main section:
   num3 = 25
   print(f"The square root of {num3} = {calculator.square_root(num3)}")
   ```

3. **💾 Commit & Push Feature**
   ```
   git add .
   git commit -m "Implement square root function"
   git push origin feature/sqrt
   ```

4. **🐛 Fix Bug in Dev Branch**
   ```
   git checkout dev
   git pull origin dev
   ```

   I've updated the divide method:
   ```python
   def divide(self, a, b):
       if b == 0:
           raise ValueError("Cannot divide by zero.")
       return a / b
   ```

   ```
   git add .
   git commit -m "Fix divide by zero bug"
   git push origin dev
   ```

5. **🔄 Update Feature Branch**
   ```
   git checkout feature/sqrt
   git merge dev
   git push origin feature/sqrt
   ```

6. **🔀 Create Pull Request**
   - I've gone to GitHub → Pull Requests → New Pull Request 📝
   - Base: `dev` ← Compare: `feature/sqrt`
   - I've created a PR with a detailed description 📋
   - I've requested Jasmine to review the PR 👀

7. **🔀 Merge to Dev After Approval**
   ```
   git checkout dev
   git merge feature/sqrt
   git push origin dev
   ```

8. **🏷️ Release v2.0**
   ```
   git checkout main
   git merge dev
   git push origin main
   git tag v2.0
   git push origin v2.0
   ```

## 📦 Question 2: Git LFS for Large Files

### 💿 Install Git LFS

**🖥️ Windows:**
```
git lfs install
```

**🐧 Linux/Ubuntu:**
```
sudo apt install git-lfs
git lfs install
```

### 🗃️ Setup Repository for LFS

1. **📥 Clone & Create Branch**
   ```
   git clone https://github.com/yourusername/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   git checkout -b lfs
   ```

2. **⚙️ Configure File Tracking**
   ```
   git lfs track "*.zip"
   # or track specific file:
   git lfs track "IDM.zip"
   ```

3. **📤 Add & Commit Files**
   I've added:
   ```
   git add .gitattributes
   git add IDM.zip
   git commit -m "Added large file using Git LFS"
   git push origin lfs
   ```

4. **✅ Verify LFS Tracking**
   ```
   git lfs ls-files
   ```

5. **🧪 Test Clone on Another Machine**
   ```
   git clone https://github.com/yourusername/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   git checkout lfs
   git lfs pull
   ```

## 📐 Question 3: Geometry Calculator with Feature Branches

### 🏗️ Initial Setup

1. **📥 Clone & Create Base Branch**
   ```
   git clone https://github.com/yourusername/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   git checkout main
   git checkout -b geometry-calculator
   ```

2. **💻 Create Base Calculator**
   I've created `geometry_calculator.py`:
   ```python
   import math

   class GeometryCalculator:
       def calculate_circle_area(self, radius):
           return math.pi * radius ** 2

       def calculate_rectangle_area(self, length, width):
           return length * width

   if __name__ == "__main__":
       calculator = GeometryCalculator()
   ```

### ⭕ Circle Area Feature

1. **🌱 Create Feature Branch**
   ```
   git checkout -b feature/circle-area
   ```

2. **🔴 Implement Circle Area**
   I've added to the main section:
   ```python
   radius = 5
   print(f"The area of the circle with radius {radius} = {calculator.calculate_circle_area(radius)}")
   ```

3. **💾 Save Work in Progress**
   ```
   git stash
   git status  # verify clean working directory
   ```

### 📏 Rectangle Area Feature

1. **🌱 Create Feature Branch**
   ```
   git checkout -b feature/rectangle-area
   ```

2. **📐 Implement Rectangle Area**
   I've added to the main section:
   ```python
   length = 10
   width = 6
   print(f"The area of the rectangle with length {length} and width {width} = {calculator.calculate_rectangle_area(length, width)}")
   ```

3. **💾 Save Work in Progress**
   ```
   git stash
   git status  # verify clean working directory
   ```

### 🔄 Complete & Submit Features

1. **⭕ Complete Circle Feature**
   ```
   git checkout feature/circle-area
   git stash pop
   git add .
   git commit -m "Implemented circle area calculation"
   git push origin feature/circle-area
   ```

2. **📏 Complete Rectangle Feature**
   ```
   git checkout feature/rectangle-area
   git stash pop
   git add .
   git commit -m "Implemented rectangle area calculation"
   git push origin feature/rectangle-area
   ```

3. **🔀 Create Pull Requests**
   - I've created a PR: `feature/circle-area` → `dev` 📝
   - I've created a PR: `feature/rectangle-area` → `dev` 📝

4. **👀 Code Review Process**
   - I've requested Jasmine to review my PRs 🔍
   - I've added a comment: "In collaboration with Jasmine" 💬
   - I've addressed feedback from Jasmine 📝
   - I've merged PRs to `dev` after approval ✅

5. **🚀 Final Integration**
   ```
   git checkout main
   git merge dev
   git push origin main
   ```

### 📋 Workflow Summary

| Step | Command | Purpose |
|------|---------|---------|
| 📥 Clone repository | `git clone` | Get local copy |
| 📐 Create calculator branch | `git checkout -b geometry-calculator` | Base branch |
| ⭕ Create circle feature | `git checkout -b feature/circle-area` | Feature branch |
| 💾 Save circle changes | `git stash` | Store temporarily |
| 📏 Create rectangle feature | `git checkout -b feature/rectangle-area` | Feature branch |
| 💾 Save rectangle changes | `git stash` | Store temporarily |
| ⭕ Complete circle feature | `git checkout feature/circle-area && git stash pop` | Resume work |
| 📤 Push circle feature | `git push origin feature/circle-area` | Share with team |
| 📏 Complete rectangle feature | `git checkout feature/rectangle-area && git stash pop` | Resume work |
| 📤 Push rectangle feature | `git push origin feature/rectangle-area` | Share with team |
| 👀 Review & merge | Pull Requests | Quality control |
| 🚀 Release | Merge to main | Production ready |

### 📊 Expected Output

```
The area of the circle with radius 5 = 78.53981633974483
The area of the rectangle with length 10 and width 6 = 60
```

## 🤝 Collaboration

### *In collaboration with Jasmine* 👩‍💻

Throughout this project, I've worked closely with Jasmine to implement the Git workflow and features. Jasmine has:
- 👀 Reviewed my pull requests for the calculator features
- 💬 Provided feedback on my code implementation
- 🧪 Helped test the geometry calculator functionality
- 📦 Collaborated on the Git LFS setup

This collaboration demonstrates effective teamwork using Git's branching and review features, allowing us to work independently while maintaining code quality through peer reviews. 🌟
