# Making a Guide

Guides on this page are Mardown documents. Markdown is a markup language that allows you to create simple formatted documents. If you are unfamiliar with Markdown, there are a number of [**tutorials**](https://www.markdownguide.org) online that can teach you the basics in minutes.

<br>

### Before Writing Your Guide

1. Create a file named YYYY-MM-DD-yourtitle.md (fill the current year, month, day, and your title in)
2. Add the following code to the top of your file (copy it exactly)

    ```
    ---
    layout: post
    title: Your Title
    permalink: /yourtitle/
    image: "images\\yourtitle.jpg"
    description: Your Short Desciption
    type: guide
    author: username
    ---
    ```
3. Customize the above code to be relevant to your guide. You should change the title, permalink, image, description, and username fields

4. Prepare an image for your guide. It should be named the same as your permalink and be a .jpg image

Once you have completed these steps, you are ready to start writing your guide! 

Note: please make sure you are allowed to use the thumbnail image you choose. Websites like [**Unsplash**](https://unsplash.com) can provide you with free photos to use. 

<br>

### While Writing Your Guide
Use Markdown to start writing your guide. To see what your guide will look like while writing it, consider using an [**online markdown editor**](https://dillinger.io). Please make sure to keep your language family-friendly and not to spoil any scavenger hunt eggs!

#### Adding an Image to the Guide
To add an image to your guide, please reference it in Markdown as follows. 

`![alt text goes here](\\images\\yourfilename.jpg)`

You will likely not be able to view the image in your local Markdown editor like this, so feel free to perform this step at the end.

#### Adding a Table to the Guide
To add a table, consider using an online markdown table generator, then add this code. Replace the table inside this `<div>` tag with your table; keep the space between the tags and the table.

```
<div class="table-wrapper" markdown="block">

|First Name           |Last Name|Address                         |City       |ST |ZIP   |
|---------------------|---------|--------------------------------|-----------|---|------|
|John                 |Doe      |120 jefferson st.               |Riverside  | NJ| 08075|
|Jack                 |McGinnis |220 hobo Av.                    |Phila      | PA|09119 |
|John "Da Man"        |Repici   |120 Jefferson St.               |Riverside  | NJ|08075 |
|Stephen              |Tyler    |7452 Terrace "At the Plaza" road|SomeTown   |SD | 91234|
|                     |Blankman |                                |SomeTown   | SD| 00298|
|Joan "the bone", Anne|Jet      |9th, at Terrace plc             |Desert City|CO |00123 |

</div>
```



<br>

### Adding a Guide to this Website
Once you have your completed Markdown document and have your images ready, you are ready to add it to the website. There are currently two ways to do this.

#### 1. GitHub Pull Request

If you are familiar with Git or GitHub, this can be a convenient way to add your guide. 

Create a [**pull request**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to this GitHub repository with your Markdown document in the `_posts` folder and your images in the `images` folder. An administrator will review your guide and approve your pull request!

#### 2. Complete this Google Form

If you are not familiar with GitHub, no worries! You can complete this [**Google Form**](https://forms.gle/Xxr6Y6NvGG5kBcHcA). Please note that it may take a few days for an administrator to add your guide to the website. Please only complete the form once per guide.

