# What Do I Need For AWS Job?

There are three main groups of jobs related with AWS:
1. DevOps Engineer
2. Software/Cloud Engineer
3. Software/Cloud Architect

While not specific to AWS, the [DevOps Roadmap](https://roadmap.sh/devops) is incredibly useful in painting some context for the general learning of AWS concepts like EC2 and logs management and CI/CD tooling.

That being said, for DevOps position, here is a very general idea to get you started:
1. At least 1 major cloud associate level certification (AWS, Azure, GCP)</li>
2. At least 1 hands on with Ansible, Puppet, Chef, Salt</li>
3. At least 1 hands on with Docker or Kubernetes</li>
4. At least one scripting language, perf Python, JavaScript, Go, or Java</li>
5. At least 1 Windows or Linux, perf both</li>
6. An understanding of DevOps and Agile environments</li>

Software/Cloud Engineer is responsible for a business logic that is about to be implemented ([more in the definition](https://www.comptia.org/blog/your-next-move-cloud-engineer)). Since in such role, work on the actual code is being done, automation skills are not so important but a practical knowledge of tools that help you implement logic is necessary. That include:

1. Ability to use: EC2, ECS, EKS, Lambda for development work
2. Ability to use available databases and storage products to model and store data in:
    1. Relational databases like PostgreSQL, MariaDB
    2. NoSQL datastores like DynamoDB, DocumentDB, Redis, Elasticsearch
    3. S3
3. Asynchronous systems like SQS, SNS, Kafka
4. API platforms like API Gateway, AppSync
5. Big Data platforms like AWS EMR, Glue, Athena
6. Knowledge of CloudFront to optimize websites (if doing web development)

When searching for AWS jobs, there's a lot of offers for Cloud/Solution/Software Architect positions. In general, an architect at an IT project is _a software developer expert who makes high-level design choices and tries to enforce technical standards, including software coding standards, tools, and platforms._ [Software architect](https://en.wikipedia.org/wiki/Software_architect). Such role encompasses technical expert skills and soft skills, since communication across team members, representatives and across enterprise can be necessary. Usually an architect is a  distinguished developer with years of work experience across many projects. No single path leads to this role but [this paper](http://www0.cs.ucl.ac.uk/staff/A.Finkelstein/fose/finalgarlan.pdf) tries to sketch a roadmap.

Keep in mind, practice and experience are often more important than certificates:
[Why An AWS Certification Will Not Get You An AWS Job!](https://www.reddit.com/r/AmazonWebServices/comments/ga0tqc/why_an_aws_certification_will_not_get_you_an_aws/)

No two jobs will be the same. Find out the AWS position you want and then go research it on Indeed, LinkedIn, ZipRecruiter, CareerBuilder, GlassDoor, Monster. What appears on "most" of those job reqs is what you need to learn/know.

[Create better searches on those job sites!](https://business.linkedin.com/content/dam/me/business/en-us/talent-solutions/learning-center/tip-sheets/en-us/UseBooleanLogic.pdf)

You can find recruiters by doing fuzzy searches on keywords + location. Then follow or message said recruiter for future opportunities. From there you can also find the commonly used "recruiter hashtags" that are relevant to your area. Recruiters tend to use common hashtags for job postings (sometimes location dependent -- #awsToronto #awsSeattle)

[Where Do I Find Recruiters?](https://www.reddit.com/r/ITCareerQuestions/comments/f8bo3v/where_do_i_find_recruiters/)


# How Much Should I Make At x Position?

1. [Glassdoor](https://www.glassdoor.com/)

2. [LinkedIn Salary](https://www.linkedin.com/salary/)

3. [Payscale](https://www.payscale.com/)

4. CompTIA [IT Career Path](https://www.comptia.org/content/it-careers-path-roadmap)

5. CompTIA [Tech Town Index 2019](https://www.comptia.org/content/research/best-tech-cities-it-jobs)

6. [IT Career Roadmap 2020 by Salary](https://i.lensdump.com/i/iHcJHP.png) - credits to [/u/SinecureLife](https://www.reddit.com/r/ITCareerQuestions/comments/dbjkdx/oc_common_it_career_paths_roadmap_visual_2020/)


# How to write a good CV?

1. Try to keep information about you on one page and include:
    1. Your current title
    2. Short description of your skills
    3. Your experience, only relevant one for your position
    4. Your certificates, school (if relevant)
    5. GitHub profile if active

2. When listing experience, be concrete and precise; show what impact you had to the organization and provide measurable values e.g.
    1. Managing 5 AWS accounts in a process of company wide cloud migration process for 10 development teams
    2. Being technically responsible for 2 company products
    3. Developing organization wide CI/CD pipelines utilizing Serverless Functions (Lambda), Ansible, AWS APIs to 5 development teams

3. [Everybody lies](https://house.fandom.com/wiki/Everybody_lies), same as your competitors for a job; try to provide demonstrable information in the resume, it's easy to see if a person is not consistent

4. Forget cover letters if it's not a VP/SVP/Director level; if an organization asks for it at technical positions, it's a sign of a pathological organization (Google doesn't do cover letters at all)

5. If a company tries to do a reference check, that can be a signal of a pathological organization; don't bother getting references but try to understand reasons for them once asked

6. KISS, for technical roles that's fine to have even txt with your achievements

# How to architect and choose the best solution?

1. Figure out what the factors that are important to the organization are (it's rarely "cheapest possible" or "latest hype" option)

    1. If it is an improvement to an existing product, think about the existing project stakeholders and how the change will affect them
    
    2. If it is a new project, think about how the product will be used in production

2. Define and compare several approaches, follow [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)

3. You might want to follow [Well-Architected Framework](https://wa.aws.amazon.com/index.en.html) but take it with a grain of salt, use [YAGNI principle](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)


# Recommended Reddit posts

1. How To [Start a Career in Cloud Computing](https://www.reddit.com/r/ITCareerQuestions/comments/crn6qp/how_do_you_start_a_career_in_cloud_computing/ex7fg16/)

2. [How I Went From 14hr to 70k with no experience!](https://www.reddit.com/r/ITCareerQuestions/comments/bhfegj/how_i_went_from_14hr_to_70k_with_no_experience/)

3. [Tossing My Coin That Hat Too I'm A College Dropout](https://www.reddit.com/r/ITCareerQuestions/comments/gc9a1v/tossing_my_coin_that_hat_too_im_a_college_dropout/)
