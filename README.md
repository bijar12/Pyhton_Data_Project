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

![Visualization of Top Skills for Data Peoples](3_Project\Images\skill_demand_all_data_roles.png)


### Insights

- Python is a must-have skill across all roles, particularly for Machine Learning Engineers.
- SQL is crucial for both Data Engineers and Data Scientists.
- Specific tools like AWS for Data Engineers, R for Data Scientists, and TensorFlow/PyTorch for Machine Learning Engineers add significant value.


# The Analysis

## 2. How are in-demand skills trending for data Scientist?

```python
df_plot_pak=df_DS_Pak_percent.iloc[: , :5]

sns.lineplot(data=df_plot_pak, dashes=False , palette='tab10')



from matplotlib.ticker import PercentFormatter
ax=plt.gca()
ax.yaxis.set_major_formatter(PercentFormatter(decimals=0))


plt.show()

```
### Results

![Trending Top Skills for Data Scientist in Pakistan](3_Project\Images\Skill_Trend_DS.png)
*Line graph Visualizing the trending top skills for Data Scientist in Pakistan in 2023*


### Insights:

- **Python**: Consistently the most in-demand skill, peaking multiple times throughout the year.
- **SQL**: Another highly sought-after skill, with consistent demand that peaks around November and March.
- **R**: Shows moderate demand, with notable fluctuations, especially between June and August.
- **Hadoop**: Experiences a significant decline in demand, especially from May to August, with brief recoveries.
- **Tableau**: Least demanded skill among the top 5, with very low demand throughout the year and a notable drop after February.

This graph highlights the fluctuating demand for these key skills, with Python and SQL being consistently dominant throughout the year.





