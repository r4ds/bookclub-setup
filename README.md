# Setting Up for R4DS Online Learning Community Book Clubs

To update the shared slides for R4DS Online Learning Community book clubs (or to participate in other open source projects), you need to set up GitHub.
These instructions should help you get started.

If you have questions about this process, ask in the [#help-zzz-github_open_ource](https://rfordatascience.slack.com/archives/CA349P7EC) channel on the [R4DS Online Learning Community Slack](https://r4ds.io/join).

1.  [Create a GitHub account](https://github.com/signup).

2.  Install git. This is highly system dependent, so we recommend following the instructions in [Happy Git and GitHub for the useR](https://happygitwithr.com/install-git.html).

3.  Install the {usethis} and {devtools} packages:
`install.packages(c("usethis", "devtools"))`

4.  `library(usethis)`.

5.  Run `use_git_config(user.name = "Your Fullname", user.email = "your_email@yourplace.cool")`

6.  Run `usethis::git_sitrep()` to see what steps you need to do. Read the errors and warnings carefully, and follow the instructions provided. We'll continue with instructions that work if you've never set up GitHub in RStudio before, or if you've set it up incorrect (eg, you get the error "Token lacks recommended scopes").

7.  As recommended, run `usethis::create_github_token(description = "rstudio")` (the `description` argument can be whatever you want, just something to remember what you use that token for). The call should open a browser tab on which you can create a token with the recommended settings. You may have to login to GitHub to get to the expected page. Set the expiration of the token to whatever makes sense for you (ie, balance security vs how often you'll have to repeat this step).

8.  Click "Generate token" (green button at the bottom of that page).

9.  Be sure to **copy** the token. It should look something like this: `ghp_ABunchOfLettersAndNumbers`. You must copy it right now, you won't get another chance (but you can always delete the token and try again if you make a mistake).

10.  Call `gitcreds::gitcreds_set()` to register this token in the local Git credential store. If you already have a token stored, you'll be asked if you want to keep, replace, or see those credentials. Choose "Replace these credentials".

11. Paste the token you copied above when asked for a token or password.

12. Re-run `usethis::git_sitrep()`. If you have any more errors, resolve them as suggested by that call. We'll continue with the most likely situation. Re-run this each time you make a change, until it doesn't give any errors or warnings.

13. Call `usethis::git_vaccinate()`. This function "vaccinates" your system against common git safety issues, such as accidentally sharing passwords.

14. (optional) Set up a default {usethis} directory:
  - `usethis::edit_r_profile()` to open your profile for editing.
  - Add this line: options(usethis.destdir = "YOURDIR") (replace YOURDIR with the root directory under which you want your R projects to appear).
  - Restart your R session (Session/Restart R in Rstudio).
  - Run `getOption("usethis.destdir")` to make sure it shows what you expect.

15. When you work on a book club or other project, use `usethis::create_from_github()` to set up a new RStudio project. For example, `usethis::create_from_github("r4ds/bookclub-setup")` creates an RStudio project for this repository.

We recommend using the [{usethis} pull request helpers](https://usethis.r-lib.org/articles/pr-functions.html) for all work on R4DS repositories. Please reach out for help if you have any questions!
