# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles?

To find the top most demanded skills for the top 3 most popular data roles . I filtered out those positions by which ones were the most Popular, and got top  5 skills for these 3 roles . this query highlights the most popular job titles and their top skills , showing which skills I should pay attention to depending on the role I'm targeting. 

View my notebook with detailed steps here: 
[2_skill_Demand.ipynb](3_Project\2_Skill_Demand.ipynb)

### Visualize Data

```python
fig, ax =plt.subplots(len(job_titles), 1)


for i , job_title in enumerate(job_titles):
    df_plot=df_skills_perc[df_skills_perc['job_title_short']== job_title].head(5)
    sns.barplot(data=df_plot, x='skill_percent' , y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
    
plt.show()

```

### Results

![Visualization of Top Skills for Data Peoples](3_Project\skill_demand_all_data_roles.png)


### Insights

- Python is a must-have skill across all roles, particularly for Machine Learning Engineers.
- SQL is crucial for both Data Engineers and Data Scientists.
- Specific tools like AWS for Data Engineers, R for Data Scientists, and TensorFlow/PyTorch for Machine Learning Engineers add significant value.