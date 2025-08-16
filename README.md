# Ai‑assistant

This repository contains JSON definitions for multiple specialized agents used in **n8n** workflows.  
Each agent is a self-contained tool designed to handle a specific type of task, allowing flexible and modular automation.

## Agents Overview

### 1. Assistant.json
Main **supervisor agent** that coordinates the execution of all other agents.  
It receives the user’s request, determines which sub-agent should handle it, and routes the query accordingly.

### 2. Calendar_agent.json
Agent for **calendar management**:
- Creates new events with date, time, and description.
- Updates or deletes existing events.
- Sends reminders about upcoming tasks or appointments.

### 3. Create_food_report.json
Agent for **nutrition reporting**:
- Collects food intake data for a given date range from the database.
- Summarizes daily calories, protein, fats, and carbohydrates.
- Creates a structured **Markdown** report with a **QuickChart** graph (pie chart for one day, line chart for a week).

### 4. Finance_agent.json
Agent for **financial queries**:
- Retrieves data about stocks, currency rates, or crypto prices.
- Can generate simple financial summaries based on provided parameters.

### 5. Food_assistant.json
Agent for **daily nutrition tracking**:
- Receives dish names or meal details from the user.
- Uses a nutrition API (e.g., **Nutritionix**) to calculate calories and macronutrients.
- Saves the data in **Supabase** in two tables:
  - **User profile** (contains daily calorie goal).
  - **Daily nutrition log** (calories, proteins, fats, carbs per day; stores 7 days for reports).
- If no entry exists for the current day, it creates one automatically.

### 6. Research_agent.json
Agent for **information retrieval and summarization**:
- Searches external sources for answers to user queries.
- Returns a concise and relevant summary.

---

## Usage
Each JSON file can be imported into n8n as a workflow node or subworkflow.  
You can combine them into a single assistant system or run them individually.

