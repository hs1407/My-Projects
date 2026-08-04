# IBM HR Employee Attrition Analysis

## Project Overview

Employee attrition can increase recruitment costs, disrupt team productivity, and lead to the loss of valuable knowledge. This project analyzes employee data to understand whether overtime and job satisfaction are associated with an employee's decision to leave the company.

The analysis focuses on one primary hypothesis and one supporting hypothesis. The goal is to help Human Resources identify practical opportunities to improve employee retention and create a healthier work environment.

## Business Problem

The company is experiencing employee turnover but needs to better understand which workplace factors may be contributing to it. The main business questions are:

1. Are employees who work overtime more likely to leave the company?
2. Does lower job satisfaction contribute to higher employee attrition?

Answering these questions can help the company prioritize retention strategies, manage workloads more effectively, and improve the employee experience.

## Dataset Overview

The dataset contains 1,470 employee records and 35 workforce-related variables. It includes information about:

- Employee demographics
- Department and job role
- Overtime status
- Job satisfaction and work-life balance
- Monthly income and salary increases
- Years of experience and company tenure
- Employee attrition

The overall employee attrition rate in the dataset is 16.12%, representing 237 employees who left the company.

## Primary Hypothesis: Overtime and Attrition

**Employees who work overtime are more likely to leave the company than employees who do not work overtime.**

This may happen because frequent overtime can contribute to:

- Increased stress
- Poor work-life balance
- Physical and emotional burnout
- Lower job satisfaction
- Difficulty managing family or personal responsibilities

### Findings

| Overtime Status | Total Employees | Employees Who Left | Attrition Rate |
|---|---:|---:|---:|
| Yes | 416 | 127 | 30.53% |
| No | 1,054 | 110 | 10.44% |

Employees who worked overtime had an attrition rate approximately 2.9 times that of employees who did not work overtime. The difference between the two groups was 20.09 percentage points.

### Hypothesis Conclusion

The primary hypothesis is strongly supported by the data. Employees working overtime showed a substantially higher attrition rate, suggesting that workload pressure and reduced work-life balance may be important retention concerns. However, the results show an association and do not prove that overtime alone caused employees to leave.

## Supporting Hypothesis: Job Satisfaction and Attrition

**Employees with lower job satisfaction have higher attrition.**

Employees who are unhappy with their jobs may be more likely to:

- Search for better employment opportunities
- Feel unmotivated in their current roles
- Have lower engagement and commitment
- Feel that their expectations are not being met

### Findings

| Job Satisfaction Level | Total Employees | Employees Who Left | Attrition Rate |
|---|---:|---:|---:|
| 1 – Low | 289 | 66 | 22.84% |
| 2 – Medium-Low | 280 | 46 | 16.43% |
| 3 – Medium-High | 442 | 73 | 16.52% |
| 4 – High | 459 | 52 | 11.33% |

Employees in the two lower satisfaction groups had a combined attrition rate of 19.68%, compared with 13.87% among employees in the two higher satisfaction groups.

### Hypothesis Conclusion

The supporting hypothesis is generally supported. Employees with the lowest job satisfaction had the highest attrition rate, while employees with the highest satisfaction had the lowest rate. The relationship was not perfectly linear because satisfaction levels 2 and 3 had nearly identical attrition rates. This suggests that job satisfaction is relevant, but other factors may also influence an employee's decision to leave.

## Business Recommendations

1. **Reduce unnecessary overtime:** Review departments and job roles with frequent overtime, improve staffing and scheduling, and distribute workloads more evenly.
2. **Address low job satisfaction early:** Use regular employee feedback surveys, manager check-ins, and confidential discussions to identify concerns before employees disengage.
3. **Create a retention monitoring dashboard:** Track overtime, job satisfaction, and attrition by department and job role so HR can identify high-risk groups and measure whether retention initiatives are working.

## Overall Conclusion

The analysis identifies overtime as the strongest concern among the two factors studied. Employees working overtime were nearly three times more likely to leave than those not working overtime. Lower job satisfaction was also associated with higher attrition, although the pattern was less pronounced.

The company should prioritize workload management and work-life balance while also strengthening employee feedback and engagement programs. These actions may help reduce avoidable turnover, improve employee well-being, and support a more stable workforce.

## Project Scope and Limitation

This analysis is based on a single employee dataset without time-based information. The findings describe relationships between variables but do not establish cause and effect. Additional data, such as exit interview feedback, overtime hours, manager information, and historical attrition trends, would help the company make more precise decisions.
