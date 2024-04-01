# CWBI GitHub Access Requests
_Temporary repository for tracking access requests for migration from Platform 1 to GitHub_

We will be using issues on this repository for tracking requests to move repositories from the current Platform 1 GitLab hosting environment here to the CWBI enterprise GitHub account. 

**Suspense - April 30, 2024** We don't have a lot of time to migrate, so we're going to try and make the process as easy as possible.

**Note** All user profiles granted access to the organization must follow the [profile guidelines](https://github.com/cwbi-apps/policies?tab=readme-ov-file#user-profiles) in the CWBI-Apps policies repository

Please create an issue here to request migration of your module code from P1.  There is an issue template that will prompt you for some important information:

1. Module Name - Which CBWI module do the repo(s) support?
2. Repositories - Which Platform 1 repos will be migrated? We want to make sure all code gets migrated even if it is in an archived state, mark the repo as archived in the request and we'll mark it as archived in GitHub which makes it read-only.  Archived repos can be un-archived if needed in the future.
3. Module Admin(s) - Should be the name and GitHub usernames to be added to the admin group for the module, this should include at least one government poc for the module.
4. Module Contributors - List the name and GitHub username for each user who should have write access to the repository.
5. Additional Requests / Comments - Anything else you need to convey on the request.

#### Next Steps

We will create the new repositories here which will initally be empty, there are any number of approaches for moving the code, our recommended approach is as follows:

1. Request new repo(s)
2. Once repos are created we will add the link(s) in a comment on the issue.
3. Run `git remote -v` to list all remotes you have set up.
4. Run `git remote rename origin platform1` assuming your origin is pointed to Platform 1 (verified in step 3), rename it.
5. Run `git remote add origin <new repo git url>` to add the new repository as origin (or name it whatever you want).
6. Run `git push origin refs/remotes/platform1/*:refs/heads/*` to move all working branches from Platform 1 to GitHub, assuming you followed the remote naming convention from above.  This should be an easier way to move each of your branches over without having to manually push each.

If you need any help with the migration please reach out to the CWBI PMO.


