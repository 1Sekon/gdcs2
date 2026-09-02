---
draft: false
authors:
  - komatic5
  - chuckolate
title: Decap
weight: 200
date: 2026-03-23T00:00:00.000Z
contributors:
  - komatic5
  - chuckolate
description: Decap CMS is a Git-based content management system. It provides a web interface that lets you edit files in the repository without working directly with Git. Here we'll cover how to use it in order to make contributing easier for everyone.
tags:
  - Contributing
seo:
  title: How to Use Decap CMS for Geometry Dash Creator School
  description: Learn how to use Decap CMS to edit Geometry Dash Creator School content through a web interface without working directly with Git.
  canonical: ""
  noindex: false
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}


* How to use [Decap CMS](https://decapcms.org/) to make changes to the site.


{{< /callout >}}

# 1: Interface

While on the website or localhost, navigate to [https://www.gdcreatorschool.com/admin](/admin). You should be prompted with a page asking you to log into Github.

{{< img src="https://lh3.googleusercontent.com/d/1sZ42lbtjHN7nDrG2tUmrJuqhqMdRHOTi" >}}

You have to log with your Github account and authorize the CMS.

{{< img src="https://lh3.googleusercontent.com/d/1xkdfNlHFNOLFbDKYrr-VkKDVgdUZadCi" >}}

Once you log in, you should see a page like this. Each page under "Guides" corresponds to a unit, such as Advanced Triggers.

{{< img src="https://lh3.googleusercontent.com/d/13TR-3VUi6C2C6xHBDYkipfulIbhxXvPw" >}}

Clicking on a unit will bring up all guides in that unit.

{{< img src="https://lh3.googleusercontent.com/d/1X2HZ_cl-p7pe1sSBegHZkg78Z2h8Ohza" >}}

Clicking on a guide brings up the editing menu, which lets you make changes to guides. The right side is a **preview panel**, while the left side is the **editing panel** where you can make changes. Each section of the editing panel corresponds to an attribute in the guide's **frontmatter**, check the [Formatting](/contributing/guidelines/formatting) guide to understand what the frontmatter is and what its attributes do.

{{< img src="https://lh3.googleusercontent.com/d/1Ndw25njEufbpMUPWzyou05Pselsfr_VW" >}}

Be sure to save your changes frequently by clicking the "Save" button.

{{< img-grid >}}
{{< img src="https://lh3.googleusercontent.com/d/1VIdMHn0ZEEJqqUqk2yQVwgIZHNHck0a5" >}}
{{< /img-grid >}}

To make a new guide, click the "New Guides" button at the top. This will give you a fresh page.

{{< img-grid >}}
{{< img src="https://lh3.googleusercontent.com/d/1MpgKTLhXsu71Wec3YQJTdZflzw-2rkDa" >}}
{{< /img-grid >}}
{{< img-grid >}}
{{< img src="https://lh3.googleusercontent.com/d/1sEPqKkbUSpi4vMB3F9Pkaavb4ljt5kv9" >}}
{{< /img-grid >}}

Once your changes are made, they'll automatically be pushed to the Github repository as a pull request. We'll review your changes and choose whether to accept your changes.

{{< img-grid >}}
{{< img src="https://lh3.googleusercontent.com/d/1ch091K3swpECIPNEXuDkLUTi4gQO4pAt" >}}
{{< /img-grid >}}
