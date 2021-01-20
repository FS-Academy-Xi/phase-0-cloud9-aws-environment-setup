# AWS Cloud9 Environment Setup

## Introduction

The following instructions are for setting up AWS Cloud9, a cloud-based
Integrated Development Environment. These instructions are provided as an
alternative to setting up a local environment on your personal computer. If you
have not attempted to set up your local environment, we recommend trying to do
so now before continuing:

- [MacOS Environment Instructions](https://github.com/learn-co-curriculum/environment-mac-os-catalina-setup)
- [Windows 10 WSL2 Environment Instructions](https://github.com/learn-co-curriculum/wsl2)

If you attempted the instructions for your operating system but ran into issues
with setup, AWS Cloud9 can serve as a temporary environment and will allow you
to complete and store your Flatiron School coding work in your browser.

## Important Notices

The AWS Cloud9 IDE shoud only be used as a temporary environment solution. Later
portions of our course content require you to have a local environment. The Cloud9 IDE
will allow you to focus on the early course content and maintaining a good pace rather
than being totally blocked due to environment setup issues. We recommend that you
continue to try and get your own local environment set up as you work through your
lessons and assignments.

Using the Cloud9 IDE requires a credit card and may incur charges from AWS if
used for an extended period of time. If you are a new AWS customer, you will
have access to the AWS Free Tier, providing the Cloud9 IDE for free for 12
months. There are some [resource limits][], including a limit of 750 hours of
use per month. Although we don't expect you to hit this limit (750 hours divided
by 30 days is 25 hours per day), [AWS provides an example of what pricing might
look like][aws pricing], should you hit a limit.

## Setting Up Your AWS Account

The first step in accessing the Cloud9 IDE set up is to sign up for your AWS Account.
Go to [https://aws.amazon.com/cloud9/][cloud9] and click **Get
Started with AWS Cloud9**.

![cloud9 get started button](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-get-started-button.png)

To continue, you will need to set up an AWS account. Fill out the required account and
credit card billing information. Once you have set up your account, head back to
theh [cloud9 landing page][cloud9] and click **Sign in to the Console** in the
upper right.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-sign-in-to-console.png" height="50px">

The AWS Management Console will load. In the **Find Services** search bar,
search for `Cloud9`.

![find cloud9](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-find-services-aws.png)

Clicking on the Cloud9 result will bring you to your Cloud9 homepage. The URL
will be unique, depending on what AWS servers are hosting your IDE. We recommend
bookmarking this page to get back to it easily. If you have already created a
Cloud9 IDE, the environment instance will be listed here. In our case, we
want to click the **Create environment** button.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-create-environment-button.png" height="50px">

AWS will prompt you to give your environment a name and an optional
description. Click **Next Step** when ready.

![cloud9 name and description](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-name-and-description.png)

After naming the environment, you will need to select the Environment type and
Instance type. Choose **Create a new EC2 instance for environment (direct
access)** for Environment type. For Instance type, choose **t2.micro(1 GiB RAM +
1 vCPU)**. This is the only Instance type eligible for the AWS free-tier but is
more than enough processing power for our purposes.

![cloud9 environment and instance settings](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-and-instance-settings.png)

Below these options, you'll have a choice of Platform and Cost-saving settings.
Leave the default options - **Amazon Linux** and **After 30 minutes**. Click
**Next Step** to move on.

![cloud9 platform and cost savings options](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-platform-and-cost-savings.png)

On the final page, you will have a chance to review your settings.

![cloud9 environment review page](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-settings-review-page.png)

If everything looks correct, click **Create environment**. Your new Cloud9 IDE
will load in the browser window. It may take a few minutes for AWS to configure
everything.

When everything is loaded, you should see an AWS Cloud9 welcome page.

## Exploring the Cloud9 IDE

The Cloud9 IDE is divided into three main sections.

- On the left side of the screen is your directory navigation. As you work on
  various assignments, this section will become populated with files and
  folders.

  <img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-directory-navigation.png" height="200px">

- Along the bottom of the page is a terminal. You will use this terminal to
  write and execute commands. Click the terminal, type `echo "hello world"`,
  and press `enter` / `return` to test it out. The terminal will print out `hello
  world` in response.

  ![cloud9 terminal example](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-terminal-example.png)

- The IDE's central section (where you see the welcome page) will display
  file contents. Clicking on files in the directory navigation will open them up
  in this section.

  ![cloud9 file contents sections](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-nav-and-file-contents.png)

> **Note:** If you would like more space to type in your terminal or view file
> contents, you can click and drag the border just above the terminal to adjust
> the height of both.

Now that you have your Cloud9 IDE up and running, it is time to do some
configuration for this course.

## Configure the Cloud9 IDE

For some of the content in this course, we'll need to install tools known as
Ruby gems. These gems will help set up and test assignments you'll be working on.
The only gem we need to install right now is `bundler`. `bundler` will actually help
us in later lessons by installing _other_ gems we'll need.

To install `bundler`, type the following into the terminal:

```sh
gem install bundler
```

You should see a message `1 gem installed` once the installation is complete. 

## Setting up a GitHub Account

Before we go any further, you will need a [GitHub][] account. GitHub
will be necessary for working on lessons and assignments during the
program.

### Action Item

1. Open the [GitHub signup webpage][] at https://github.com/join
2. Fill out the form and create your account
3. Verify the email address connected to your GitHub account

[GitHub signup webpage]: https://github.com/join

## Configure Git

Now that you have a GitHub account, it is time to configure Git. Git is a
command-line tool that will allow us to access content stored on GitHub, including
the lessons and assignments in this course. Git will also allow us to upload
work that _you_ do. 

Git should already be installed on your Cloud9 IDE. However, at the moment, you will
be prompted to enter your GitHub account info every time you want to upload work.

To use Git without signing in every time, we will go through the process of creating a Secure Shell (SSH) key and
associating that to your GitHub account. The following steps will ask you to do work both in your
browser and your terminal.

## Action Items

1. Click on the terminal in the Cloud9 IDE
2. Type `git config --global color.ui true` and press `<Enter>`
3. Type `git config --global user.name` + `<Space>` + your name and press `<Enter>` _(Note: this should be your full name, not your GitHub username, in quotes.)_
4. Type `git config --global user.email` + `<Space>` + the email address you used to sign up to GitHub and press `<Enter>`
5. Type `ssh-keygen` and press `<Enter>`
6. For each prompt **do not type anything**, just continue to press `<Enter>`
7. Type `cat ~/.ssh/id_rsa.pub` and press `<Enter>`. Select and copy the output, starting with `ssh-rsa`. 
8. Open the [GitHub New SSH key form][] (https://github.com/settings/ssh/new) _(Note: you need to be logged in to GitHub to access that link.)_
9. Type "My Cloud9 IDE" in the "Title" input field
10. Paste what’s on your clipboard from step seven in the "Key" input field. Each key is unique, but it should look something like this (notice the beginning and end):

    ```sh
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDWN9he+rGvUsQP
    0vldUZT7Z/nTCPqFAPqjiDhNX0SxKdlWeTvhHXjqFRzy0K3cXpgxe0NR
    /yLUphnFbsqCTzgLYTwMn/m8je/gOfPMtZcRuoOj69AJh5LM+TdLcFLZ
    gL1sxjiLCcVO7Sn9ThTYEHSCsS6r2ZaTlFMfakeKBfH9pdWZHqR84pHP
    aq3QxkkrWC7RGrPsBPTYjLYuy7d3Mjw+fUar2oeLUpmMjxX8Fqs7Qf5L
    QR+4/MjA1PMVCVXSRDFUyDYZ756XBcnqQqyaJmSSfgSrk8OE3hqW
    MDFerSP0tzgq26YBWnqsqmCTrSiDgHzgSyO7B8FizTUgn/okdD1b 
    ec2-user@ip-174-35-43-2
    ```

11. Click "Add SSH Key"

[GitHub New SSH key form]: https://github.com/settings/ssh/new

### Check Your Work

If you see your new SSH key beneath the "SSH keys" heading, continue below.

## Conclusion

You've completed your Cloud9 environment setup and first assignment! You are now
set to complete assignments in this first phase of this course. Equipped with
this knowledge, you are now ready to tackle greater challenges!

## Resources

- [Flatiron School][]
- [GitHub][]
- [AWS Cloud9][cloud9]

[resource limits]: https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all
[aws pricing]: https://aws.amazon.com/cloud9/pricing/
[Connected Apps]: https://portal.flatironschool.com/account/github
[GitHub]: https://github.com/
[Flatiron School]: https://portal.flatironschool.com/
[cloud9]: https://aws.amazon.com/cloud9/
