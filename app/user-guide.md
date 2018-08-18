---
sidebar: auto
---

# User Guide

## What is Directus
Directus is a suite of software for managing content that can be connected anywhere. Let's take a look at a few examples to get a better idea what that means.

* **Websites** – You might be managing simple text and images for a personal blog, massive amounts of syndicated content for an enterprise site, or highly customized user account data for a complex webapp service.
* **Native Apps** – Phone apps have similar needs to websites, but often need to receive content in a different format. Directus stores and delivers all content _agnostically_ so that's not a problem.
* **Kiosks** – Ever seen those kiosks at airports or restaurants? That's right, flight information and menus are content too (sometimes called data) and it can also be managed in Directus.
* **Digital-Signage** – From small screens in the back of taxis to huge digital billboards towering over highways. The text, images, and videos on those displays is all content that needs to be managed. Directus!
* **Internet-of-Things (IoT) Devices** – The internet-of-things is the umbrella term for all the world's connected "smart" devices. Refrigerators, washing machines, security cameras—even lights and thermostats. If it's considered a smart device then chances are it's sending or recieving data somewhere. Somewhere like Directus.
* **Wearables** – Smart watches, fitness trackers, and GPS bracelets all typically stores data in the "Cloud" (a fancy word for the internet). Whether mapping the route of your hike or tracking the number of steps taken along the way, each of those devices shares its data with a service like Directus.
* **Combined Systems** – Perhaps your project includes several of the above platforms. Why setup, learn, and pay for multiple specific systems that can't share content with each other? Instead, manage all your content in one place, then simply connect it anywhere and everywhere. Now data for your customers, sales, payroll, scheduling, etc all live in one place, which allows for very revealing connections to be made. Synergy!

## Login

![Login with SSO](./img/directus-login-with-sso.png)

This is probably the first Directus page you'll see, so let's learn a bit more about what you can do here. First off, Directus uses your email address instead of a username, so there's one less thing to forget. Simply enter your email address, and type in your Directus password.

::: tip
You can see which version of the Directus App you're using by hovering over the "Powered by Directus" text at the bottom of the page.
:::

::: warning
Warning: Never share your password. Directus securely encrypts all passwords so there is no reason for anyone to ask you for it.
:::

### Changing Projects

If Directus has been configured to connect to multiple projects then you'll see a dropdown on the login form. You can use this to select a specific project to log in to, or in some cases to type/paste a project link. 

::: tip
Remember, your account passwords may be different on separate projects, even if they use the same email address.
:::

### Single Sign-On

Next to the default secure login, Directus allows you to use several external services as means of authentication.

