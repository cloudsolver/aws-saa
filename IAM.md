Identity and Access Management is a core #awsservice  Global Service.

### IAM User
- Users: mapped to a physical user, has a password for AWS Console
-  Many users can be created. 
- Principle of least privilege: give users only rights they need to do their job. #wellarchitected
Changes to IAM groups are live immediately. Policy can be attached directly, and by groups.
### IAM Group
- Groups: contains users only.
- Groups can be given permissions via IAM Policy.
### IAM Policy
- An IAM Policy is a JSON document that outlines permissions for users or groups.
	* Users or Groups can be assigned JSON documents called Policies.
	* Policies declare permissions. You can inherit policies, but not roles.
	* IAM Policy contains 'version'
	* IAM Policy Statement contains Sid, Effect, Principal, Action, Resources, and Condition.
	* `sid` is the statement identifier that describes the policy statement.
	#Q An IAM policy consists of one or more statements. A statement in an IAM policy consists of the following, EXCEPT:
	1. Effect
	2. Principal
	3. Version
	4. Action
	5. Resource
	Answer: This is a tricky question because the JSON contains everything listed. However, the version is at a higher level than the statement itself.
### IAM Role
IAM Roles for [EC2](EC2.md) instance or AWS Services.
	* IAM Role for Services:
	* Perform actions on your behalf 
	* Assign permissions to AWS services with IAM Roles e.g. [EC2](EC2.md) Instnace, Lambda, etc.
* Security: MFA + Password policy.
	* IAM password policies can be protected by requiring
	* Complexity: min length, specific character types, numbers, non-alphanumeric characters, expiration, prevent reuse and change password by user.
	* MFA: protect Root and IAM users. Password you know + Security device you own.
* Access Keys: CLI or SDK
* [[Audit]]: [[Credentials Report]] and [[Access Advisor]] 





#Q What happens when a user has restricted policy as well as a group that has permissions that override that restriction?
1. The policies
2.
#Q  Which of the following is an IAM Security Tool?
1. [[Credentials Report]]
2. IAM Root Account Manager
3. IAM Services Report
4. IAM Security Advisor
Answer: This is a tricky question because when the question is framed like a 'tool' you would want to pick IAM Securtiy Advisor thinking it is the IAM [Access Advisor](Access%20Advisor.md). However, that would be incorrect becauser there is no Security Advisor within IAM. There is a report that comes out of IAM i.e. [[Credentials Report]] - but it is not a tool. Is it? Well, I guess that's the answer for this question.



[[Cloud_Shell]] is handy.


### IAM Guidelines & Best Practices #bestpractice
1. Don't use root.
2. One physical user 
3. Assigne users to groups and assign permissions to groups
4. Strong password
5. MFA
6. Use Roles for permissions to AWS services
7. Use Access Keys for CLI SDK
8. [[Credentials Report]] for audit.
9. Use [Access Advisor](Access%20Advisor.md) to review policies and least priviledge adjustments. [[Access Advisor]] shows the services permissions granted to the user and when those services were last accessed. You can use this information to review your policies later.
10. AWS documented IAM best practices: [Click Here](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)