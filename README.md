# Renaming “master” to “main”
Here are the steps I followed to change the default branch of most of my Git repos. This guide may be useful to you if you think that the word “master” (for the default branch of version control) runs the risk of trivialising or normalising slavery, or there’s some other reason why you want to change the branch name.

It assumes you already have a GitHub repo, and that no-one else is collaborating on it who might object to the branch being renamed.

## Caveats about GitHub Pages
I have some sites deployed on GitHub Pages, which will not use branches other than “master” or “gh-pages”. On static React sites, my build process creates a “gh-pages” branch from my “main” branch, so that’s fine. Otherwise, if you want to deploy to GitHub Pages but avoid the “master” vocabulary, you’ll have to rename “master” to “gh-pages”, not “main”.

For the user root repo, ie [DuncanRitchie.github.io](https://github.com/DuncanRitchie/DuncanRitchie.github.io) for me, GitHub Pages will only deploy the “master” branch; you can’t publish “gh-pages” or any other branch. So my portfolio website is still on a “master” branch.

(Happily, though, a repo with the same name as the user, eg [DuncanRitchie/DuncanRitchie](https://github.com/DuncanRitchie/DuncanRitchie), can have a default branch called “main” and its README.md will still appear on the user’s profile on GitHub.)

Finally, if your repo contains markdown files (such as this one) instead of webpages, you can use GitHub Pages to deploy the markdown files as if they were webpages. But this is only true for the “master” branch. It might have been nice to have this document published at www.duncanritchie.co.uk/master-to-main/ , but I’m not renaming this repo’s default branch to “master” to do it.

## Procedure
### If you have the repo locally
Open terminal in the Git repo.

If you are not already on the “master” branch, go onto it:

`git checkout master` 

Check that local is up-to-date with remote:

`git status`

(Run `git pull` or `git push` if you need to!)

Rename branch locally:

`git branch -m master main`

Create a new remote branch from the local “main”:

`git push -u origin main`

(The `-u` flag sets the local “main” branch to permanently track the remote “main” branch, so the simple commands `git pull` and `git push` will work in future.)

(To do the same with more typing, `git push origin HEAD` followed by `git branch -u origin/main`.)

### If you don’t have the repo locally
Open the GitHub repo page, eg https://github.com/{user}/{repo} . There is a dropdown menu on the top-left listing the branches; open it. Above the list of branches is a field. Type “main” into it, then click “Create branch: main from ‘master’”. (Or, instead of clicking, you can press the Down key then Enter to create the branch.) You now have both a “master” and a “main” branch on GitHub.

### After you’ve got a main branch on GitHub
Change anything dependent on the “master” branch to be dependent on the “main” branch. For example, I have deploys on Netlify and Render and and hyperlinks to some specific files in my projects.

From the repo, go to “Settings”, then “Branches”, change the default branch (in the dropdown menu under “Default branch”) to “main” and click "Update", then "I understand, update the default branch”.

(Alternatively, go to https://github.com/{user}/{repo}/branches and click “Change default branch”, to go to the same settings page.)

Delete the remote “master” branch from https://github.com/{user}/{repo}/branches .

Check any deploys and links to your project still work.

## End note
After all this, or before it, or instead of it, take heed of a more important, and hopefully more obvious, message. Renaming a Git branch is not going to do much to alleviate racism, nor will it be of great benefit to victims of slavery. I’m far from an expert in these matters, but since I have your attention here I’d like to make a modest reminder that there are many worthier ways of supporting the Black, Asian, minority-ethnic community. Lots of people have been signing petitions, listening to podcasts, reading books, contributing to charities, supporting Bame businesses, and thinking about how the world could still treat so many much more fairly than it does. This is a good start, but there’s so much yet to do.