When [the system has been configured to allow you to login with external services](#), the logos of these services will show up on the login form.

Clicking one of these icons will take you to a secure login page of the service you chose. Directus will allow you to login with your external account as long as it's using the same email address as your user account in Directus.

### Forgot password

Your password is securely encrypted, so no one can remind you what it is if you forget. Instead, click on the "Forgot Password" link and enter the email address you use to log in. Directus will then send you an email with a temporary reset link, simply click on that link or paste it into your browser to set your password.

## Overview

@TODO: screenshot of interface

### Header

The header bar contains a breadcrumb showing you where you currently are in the system and will provide you with a set of actions you can perform on the current page. Often these actions will be related to managing item(s), like saving, searching, deleting, or modifying the selection.

### Navigation Sidebar

The navigation sidebar contains links to your collections, bookmarks, and extensions. This sidebar is accessible from all pages in the system.

#### Logo & Loading Indicator

Everytime the application is working on something, like saving or retrieving items, the logo in the top-left will transform into a loading indicator. 

#### Project Switcher

To switch from the current project to another, you can click on the project name in the top left. This section also shows you the current connection status with the system. Hovering over the project switcher will show you the exact URL you're currently connected to and the latency (milliseconds of delay) to the server.

#### Collections

The first of three link sections shows all the available collections.

#### Extensions

The second link section contains shows any installed extensions. These pages provide extra functionality within the system.

::: tip
This menu won't show up if there aren't any extensions installed.
:::

#### Bookmarks

The third link-section shows your bookmarks. To learn more about bookmarking pages, see [the bookmarking section](#bookmarking).

::: tip
Your system administrator has the ability to [override the links](#) in the navigation sidebar, so the way it looks and works might differ in your application.
:::

#### User Menu

At the bottom of the navigation sidebar is your user's avatar and name. Hovering over this section reveals the user menu which contains links to system pages and a logout button.

* **Admin Settings** – Only available to members of the Administrator Role
* **Help & Docs** – An external link to these Directus Docs
* **File Library** – Navigates to the [File Library](#File-Library)
* **User Directory** – Navigates to the [User Directory](#User-Directory)
* **My Activity** – Navigates to the [Activity Page](#Activity-Page)
* **My Profile** – Navigates to your profile page, where you can update your user account
* **Sign Out** – Logs you out of Directus

### Info Sidebar

The info sidebar is hidden by default, but appears when you click the "i" button in the header. It contains additional information or settings for the current page. When viewing items for example, this sidebar allows you to configure the way your data is displayed. 

### Page

The main section of the app contains the actual page's content.

## Pages

### Collections

@TODO Screenshot

A "collection" is a _group_ or _category_ of items. This could be almost anything: Articles, Projects, Customers, Sales, Reports, Messages, or anything else. This page lists all of the collections you have access to.

### Items

This page displays the items within a collection. All the inforation you need might be displayed here, or you can use this page to find and manage specific items. This is one of the most powerful pages in Directus with many different features available depending on the layout chosen.

#### Layouts

By default the Items page will use the List layout, but depending on the collection content you may want to view items as a grid of cards, on a map, in a calendar, or in a more custom way. You can change the layout from the top of the [Info sidebar](#Info-Sidebar).

#### Layout Options

Each layout may have options for customizing its appearance. These can also be found in the [Info sidebar](#Info-Sidebar), just below the [Layout](#Layouts) dropdown. For example, the default List layout lets you toggle/reorder field columns and change row spacing.

#### Searching

You can easily search through items by entering a query into the search box in the header. This is a quick but blunt tool for finding specific items. When not in use, the search input displays the number of items displayed.

#### Filtering

For more precise results, you can click on the filter icon on the right-side of the search input to expose the filter dropdown. Here you can add a single filter (eg: where _Publish Date_ is after today) or chain multiple filters together.

Each filter is composed of three parts: the field, the [operator](#), and the value. For example: _Date Published_ (field) greater than or equal to (`>=` operator) "April 20th, 2018" (value). The operator can be changed by clicking on it.

If any active filters are present then an orange dot will be shown on top of the filter icon. Individual filters can be removed by hovering over it and clicking "Remove". All filters (and any Search query) can be cleared by clicking the "X" in the search box.

::: tip
Multiple filters are added together with "and", not "or". For example: _Name_ contains "Ben" **and** _Location_ is "Brooklyn" would only return results where both filters match.
:::

#### Selecting & Opening

Certain layouts allow for selecting items. List view items can be selected by toggling the checkbox on the left-side of its row, you can select-all by clicking the checkbox in the column header. The Card view shows a selection toggle when you hover over each card.

Once one or more items are selected, a Delete button will appear in the header. Once two or more items are selected, a [Batch Edit](#Batch-Edit) button will appear in the header.

::: warning
It is possible to quickly and irreversibly delete many items on this page. Always perform batch deletes carefully.
:::

Alternatively, simply clicking on an item will take you to its [Item Detail](#Item-Detail) page.

#### Sorting

Certain layouts support sorting items. In the List view, clicking a column header sorts by that field A-Z, clicking it again will reverse the sort to Z-A. Sorting items is a convenient way to browse items but does not change how they are displayed elsewhere.

#### Reordering

Certain layouts support changing the order of items. For example, on the List layout you can enable drag-and-drop reordering by clicking on the sort column's header (the left-most column). Once enabled, you can reorder items by dragging them by their handle. Reordering items is often used to change the way the content is stored and can change your actual project, so you should always use this feature carefully.

::: tip
This feature is only available if your collection supports reordering.
:::

#### Bookmarking

As you can see, there are many ways to fine-tune the way you view Items. Whenever you change one of the above options Directus saves it to your user's preferences so it will look the same next time you view the page. If you would like to save _multiple_ different views then you would use bookmarks.

You can create a bookmark by clicking the icon to the right of the breadcrumb in the [header](#Header). Once clicked, you'll be prompted to enter a name for the bookmark, and then it will be added to your [Bookmarks](#Bookmarks) list in the navigation sidebar for easy access.

To delete a bookmark, just hover over it in the Bookmarks list and click the delete icon on the right.

Here's what info is saved for each bookmark:

* Layout view (eg: List, Card, Map, Calendar, etc)
* Layout options (eg: visible fields, field order, spacing, etc)
* Sort Column & Direction (eg: Name Ascending, Date Published Descending, etc)
* Search & Filters (eg: "Lorem" general search and _Price_ greater than 10)

::: tip
If you see bookmarks that you didn't create, don't worry. They are likely Role or Global bookmarks that your administrator added for convenience. Role and global bookmarks can not be deleted by users.
:::

### Item Detail

This page is used to view, create, edit, or delete a specific item based on your [role permissions](#). The main content of this page is a form showing the interfaces for all available fields. The [Info Sidebar](#) of this page is used for Item Activity and Comments.

#### Required Fields

Required fields display an accent `*` to the right of their label. These fields must be completed before saving is allowed.

#### Activity & Revisions

All changes made through Directus are tracked for accountability. That means that you can always go back and review the history of each item, from the most current edit back to its creation. Each revision expands when clicked, and will show the specific updates made and give the option to revert back to that version.

#### Reverting

As described above, clicking a revision in the sidebar's Activity timeline will expose the specific updates (only the _edits_ made) and a "Revert" button. Clicking this button will open a _full_ preview of the item at that point in time. At the bottom of this preview is a button to perform the actual revert.

#### Comments & Mentions

Also in the info sidebar, and commingled with the activity timeline, are any comments that users have left for this item. New comments can be added in the input at the top of the sidebar. Comments support basic [Markdown syntax](#) for formatting.

#### Saving

#### Translations
#### Deleting

### File Library

#### Uploading & Adding Files

### User Directory

### My Account

### My Activity

## Permissions
## Status & Workflow