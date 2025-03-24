# EasyTest - Running R in GitHub Codespaces

## 🚀 Setting Up GitHub Codespace

1. **Go to the R Dev Container Repository**  
   Navigate to the repository on GitHub.

2. **Start a GitHub Codespace**  
   - Click the **"Code"** button (green dropdown at the top right).
   - Select the **"Codespaces"** tab.
   - Click **"Create codespace"**.
   - Wait 2-3 minutes for initialization  

## 🖥️ Writing and Running R Code

1. **Create a New R Script**  
   - Inside VS Code (Codespaces), create a new file with a `fun_facts.R` extension.

2. **Attach R Terminal**  
   - Look at the bottom status bar
   - Click **"R (not attached)"**

3. **Write and Run R Code**  
   - Open your new `fun_facts.R` file and type a R command.

## Test

The following code make a matrix Mat and print its value. Below is the the code for Test:

```markdown
facts <- c(
  "R was created by Ross Ihaka and Robert Gentleman!",
  "The name 'R' comes from the first letters of its creators' names!",
  "R is used by 70% of data scientists worldwide!",
  "The first R version (1.0.0) was released in 2000!"
)

cat("Fun Fact: ", sample(facts, 1), "\n", sep = "")
```

Here is the screenshot of R session required for First Test

![image](https://github.com/user-attachments/assets/f801da59-25c7-47db-acaf-9bc2ee8db771)

