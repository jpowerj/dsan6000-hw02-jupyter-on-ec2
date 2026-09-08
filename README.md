# DSAN 6000 Homework 2: Jupyter on EC2

**Due Friday, September 18, 5:59pm EDT**

> [!WARNING]
> If you have cloned the repository **template** from the `https://github.com/jpowerj/dsan6000-hw02-jupyter-on-ec2` URL, you are **not starting the assignment correctly!** That is, if the command you used to clone the repo onto EC2 looks like:
> 
> `git clone https://github.com/jpowerj/dsan6000-hw02-jupyter-on-ec2`
> 
> This will **not work** for assignments in this course, since you **will not be able to push your changes** back to this repository! (Notice how the above code purposefully has *no copy button!*) Instead, you need to create your **own version of the template**, as described in the next section.

### Creating Your Own Repo From the Template

Click the **green "Use this template" button** in the upper-right corner of the template repo on GitHub, then choose the "Create a new repository" option. On the next page, you will be able to create a **new repository** in **your own GitHub account**, which you should call **`dsan6000-hw02-jupyter-on-ec2`** (the same name as the template).

Once this **derived** repository has been set up on **your GitHub account**, you should first **submit the URL for your newly-created repository on Canvas, immediately after it has been created**: this is what will allow us to see your progress and check any issues between distribution and submission.

Then, once you have submitted the URL on Canvas, **clone *this* newly-created repository (*not* the template owned by `jpowerj`) to your EC2 instance to begin working!** In other words, the command you run on EC2 should look as follows (with your GitHub username in place of `YOUR_GH_USERNAME`):

```bash
git clone https://github.com/YOUR_GH_USERNAME/dsan6000-hw02-jupyter-on-ec2
```

## HW2 Task: Processing OLTP Data via Your "Standard" Python Workflow

### Part 1: Setting Up Your Python Environment

### Part 2: Creating and Writing to a New S3 Bucket

### Part 3: Submission

Once you have completed the above steps, your local repository (on EC2) should contain the following files:



Since you submitted your GitHub URL all the way up at the top of the instructions, all that is left is for you to **push your work from EC2 to GitHub**. If you push a commit with the commit message **"Final submission"** (by running `git commit -m "Final submission"` and then `git push`), we will consider your repo ready to grade – otherwise, if no commit with this message is found, we will consider the **most recent commit when the due date is reached** to be your final submission.

---

Assignment hash: `818283d2eb1ab4323c105aca8b963ee617906a6278e0358a705c6bd2befcd8f3`
