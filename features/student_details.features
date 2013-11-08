Feature: Checking for Financial Aid Requirements
	As a user (student)
	So I can view student financial aid status
	I want to view financial aid requirements

Background: Contact in Database

	Given the following contact exists:
	| first_name | last_name | email            | address   | town    | countY  | post_code | telephone   |
	| John       | Doe       | john@example.com | 1 Sum St. | ATown   | Sumwhere| 12345     | 000-000-0000|

Background: Student Status Details in Database

	Given the following contact submitted the FAFSA:
	| FAFSA_submit | level       | Admitted   | FA_Award | Requirements | 
	| Yes          | Undergrad   | Yes        | Offered  | Unsatisfied  |	

Background: Financial Aid Award Offer

	Given the following contact was awarded:
	| Pell_Grant   | HPU_Grant   | Fed_Unsub_Loan | Fed_Sub_Loan | Fed_Parent_Loan | Scholarship | 
	| Accept       | Accept      | Offered        | Accept       | Accept          | Accept      |

Background: Financial Aid Requirements
	
	Given the following contact accepted/declined awards:
	| Award_Package | Dep_Verif   | Loan_Entrance | Scholar_Agree | ParentLoan_App | Parent_Tax_Trans |
	| Unsatisfied   | Satisfied   | Unsatisfied   | Satisfied     | Unsatisfied    | Unsatisfied      |

Scenario: Check my status
	When I go to the student details page
	And I fill in "StudentID" with "@01012222"
	Then I should see "John Doe, john@example.com, 1 Sum St., ATown, Sumwhere, 12345, 000-000-0000"
	And when I go to student status page
	Then I should see "Yes, Undergrad, Yes, Offered, Unsatisfied"
	And when I go to financial aid award page
	Then I should see "Accept, Accept, Offered, Accept, Accept, Accept"
	And when I go to financial aid requirements page
	Then I should see "Unsatisfied, Satisfied, Unsatisfied, Satisfied, Unsatisfied, Unsatisfied"

