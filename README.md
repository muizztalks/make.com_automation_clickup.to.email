# ClickUp Archive and Email Automation

This Make (formerly Integromat) scenario automates the process of archiving completed ClickUp tasks and sending an email summary once the process is complete. It is designed to streamline task maintenance and reporting for ClickUp users who regularly close and organize large volumes of tasks.

---

## Overview

**Workflow Name:** ClickUp Archive & Email  
**Platform:** [Make.com](https://www.make.com)  
**Primary Integration:** ClickUp API  

This automation performs the following sequence:

1. **Retrieve Completed Tasks**  
   The scenario connects to ClickUp and fetches all tasks marked as *complete* from a specified list or workspace.

2. **Iterate Through Tasks**  
   Each retrieved task is processed in sequence through an iterator.

3. **Archive Tasks**  
   The scenario uses the ClickUp "Edit Task" module to set the `archived` field to `true`, moving each completed task to the archive.

4. **Aggregate Results**  
   The IDs of all archived tasks are collected using a text aggregator for summary reporting.

5. **Send Summary Email**  
   After archiving, the system sends an automated email summarizing the archived tasks to the configured email address.

---

## Modules Used

| Step | Module | Purpose |
|------|---------|----------|
| 1 | **ClickUp: Get List Tasks** | Fetch all tasks with status set to `complete` |
| 2 | **Basic Feeder (Iterator)** | Loop through each task |
| 3 | **ClickUp: Edit a Task (Advanced)** | Archive each completed task |
| 4 | **Text Aggregator** | Combine all archived task IDs into a single text block |
| 5 | **Email: Send Me an Email** | Notify the user when archiving is complete |

---

## Configuration

### Prerequisites
- Active **ClickUp account** with API access
- Valid **Make.com** account
- Authorized **ClickUp connection** in Make
- Configured **email module** within Make for notifications

### Setup Instructions
1. Import the `scenario.blueprint.json` file into your Make dashboard.  
2. Connect your ClickUp account using OAuth or API token.  
3. Adjust the parameters in the **Get List Tasks** module:
   - `list_id`: your target ClickUp list ID  
   - `statuses`: set to `complete` or your equivalent closing status  
   - `limit`: optional task limit per run  
4. Confirm the **Edit Task** module uses the same connection and has `archived` set to `true`.  
5. Configure the **Email module** with your preferred recipient address.  
6. Run once manually to test and confirm successful execution.  
7. (Optional) Schedule the scenario to run periodically.

---

## Use Cases

- Automatically clean up completed tasks from active ClickUp boards  
- Maintain workspace performance by reducing visible task clutter  
- Generate automated email reports for team tracking or auditing  

---

## Developer

**Developed and maintained by:** Muizz Khan  
**Email:** [muizztalks@gmail.com](mailto:muizztalks@gmail.com)

---

## License

MIT License  
Copyright (c) 2025 Muizz Khan  

Permission is hereby granted, free of charge, to any person obtaining a copy  
of this software and associated documentation files (the "Software"), to deal  
in the Software without restriction, including without limitation the rights  
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
copies of the Software, and to permit persons to whom the Software is  
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in  
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN  
THE SOFTWARE.
