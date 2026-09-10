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

## HW2 Task: Processing OLTP Data With a "Standard" Python Workflow

For this assignment you will be working with the **same data you saw in HW1**, but with the added challenges of:

* (a) Using your **`.pem` public key file** to connect to your EC2 instance from **within VSCode**, and
* (b) Setting up and working with **your own S3 bucket** (rather than just reading data from a publicly-accessible bucket like you did in HW1).

I promise, though, that if you're getting bored/frustrated with all of the setup steps you've had to carry out in these first two homeworks, **they will pay off** when you get to Homeworks 3-9!

The majority of these remaining homeworks will involve the **exact same workflow** as this one (connecting to your EC2 instance using VSCode, and then writing and excecuting Python code remotely). Then the last few assignments and the Final Project will only add on a few additional steps to this workflow.<a name='fn1loc'></a><sup>[1](#fn1)</sup>

### Part 1: Setting Up Your Python Environment

If you followed the in-class demonstration where Jeff walked through how to connect to your EC2 instance from within VSCode, you can start on this part right away!

Otherwise, you can use the full instructions in [this writeup](https://jjacobs.me/dsan6000/writeups/ec2/) on the course website to reach this stage, but the quick summary is as follows:

> [!NOTE]
> #### Connecting to EC2 From VSCode
> 
> 1.  Start your 4-hour **AWS Academy Lab Session** by clicking "Start Lab" from within the "AWS Learner Lab" Module
> 2.  Open the **AWS Console** (the page with a URL that looks like `https://https://us-east-1.console.aws.amazon.com/console/home`)
> 3.  Navigate to the **EC2 Console** (for example, by typing "EC2" into the Search bar at the top of the AWS Console interface)
> 4.  Click "Instances (running)" to view your active EC2 instances
> 5.  Single-click on the row for the instance you'd like to connect to, then look at the instance info panel that appears below the list of instances. Copy the address given in the instance's **Public DNS** field
> 6.  Click the "Warp button" in the bottom-left of the VSCode interface &rarr; "Connect Current Window to Host..." &rarr; "Configure SSH Hosts..." &rarr; Choose the first file that appears in the resulting list of config files
> 7.  Remove the existing DNS address that appears after `HostName` (e.g., the URL starting with `ec2` in `HostName ec2-44-210-233-143.compute-1.amazonaws.com`) and paste the new DNS URL in its place
> 8.  Click the "Warp button" in the bottom-left of the VSCode interface once again &rarr; "Connect Current Window to Host...", but this time select the option corresponding to the `Host` nickname for your EC2 instance (for example, if the portion of your config file containing connection info for the EC2 instance starts with `Host DSAN6000`, then `DSAN6000` should be one of the options in this menu)
> 9.  Finally, click "Open" and then allow VSCode to auto-fill the path (it should auto-fill the path field with your home directory, `/home/ubuntu/`). The list of files and folders stored within your home directory should now appear in the Explorer panel on the left side of the VSCode interface, which means you're ready to clone your repo and start working!

If you followed the writeup and/or the above steps, your VSCode interface should now look something like the following image:

![](images/vscode-connected.jpeg)

> [!NOTE]
> ### Setting Up `uv`
> 
> In this class, to ensure that the Python libraries necessary for each assignment are installed on your EC2 instance, we will be using the [`uv` package manager](https://docs.astral.sh/uv/). Setting up `uv` and then activating the environment works as follows:
> 
> 1.  If you have not yet installed `uv` on your EC2 instance, run the following command within VSCode's Integrated Terminal:
> 
>     ```bash
>     curl -LsSf https://astral.sh/uv/install.sh | sh
>     ```
> 2.  Now just type `uv sync`, and `uv` will create a new Python environment (within a subdirectory it will create, called `.venv`) where all libraries necessary for this assignment are automatically installed.
> 3.  Once the `uv sync` command has finished running, activate the created environment by executing
> 
>     ```
>     source .venv/bin/activate`
>     ```
> 4. If the environment was activated successfully, the command prompt in VSCode's Integrated Terminal should now have a `(dsan6000-hw02)` prefix. That is, the prompt should look like:
> 
>     ```
>     (dsan6000-hw02) 
>     ```

### Part 2: Creating and Writing to a New S3 Bucket

### Part 3: Submission

Once you have completed the above steps, your local repository (on EC2) should contain the following files:



Since you submitted your GitHub URL all the way up at the top of the instructions, all that is left is for you to **push your work from EC2 to GitHub**. If you push a commit with the commit message **"Final submission"** (by running `git commit -m "Final submission"` and then `git push`), we will consider your repo ready to grade – otherwise, if no commit with this message is found, we will consider the **most recent commit when the due date is reached** to be your final submission.

---

<a name="fn1">1</a>. As a preview: you will launch **web servers** that will run on a particular **port** on your EC2 instance, then you will make requests to this server from your local laptop via **port forwarding**. [↩︎](#fn1loc)

---

Assignment hash: `818283d2eb1ab4323c105aca8b963ee617906a6278e0358a705c6bd2befcd8f3`
