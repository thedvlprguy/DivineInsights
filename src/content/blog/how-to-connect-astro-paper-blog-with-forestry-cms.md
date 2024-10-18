---
title: How to connect DivineInsights blog with Forestry CMS
author: Aditya Tomar
pubDatetime: 2024-10-18T05:17:19Z
slug: how-to-connect-divineinsights-blog-with-forestry-cms
featured: false
draft: false
tags:
  - docs
  - forestry-cms
  - divineinsights
ogImage: https://res.cloudinary.com/noezectz/v1663745737/divineinsights/DivineInsights-x-forestry-og_kqfwp0.png
description:
  Step by step process of connecting divineinsights blog theme with Forestry
  Headless CMS.
---

> Important!!! Forestry is going to be discontinued on April 22nd, 2023. You can [read their announcement](https://forestry.io/blog/forestry.io-end-of-life/) for more info.

In this article, I will explain step by step process of connecting DivineInsights theme with the Forestry headless CMS. So, let's get started 🎉

## Table of contents

## What is Forestry?

[Forestry](https://forestry.io/ "Forestry Website") is a git-based headless CMS and we can manage our markdown contents easily by using that. Although it is not an open-sourced CMS, it has a good free plan by which we can import up to 3 sites (3 repositories). In this article, I'll demonstrate how we can use Forestry as git-based CMS of our DivineInsights blog theme.

## Login / Register an account at Forestry.io

First of all, you have to create an account at [Forestry website](https://app.forestry.io/login "Forestry Login Page"). I usually sign up with my Github account.

![Forestry Login page](https://res.cloudinary.com/noezectz/v1663739096/divineinsights/Forestry-io_hk5yzv.png)

## Import DivineInsights site (repository)

This part is importing the repository to Forestry and a little bit of set up process.

### Add Site

After logging in/signing up an account, import your DivineInsights site by clicking "Add Site" button.

![Forestry 'My sites' page](https://res.cloudinary.com/noezectz/v1663739752/divineinsights/Forestry-io_1_z1bdyd.png)

### Select SSG

In this case, just choose "Others"

![Selecting 'Others' as a site generator](https://res.cloudinary.com/noezectz/v1663740872/divineinsights/Forestry-io_2_blrrw2.png)

### Select Git Provider

My git provider is Github and I assume yours is the same. So, choose "Github".

![Selecting Github as a git provider](https://res.cloudinary.com/noezectz/v1663740922/divineinsights/Forestry-io_3_pj1v8v.png)

After this, the process of importing site (repo) is done.

## Set up Sidebar

The next phase after importing site is setting up sidebar menu. You can add many sidebar menu as you want. However, I'll only add one sidebar menu in this case.

Navigate to "Finish setup process" > "Set up sidebar" and click "Configure sitebar"

![Forestry welcome screen](https://res.cloudinary.com/noezectz/v1663740974/divineinsights/forestry-io_4_j35uk9.png)

Then, click "Add Section" button.

![Clicking 'Add Section' for sidebar](https://res.cloudinary.com/noezectz/v1663741011/divineinsights/forestry-io_5_sxtgvx.png)

After that, choose DIRECTORY for the Section Type.

![Choosing 'DIRECTORY' as the Selection Type](https://res.cloudinary.com/noezectz/v1663741052/divineinsights/forestry-io_6_lddmkx.png)

Then, configure the directory section. You can follow along with my setup.

![Configuring the Directory Section](https://res.cloudinary.com/noezectz/v1663741105/divineinsights/forestry-io_7_jkwgi1.png)

After this step, you should see a sidebar menu "Blog Posts" and some blog posts.

## Set up Media Import

In Forestry CMS, you can set up different options for media (aka assets) such as Cloudinary, git commit media etc. I usually store my assets in [Cloudinary](https://cloudinary.com/). To set up media import, go to Settings > Media. Then select your image storage provider. (I chose Cloudinary).

![Setting up 'Cloudinary' as the media import](https://res.cloudinary.com/noezectz/v1663741636/divineinsights/forestry-io-media-import_1_f8i4lm.png)

You can see details of Forestry Cloudinary setup at [Forestry documentation](https://forestry.io/docs/media/cloudinary/).

## Set up Front matter template

After setting everything up, you can set up front matter template for your future blog post. To set up front matter template, navigate to "Front matter" menu on the sidebar.

Then, click "Add Template" button at the top right corner.

![Front Matter Templates page](https://res.cloudinary.com/noezectz/v1663742060/divineinsights/forestry-io-frontmatter_yskfvn.png)

Select new template based on existing document.

![Creating new template based on existing document](https://res.cloudinary.com/noezectz/v1663742179/divineinsights/forestry-io-existing-doc_bwcb9q.png)

Then, add template name and choose one of my document page as template.

As the final setup, make some adjustment in the front matter field settings.

![Making some adjustment in a front matter field setting](https://res.cloudinary.com/noezectz/v1663742450/divineinsights/forestry-io-fm-config_jqmgwz.png)

Here are some adjustments you have to make.

**_title_**

- Validation => REQUIRED => true

**_author_**

- Default => your name

**_datetime_**

- Default => USE "NOW" AS DEFAULT

**_description_**

- Validation => REQUIRED => true

## Conclusion

You can now post your articles and write whatever you want.
