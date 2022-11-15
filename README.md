# Setting Up for R4DS Online Learning Community Book Clubs

To update the shared slides for R4DS Online Learning Community book clubs (or to participate in other open source projects), you need to set up GitHub.
These instructions should help you get started.

If you have questions about this process, ask in the [#help-zzz-github_open_ource](https://rfordatascience.slack.com/archives/CA349P7EC) channel on the [R4DS Online Learning Community Slack](https://r4ds.io/join).

1.  Create a GitHub account.

2.  Run this code to install {usethis} and {devtools} packages.
`install.packages(c("usethis", "devtools"))`

3. Next step is to run this `usethis::git_sitrep()` 
It will help us figure out what you need to do to get ready. 
Depending on what error code is returned, follow the instructions from the error code. 
E.g.
Below is an example of an output after running the above code (the instruction to follow is italicized):


Token lacks recommended scopes:
- 'user:email': needed to read user's email addresses
  *Consider re-creating your PAT with the missing scopes.*
  `create_github_token()` defaults to the recommended scopes.
Can't retrieve registered email addresses from GitHub.
  Consider re-creating your PAT with the 'user' or at least 'user:email' scope.
Git repo for current project
No active usethis project

**If the above was the error code then call:**
`create_github_token()`
N.B. The call should open a browser tab after given you an identical output of the nature below.

• Call `gitcreds::gitcreds_set()` to register this token in the local Git credential store
  (It is also a great idea to store this token in any password-management software that you use)

 Opening URL 'https://github.com/settings/tokens/new?scopes=repo,user,gist,workflow&description=DESCRIBE THE TOKEN\'S USE CASE'

log in your GitHub details in the opened browser.
Set the token use case.
Not sure what to type, you could type your name.
Note: you could set the expiration of the token for as loong as you want. e.g. 90 days
And then scroll down and click "Generate Token".

Ensure you copy and keep (preferably, any password-management software you use) the generated token as you will need it for this call
`gitcreds::gitcreds_set()` 
N.B. using a local version of R makes things easier.
 
After the above steps, you should get the following output:
What would you like to do?
-> Your current credentials for 'https://github.com':
  protocol: https
  
  host    : github.com
  
  username: ***********
  
  password: <-- hidden -->

1: Keep these credentials

2: Replace these credentials

3: See the password / token

The above output is likely for those who had their setup properly configured.
Select 2. insert the generated token that you copied and safekept from the browser earlier. 

An output of this nature should be observed:
-> Adding new credentials...
-> Removing credentials from cache...
-> Done.
Next: run `usethis::git_sitrep()`
follow the error code after you run the above code. Most likely you might be required to vaccinate. 
Run this code `usethis::git_vaccinate()`
NEXT: `usethis::edit_r_profile()`. That will open up your .Rprofile file in the RStudio editor. If you haven't done anything to it before, it might be empty.
We want to add this line:
`options(usethis.destdir = "C:/Users/whatever/yourpath")`
And then save the file.
Once that's set, go to Session: Restart R (or ctrl-shift-f10) to start a new R session. 
Type `getOption("usethis.destdir")` and make sure it shows the thing you set up

Voila!!!
