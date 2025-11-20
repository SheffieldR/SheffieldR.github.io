# SheffieldR.github.io

This is the repository for the [SheffieldR User Group](https://sheffieldr.github.io).

Its written in [Quarto](https://quarto.org) using the [blog
project](https://quarto.org/docs/websites/website-blog.html).

## Creating new Posts

When a meeting is scheduled its normal to write a page for the site detailing what the talk(s) will be about and a short
biography of the presenter(s). To create a new post follow the steps below.

1. Create an
   [issue](https://github.com/SheffieldR/SheffieldR.github.io/issues?asignees=&labels=meeting&projects=&template=meetin_setup.md&title=)
   filling in the details for room booking, speakers, calendar and meet links and assign the issue to yourself.

2. Clone this repository locally.

3. Create a branch, typically use your GitHub username and the date e.g. `ns-rse/2023-10-26` this helps yourself and
   others see who's branch it is and what meeting it relates to.

4. Create a directory in `posts` that follows the format `posts/YYYY-MM-DD-<month>-meetup`
   e.g. `posts/2023-10-26-october-meetup`.

5. Copy the template in `posts/.index_template.qmd` to the file `index.qmd` within the directory you just
   created. E.g. `cp posts/.index_template.qmd posts/2023-10-26-october-meetup/index.qmd`.

6. Open the new `index.qmd` and modify the `title`, `date` and `image` fields in the YAML header to reflect the meeting
   (these should mostly have already been detailed in the issue you created in step 1).

7. Update the first paragraph with a description of the meeting, see previous pages for example.

8. Add details of the first talk, then a short speaker biography. These should come from the person presenting.

9. If there is a second speaker add details of their talk and biography, again these should come from the person
   presenting.

10. Preview your changes locally to make sure all fields, links etc. render correctly (use `quarto preview` or the

   "Render" button in RStudio).

1. Once everything has been checked and is correct save all changes, commit them to git and push the changes to
    GitHub. **NB** There is no need to run `quarto publish gh-pages` locally nor to commit the locally rendered HTML
    (located under `_site/_` directory and which is ignored via `.gitignore`). The GitHub Workflow (under
    `.github/workflows/publish.yaml`) handles rendering and publishing the site on GitHub.

2. Open a pull request to merge your changes into the `main` branch.

3. Announce the event details to the mailing list on
    [Meetup](https://www.meetup.com/sheffieldr-sheffield-r-users-group/).

4. Add an image to the post in the YAML header and inline before the `<!--more-->` delimiter.

### Images

A useful source of images to use in posts are those produced for [The Turing
Way](https://the-turing-way.netlify.app/). Many can be found in the DOI
[10.5281/zenodo.3332807](https://doi.org/10.5281/zenodo.3332807) note there are different versions (linked from the
right hand side). Note however that these are the original images and are quite large files and so they can take a while
to load. An alternative option is to use the URL for the images in the GitHub repository for The Turing Way website
where [smaller versions of the images](https://github.com/the-turing-way/the-turing-way/tree/main/book/website/figures)
can be found, or you can use the URL from the image as hosted on the website itself (_Right Click > Copy Image Address_)

Regardless of the image source you should include the appropriate caption for the image which cites the images
correctly. For convenience you can copy and paste the Markdown below, replacing the `<insert_image_url>` with the URL of
the image.

``` markdown
![This illustration is created by Scriberia with The Turing Way community. Used under a CC-BY 4.0 licence. DOI:
[https://doi.org/10.5281/zenodo.3332807](https://doi.org/10.5281/zenodo.3332807)](<insert_image_url)
```

### Pre-commit

This repository uses [pre-commit](https://pre-commit.com) to make various checks of files and lint the Markdown of
`.qmd` files using [markdownlint-cli2](https://github.com/DavidAnson/markdownlint-cli2)  prior to committing changes.

Ideally you should install and configure pre-commit locally so that changes are checked prior to pushing and making
pull-requests, however [pre-commit.ci](https://pre-commit.ci) is used and checks pull-request prior to merging.

If you are unfamiliar with pre-commit the following articles may be useful.

- [RSE Sheffield - pre-commit : Protecting your future self](https://rse.shef.ac.uk/blog/pre-commit/)
- [ns-rse - Pre-commit and R Packaging](https://ns-rse.github.io/posts/pre-commit-r/#windows) includes instructions for
  setting up and configuring R and RStudio with pre-commit.
