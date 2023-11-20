# SheffieldR.github.io

This is the repository for the [SheffieldR User Group](https://sheffieldr.github.io).

Its written in [Quarto](https://quarto.org) using the [blog
project](https://quarto.org/docs/websites/website-blog.html).

## Creating new Posts

When a meeting is scheduled its normal to write a page for the site detailing what the talk(s) will be about and a short
biography of the presenter(s). To create a new post follow the steps below.

1. Create an
   [issue](https://github.com/SheffieldR/SheffieldR.github.io/issues?asignees=&labels=meeting&projects=&template=meetin_setup.md&title=)
   filling in the details and assign the issue to yourself.

2. Clone this repository locally.

3. Create a branch, typically use your GitHub username and the date e.g. `ns-rse/2023-10-26` this helps yourself and
   others see who's branch it is and what meeting it relates to.

4. Create a directory in `posts` that follows the format `posts/YYYY-MM-DD-<month>-meetup`
   e.g. `posts/2023-10-26-october-meetup`.

4. Copy the template in `posts/.index_template.qmd` to the file `index.qmd` within the directory you just
   created. E.g. `cp posts/.index_template.qmd posts/2023-10-26-october-meetup/index.qmd`.

5. Open the new `index.qmd` and modify the `title`, `date` and `image` fields in the YAML header to reflect the meeting
   (these should mostly have already been detailed in the issue you created in step 1).

6. Update the first paragraph with a description of the meeting, see previous pages for example.

7. Add details of the first talk, then a short speaker biography. These should come from the person presenting.

8. If there is a second speaker add details of their talk and biography, again these should come from the person
   presenting.

9. Preview your changes locally to make sure all fields, links etc. render correctly (use `quarto preview` or the
   "Render" button in RStudio).

10. Once everything has been checked and is correct save all changes, commit them to git and push the changes to
    GitHub. **NB** There is no need to run `quarto publish gh-pages` locally nor to commit the locally rendered HTML
    (located under `_site/_` directory and which is ignored via `.gitignore`). The GitHub Workflow (under
    `.github/workflows/publish.yaml`) handles rendering and publishing the site on GitHub.
    the pages

11. Open a pull request to merge your changes into the `main` branch.

12. Announce the event details to the mailing list on
    [Meetup](https://www.meetup.com/sheffieldr-sheffield-r-users-group/).
