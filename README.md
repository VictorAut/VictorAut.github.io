# VictorAut.github.io
My github pages hosted CV. Just so that I don't have to worry about who-got-what-version and that way I never need to do something like **my_cv-cleaned-2.1-new-version2_updated.pdf** ever again. Nice.

This CV is based on the [lime-cv template](https://github.com/opieters/limecv), which provides a `limecv.cls` class file for typesetting a CV. In this CV, the `limecv.cls` is slightly modified to accomodate my needs. It is therefore _different_ to original template file.

## Local Set up
Fork this repo, or download the folders in the `main` branch as a zip.

If you're like me, you'll want to develop this locally and introduce tools in a step-wise manner in order to introduce each component.

As this website is actually hosted by github pages, I have created a CICD pipeline that will deploy the website, from a `gh-pages` branch upon pushing to `main`. As such, a good starting point to understand how to develop this locally is to have a look at the [github action workflow](/VictorAut.github.io/.github/workflows/deploy_cv.yml)

**Caveat:** This is a linux based guide to installation

1. The github runner is from the texlive image, install this locally with
```
$ apt-get install texlive
```

2. The above will install the Latex engine, which is executed in the following manner creating a `cv.pdf` file
```
$ pdflatex cv.tex
```

3. To render the fonts as provided in the repo and defined the .cls file, you'll have to use the xelatex engine instead, which is installed and executed like this:
```
$ apt-get install texlive-xelatex && xelatex cv.tex
```

4. Any further installation needs can be addressed by replicating the steps in the [github action workflow](/VictorAut.github.io/.github/workflows/deploy_cv.yml)

## FAQs

#### How to change the font of my CV?
adapting the `.cls` is the easiest way to do this. This is contained in the preamble of the file. As limecv defaults to using Fira fonts, get some inspo from [here](https://www.1001fonts.com/fira-sans-font.html)



