# Multi-labs #
### This README assumes that there are multiple labs inside the organization. Created a personal access token so that you can create a Jenkins credientials to access the GitHub through GitHub API.

1. Create a New Item in Jenkins
2. Give the New Item a name and choose it as a GitHub Organization
3. Click on the Configure option for the project created
4. Under projects section, create or choose a Credentials to access the GitHub for scanning branches and pull requests. Only "username with password" credentials are supported where password is the GitHub personal access token.
5. Owner is the organization name
6. Under Behaviours:

	> Discover branches
	
	 * Strategy - Only branches that are also filled as PRs
	
	> Discover pull requests from origin
	
	* Strategy - The current pull request revision
	
	> Discover pull request from forks
	
	* Strategy - The current pull request revision
	* Trust - Everyone
	
7. Under Project Recognizers:

	>Pipeline Jenkinsfile
	
	* Give /path/to/the/Jenkinsfile
8. Scan Organization Triggers
	* Check Peridically if not otherwise run box
	* Interval - 1 day
9. Under Automatic branch project triggering:
	> Branch names to build automatically
	
	* Put `PR-\d+` if you want to build any branch with pull requests. or name of the lab you want to build using regular expression.

10. Apply and save the configuration.
11. Scan organization to match the labs matching the regular expression applied on step 9.
	
	