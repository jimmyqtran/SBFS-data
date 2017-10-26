## <span style="color: #F27802">Accessing and Interpreting Thumbtack's Small Business Friendliness Survey Data</span>
### NOTE: use of this data requires citing Thumbtack and linking to [Thumbtack.com](https://www.thumbtack.com). For more, see the [data license](https://github.com/thumbtack/SBFS-data/blob/master/SBFS%20Data%20License.pdf).
### Table of Contents   
1. [Overview of Thumbtack's Small Business Friendliness Survey (SBFS)](#summary)     
    * [What is SBFS?](#what-is-sbfs?)     
    * [How the data is collected](#how-the-data-is-collected)    
    * [How the data is measured](#how-the-data-is-measured)      
    * [How the data is stored](#how-the-data-is-stored)   
2. [Data Dictionary and Sources](#data-dictionary-and-sources)   
    * [Data Description](#data-description)   
    * [Data Source](#data-source)     
    * [Methodology](#methodology)     

<!-- toc -->
    
### Overview of Small Business Friendliness Survey (SBFS)     
#### What is the SBFS?

Conducted since 2012, the [Thumbtack Small Business Friendliness Survey](https://www.thumbtack.com/survey) is the largest continuous study of small business perceptions of government policy in the United States. The 2017 study reached 13,284 small business owners in all fifty states, including electricians, music teachers, wedding planners, wellness professionals, and others operating in a variety of industries. Based on these survey responses, we grade states and metropolitan areas on 11 dimensions, such as ease of hiring, workforce training opportunities, and licensing regulation burdens.
                      
#### How is the data collected?

We collect this by administering an online survey once a year to the small business owners and operators to that use Thumbtack.com to find new customers. Responses that complete less than half of the survey are thrown out.
                                                           
#### How is the data is measured?
                                                           
The grades we assign are based on the evaluations of the small business owners that completed our survey. Their responses to ordinal survey questions are converted into numbers (e.g. very unsupportive = 1 and very supportive = 5), and the average was found for each city and state in which there were an adequate number of responses. Cities with relatively high average scores receive higher grades (e.g.,“A’s”)  and cities with lower scores receive lower grades (e.g., “D’s”).
                                                        
#### How is the data stored?
The data from our Small Business Friendliness Survey is publicly available via our interactive survey visualization, available at [thumbtack.com/survey](https://www.thumbtack.com/survey), and our [API](https://data.thumbtack.com/v1/friendliness/grades-ranks), which stores the data in JSON format. 

#### More Information
For more information about the survey, please review our full [methodology paper](https://www.thumbtack.com/survey/).
                                                                 
###Data Dictionary and Sources            
The survey asks a core set of economic and business questions every year. Each answer to these questions has a numerical code, as defined below:
                                                                 

#### Data Source: Friendliness Data 
https://data.thumbtack.com/v1/friendliness/grades-ranks       
This data, defined on either the state or city (CBSA) level, is a composite score of economic expecations among the small business owner-operators we heard from in the given period. The data in this section are structured as follows:

#####State Level Data                                                                 
Field         | Definition      
------------- | -------------       
`id`          | (int) numeric value for a given state     
`name`        | (chr) state's name   
`rank`        | (int) state’s numeric rank for corresponding category  
`value`       | (chr) state’s grade for corresponding category
`grade`       | (chr) state’s grade for corresponding category   
`category`    | (int) numeric representation of a policy category/question
`year`        | (chr) year of survey result 
`type`        | (chr) type of value recorded


#####City Level Data                                                                 
Field         | Definition      
------------- | -------------       
`id`          | (chr) city name     
`rank`        | (int) city’s numeric rank for corresponding category   
`value`       | (chr) city’s grade for corresponding category      
`grade`       | (chr) city’s grade for corresponding category   
`category`    | (int) numeric representation of a policy category/question
`year`        | (chr) year of survey result 
`type`        | (chr) type of value recorded


#####Regional Level Data (Only available for 2012)                                                                
Field         | Definition      
------------- | -------------       
`id`          | (chr) region name     
`state`       | (int) numeric representation for corresponding state of the region     
`rank`        | (int) region’s numeric rank for corresponding category  
`value`       | (chr) region’s numeric rank for corresponding category
`category`    | (int) numeric representation of a policy category/question
`year`        | (chr) year of survey result 
`type`        | (chr) type of value recorded



                                                                
##### Policy Category / Questions: (`grade`)
The following section defines `grade` and matches its subject heading on the survey site to the survey questions and answers it corressponds to. For example, `Overall friendliness` is the subject heading on the survey site, which corresponds to `grade = 1` and the question "In general, how would you rate your state's support of small business owners?", which is answered on an ordinal scale and converted into numbers (e.g. very unsupportive = 1 and very supportive = 5).   


Category Value | Category Subject             | Question                                                                      | Grade  (applies to all questions)
-------------- | ----------------             | ---------------------------                                                   | ----------------------------------
`1`            | Overall friendliness         | In general, how would you rate your state's support of small business owners? | `A` `A+` `A-` `B` `B+` `B-` `C` `C+` `C-` `D` `D+` `D-` `F`   
`2`            | Ease of starting a business  | How difficult or easy do you think it is to start a business in your state?   |               
`6`            | Regulations                  | How unfriendly or friendly is your state or local government with regard to business regulations generally? | 
`7`            | Health & safety              | How unfriendly or friendly is your state or local government with regard to health and safety regulations? | 
`8`            | Employment, labor & hiring   | How unfriendly or friendly is your state or local government with regard to employment, labor and hiring regulations? |  
`9`            | Tax code                     | How unfriendly or friendly is your state or local government with regard to tax code and tax-related regulations? | 
`10`           | Licensing                    | How unfriendly or friendly is your state or local government with regard to licensing forms, requirements and fees? | 
`11`           | Environmental                | How unfriendly or friendly is your state or local government with regard to environmental regulations? | 
`12`           | Zoning                       | How unfriendly or friendly is your state or local government with regard to zoning or land use regulations? | 
`22`           | Ease of hiring               | How difficult or easy is it to hire a new employee at your business?          |
`23`           | Training & networking programs (available starting 2013) |  Does your state or local government offer helpful training or networking programs for small business owners? | 


                                                           
#### Curious to Learn More About The Data?
Check out the [SBFS survey website](https://www.thumbtack.com/survey) for an interactive view of this data and the [annual SBFS report](https://www.thumbtack.com/survey).
                                                                 
If you need help pulling this data into R or Python, we've create two tutorials to help you do so. You can access the R tutorial [here](https://github.com/thumbtack/SBFS-data/blob/master/README.md) and the Python tutorial [here](https://github.com/thumbtack/SBFS-data/blob/master/Python%20Tutorial.md).
                                                                 
                                                                 
