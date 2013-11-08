Feature: Updating Financial Aid Requirements
	As an administrator
	So I can update student financial aid requirements
	I want to update student requirements
	
Background: Contact in Database

	Given the following contact exists:
	| first_name | last_name | email            | address   | town    | countY  | post_code | telephone   |
	| John       | Doe       | john@example.com | 1 Sum St. | ATown   | Sumwhere| 12345     | 000-000-0000|

Background: Student Status Details in Database

	Given the student submitted the FAFSA:
	| FAFSA_submit | level       | military  | Date_of_Birth| Admitted  | FA_Award | Requirements | 
	| Yes          | Undergrad   | No        | 01/01/1991   | Yes       | Offered  | Unsatisfied  |	

Background: Student's Financial Aid Award Offer

	Given the student completed accepting/declining all awards:
	| Pell_Grant   | HPU_Grant   | Fed_Unsub_Loan | Fed_Sub_Loan | Fed_Parent_Loan | Scholarship | 
	| Accept       | Accept      | Declined       | Accept       | Accept          | Accept      |

Background: Financial Aid Requirements
	
	Given the following student submits Parent Tax Transcript and completely accepted/declined awards:
	| Award_Package | Dep_Verif   | Loan_Entrance | Scholar_Agree | ParentLoan_App | Parent_Tax_Trans |
	| Satisfied     | Satisfied   | Unsatisfied   | Satisfied     | Unsatisfied    | Unsatisfied      |
	
Scenario: Update student status
	When I go to the student details page
	And I fill in "StudentID" with "@01012222"
	Then I should see "John Doe, john@example.com, 1 Sum St., ATown, Sumwhere, 12345, 000-000-0000"
	And when I go to financial aid award page
	Then I should see "Accept, Accept, Declined, Accept, Accept, Accept"
	And when I go to financial aid requirements page
	Then I should see "Satisfied, Satisfied, Unsatisfied, Satisfied, Unsatisfied, Unsatisfied"
	And when I go to financial aid requirements page details
	And I fill in "Parent_Tax_Trans" with "Received"
	Then I should see "Satisfied, Satisfied, Unsatisfied, Satisfied, Unsatisfied, Received"
	But I should not see "Unsatisfied" in "Parent_Tax_Trans" requirement
