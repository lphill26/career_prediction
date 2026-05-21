# Problem Statement 
    An analysis on students statstics of age, gender, education, skills to determine if they will get a placement.

# Data Cleaning 
    Load the data: df = pd.read_csv('Student_Placement_Career_Prediction_Dataset.csv')
    Explotoray Data Analysis: df.head(), df.info(), df.describe()
    Checking for null values: df.isna().sum()
    Checking fr duplicates: df.duplicated().sum()

# Percentile Distributions of Numerical Columns
    df['numerical column'].quantile([0.1,0.25,0.5,0.75])

# Analysis of Categorial Columns
    df['categorial column'].value_counts()
    df['categorial column'].nunique()

# Comparsions Across Categories 
    Grouping placement status by age: df.groupby('placement_status')['age'].agg(['mean', 'median', 'count'])
    Grouping placement status by cgpa: df.groupby('placement_status')['cgpa'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by number of internerships: df.groupby('placement_status')['internship_count'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by number of projects: df.groupby('placement_status')['project_count'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by number of certifications: df.groupby('placement_status')['certifications_count'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by coding skills score: df.groupby('placement_status')['coding_skills_score'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by number of communications: df.groupby('placement_status')['communication_skills_score'].agg(['mean', 'median', 'min', 'max'])
    Grouping placement status by number of soft skills: df.groupby('placement_status')['soft_skills_score'].agg(['mean', 'median', 'min', 'max'])

# Asociation Between Categories 
    pd.crosstab(df['hackathon_participation'], df['placement_status'])
    pd.crosstab(df['branch'], df['placement_status'])
    pd.crosstab(df['gender'], df['placement_status'])

# Visualizations 
    Histogram: df['internship_count'].hist()
    Bar chart of branch of education: df['placement_status'].value_counts().plot(kind='bar')
    Boxplot grouped by the number of interships and placement status: df.boxplot(column='internship_count', by='placement_status')
    Correlation Heatmap: df.corr(numeric_only=True).style.background_gradient(cmap='coolwarm')

# Results 
    5074 students have received a placement and 4926 students did not get placed. 
    2442 Female student got placed and 2574 did not get placed.
    2484 Male students got placed and 2500 did not get placed. 
    23 is the average age of students who received a placement. 
    Students with a cgpa of 8.0 or higher received a placement, 6.0 or lower cgpa students did not get placed.
    Students with 2 or more internships got placed, 1 or less internships did not get placed. 
    Students with 4 or more personal projects received a placement, while 3 or less did not get placed.
    Students with 3 or more certifications received a placement, while 2 or less did not get placed.
    Students with a coding score of 72 or more received a placement, while 71 or less did not get placed.
    Students with a communication score of 71 or more received a placement, while 70 or less did not get placed.
    Students with a soft skill score of 71 or more received a placement, while 70 or less did not get placed.
