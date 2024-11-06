# DE1_project
## Analytics Plan Document: Spy Agency Dataset
## Elene Zuroshvili

### 1. Project Goal
The goal of this project is to derive meaningful insights regarding agent performance, mission
success, skill proficiencies, team effectiveness, and the impact of affiliations and security
clearances on mission outcomes. By consolidating and analyzing data, I aim to answer key
analytical questions and generate metrics to support informed decision-making.

### 2. Key Analytical Questions
   
2.1 Agent Performance
• Which agents have the highest mission success rates?
• How does agent performance vary based on their affiliations, skills, and team
assignments?

2.2 Affiliation Strength
• How do different affiliations affect mission outcomes?
• Is there a correlation between the strength of an agent’s affiliation and their
success rate?

2.3 Skill Proficiency
• What skills are most prevalent among top-performing agents?
• Do agents with specific skill sets consistently perform better in missions?

2.4 Team Effectiveness
• Which teams have the highest success rates?
• How does the team composition affect the overall success of missions?

2.5 Mission Success
• What factors contribute most to successful missions?
• Does having a higher security clearance or proficiency in multiple languages impact
the success rate?

2.6 Security Clearances and Mission Access
• What levels of security clearance are most common for high-profile missions?
• Is there a link between higher security clearances and mission success?

2.7 Language Proficiency
• Do agents with proficiency in multiple languages have a higher success rate in
missions?

### 3. Metrics to Measure
   
3.1 Agent Performance Metrics
• Total Missions Assigned
• Successful Missions Count
• Average Salary
• Affiliations Count and Strength

3.2 Affiliation Impact Metrics
• Affiliations Count per Agent
• Average Affiliation Strength by Agent
• Average Mission Success Rate by Affiliation

3.3 Skill Proficiency Metrics
• Total Skills per Agent
• Most Prevalent Skills among Successful Agents

3.4 Team Success Metrics
• Total Missions per Team
• Mission Success Rate by Team

3.5 Language Proficiency Metrics
• Total Languages per Agent
• Average Mission Success Rate by Language Proficiency

3.6 Security Clearance Metrics
• Average Security Clearance Level by Mission
• Mission Success Rate by Security Clearance

### 4. Analytical Data Layer Planning
   
4.1 Goals of the Analytical Data Layer
• Consolidate data from various tables into denormalized structures.
• Facilitate efficient querying for analytics and reporting.
• Ensure data consistency and accuracy across analytical tables.

4.2 Analytical Tables to Create
• Agent Performance Table: Contains aggregated mission statistics for each agent,
including mission counts, success rates, team involvement, and salary information.
• Skill Proficiency Table: Aggregates skill information for each agent, providing a
count of the total skills each agent possesses.
• Mission Summary Table: Summarizes mission details and links them with
corresponding agents, teams, and security clearances.
• Team Effectiveness Table: Contains mission outcomes and team success rates to
analyze team performance.

### 5. ETL (Extract, Transform, Load) Planning
   
5.1 ETL Process Steps

1. Extract:
• Extract relevant data from the operational tables (agent, mission, team,
skill_relationship, affiliation_relationship, language_relationship, and security_clearance) to prepare
for transformation. This step involves selecting key columns and filtering rows that are relevant for
analytics.
2. Transform:
• Agent Performance Metrics: Calculate the total number of missions each agent has
participated in, the number of successful missions, the number of teams they have been a part of,
and their average salary.
• Affiliation Metrics: Measure the number of affiliations per agent and the strength of
each affiliation. Aggregate and calculate the average success rate by affiliation strength.
• Skill Proficiency Metrics: Calculate the number of skills each agent possesses and
identify the most common skills among top-performing agents.
• Team Effectiveness Metrics: Measure the total number of missions each team has
completed and their success rates.
• Language Proficiency Metrics: Identify the number of languages each agent speaks
and measure the success rate of agents who are proficient in multiple languages.
• Security Clearance Metrics: Measure the average security clearance level required
for each mission and the success rate based on security clearance levels.
3. Load:
• Insert or update the transformed data into analytical tables such as
agent_performance, skill_proficiency, team_success, affiliation_metrics, and mission_summary.
This ensures that the analytical layer is up-to-date with the latest information.

5.2 ETL Implementation
Stored Procedures and Triggers will be used to automate the ETL process. Here’s how each
element will work:

Stored Procedures for Transformation and Loading:
   
• Procedure for Updating Agent Performance Table: This stored procedure will
extract agent data, join it with mission and team data, and calculate key performance metrics for
each agent. It will then insert or update the agent_performance table.
• Procedure for Updating Skill Proficiency Table: This stored procedure will extract
agent and skill data, aggregate the number of skills per agent, and update the skill_proficiency
table.
• Procedure for Updating Team Effectiveness Table: This stored procedure will join
mission and team data to calculate mission success rates for each team and update the
team_success table.
• Procedure for Updating Affiliation Metrics Table: This procedure will extract
affiliation relationships, measure affiliation strength, and update the affiliation_metrics table.
• Procedure for Updating Mission Summary Table: This procedure will extract data
from the mission, agent, and security_clearance tables to create a consolidated summary of each
mission.

### 6. Data Mart Planning
   
6.1 Designing Data Marts
• Agent Performance Data Mart: A view that displays key performance metrics for
each agent, including total missions, successful missions, affiliations, and average salary.
• Team Effectiveness Data Mart: A view that shows team mission counts and
success rates.
• Mission Success Data Mart: A view that displays mission success rates by factors
such as security clearance, team, and agent proficiency.
