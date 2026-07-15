---
title: "ca2"
source: "https://www.simscale.com/docs/platform/dashboard-folders-and-spaces/"
author:
published: 2022-10-21
created: 2026-07-15
description: "The dashboard is a powerful environment in SimScale, allowing users to organize their projects and collaborate with their space members."
tags:
  - "clippings"
---
Documentation

## Dashboard

Organizing your SimScale content is critical to allowing you and your colleagues to quickly and easily find the correct project while ensuring that only the correct people can access it. This can be done within your SimScale Dashboard. There are two core features of content organization at SimScale: *Spaces* and *Folders*.

These features allow you to organize your content as well as allow your organization to efficiently manage groups of users and the simulation content they produce and access.

## Introduction

An organization is a group of users on the SimScale platform with common goals, typically colleagues at a company. You and the other users will have common goals but will typically work on different internal projects or within different business units or groups. It is therefore important to be able to segregate the simulation content you produce so it is easier to find and possible to restrict access when needed. This can be referred to as space (section or area).

## Dashboard

The Dashboard is one of the main environments in the SimScale platform. Users can create new projects, verify their core hour balance, and access projects that have been shared with them from their dashboard.

Find below an overview of the functions available:

![dashboard view in simscale](https://frontend-assets.simscale.com/media/2025/07/dashboard-view-1-2048x992.png)

Figure 1: The dashboard contains methods to organize, sort, search, and create projects.

1. Both *My Projects* and *Recent Projects* list the projects owned by the user, *Spaces* that the user is a part of, and the projects shared with the user.
2. A link to all the public projects created by any user.
3. Within a space, the user can open and edit *Folders*.
4. Existing projects are shown in the center of the page.
5. Different view modes and sorting options for projects.
6. Information panel for selected projects and folders.
7. The *New Project* button, on the top-right corner, is used to create new projects from scratch. From here you can also create new Folders.
8. Search bar, allowing you to search projects with keywords of interest.
9. Panel containing a summary of your [core hour](https://www.simscale.com/knowledge-base/what-is-core-hours/) balance.
10. *Admin* permissions, to create and manage spaces, access analytics, organization settings, manage users and invitations. This is available only to the organizational admins.
11. Access to tutorials, documentation, forum, managing user account.
12. Manage user details, simulation job usage overview, and API keys

To create a new simulation project, click the **‘New Project’** button on the *Dashboard*. The following dialog box appears:

![new project window in simscale](https://frontend-assets.simscale.com/media/2025/07/new-project-window.png)

Figure 2: Project creation dialog. Choose whether to make your project publicly accessible to everybody or to keep it private. In order to make your project private, you need to be in a Professional or Professional Trial account.

1. **Project Title**: The project title should contain the name of the type of application you want to analyze as well as the simulation method you want to use, e.g. ‘Heat exchanger – CHT simulation’. This will help other users to understand what you’re trying to simulate.
2. **Project Description**: Use the project description box to describe the purpose of your project in more detail. A good project description will make your project rank higher in the SimScale Public Projects Library.
3. **Project Category**: The category selection allows you to categorize your project based on industry. Choosing a category will help your project rank higher in the SimScale Public Projects Library.
4. **Tags**: Similar to the category selection, adding tags will help your project rank higher in the SimScale Public Projects Library. Tags are not pre-defined and can be chosen freely. A maximum of 12 tags can be added with each containing 3 – 50 characters.
5. **Advanced Settings**: In the advanced settings you can choose whether to use *SI* or *Imperial* units to interact with the CAD model that you choose to upload into your project. You can also [allow API access](https://www.simscale.com/knowledge-base/allow-api-access/) here.
6. **Public/Private Toggle**: This toggle determines whether your project will be publicly available to everybody or only visible to you. A public project can be seen, copied, and downloaded by any SimScale user. In order to create private projects, you require a *Professional* SimScale account. See [Plans & Pricing](https://www.simscale.com/product/pricing/) to upgrade or start your *Professional* trial.

Once the project is created, you’ll automatically be redirected to the SimScale simulation platform i.e. the Workbench.

Public vs Private Projects for Paid Users

By default, professional users cannot create public projects. If you wish to make some of your projects public to the community, an organization admin can allow that within the *Settings* tab of the Dashboard.  
  
Note that if a professional user created public projects before upgrading their account to professional, those projects will remain public until the user sets them to private.

The dashboard contains functionalities that allow you to create, open, copy, move, share, edit, and delete projects. By right-clicking on a project of interest, all options are shown:

![options when right-clicking on a project move edit delete](https://frontend-assets.simscale.com/media/2025/07/right-clicking-on-a-project-dashboard.png)

Figure 3: Several options appear by right-clicking on a given project.

Once a project is selected, all editing options are also available on the right-hand side panel:

![editing projects and folders right-hand side panel](https://frontend-assets.simscale.com/media/2025/07/editing-projects-and-folders-right-hand-side-panel.png)

Figure 4: After selecting a project, the editing icons are available on the right-hand side panel

Furthermore, you can also open projects with a double left-click, or by selecting the project and clicking on the top-right icon:

![options to open a project from the dashboard](https://frontend-assets.simscale.com/media/2022/10/open-project-shortcut-1.png)

Figure 5: Opening a project in Grid View Mode

Using the methods shown in figures 3 and 4, a specific project can be shared and the panel looks as follows:

![sharing projects in simscale from the dashboard](https://frontend-assets.simscale.com/media/2025/07/sharing-project-from-the-dashboard.png)

Figure 6: Steps to sharing a specific project with a user and the sharing types

In Figure 6, the left-hand side image shows how to enter the username(s) you wish to share the project with. Then, head to the next step using the icon. Now add a sharing type that defines what the user can do with that shared project. *Can view, Can copy,* and *Can edit* are the three sharing types available in SimScale. They define how multiple users can collaborate.

Sharing the project can also be done from within the Workbench. This and the different sharing types (view, copy, edit) are explained in the documentation below:

<iframe title="“Collaboration” — SimScale" src="https://www.simscale.com/docs/platform/collaboration/embed/#?secret=QfqP98QyGb#?secret=fiIJ3WThJm" width="500" height="340" frameborder="0"></iframe>

## Spaces and Folders

## My Projects

Every user has access to personal space which they can create content in. It is represented as *My Projects* within the Dashboard. Only you can create content within your personal space as you are the only member it contains.

![my projects tab dashboard](https://frontend-assets.simscale.com/media/2025/07/my-projects-tab.png)

Figure 7: The personal space functionality, named My Projects, is available to all users in SimScale and cannot be deleted.

The following table shows what you are permitted to do as a user in your personal space:

| **Permission under ‘My Projects’** | **Owner** |
| --- | --- |
| Can view content and folders |  |
| Can copy content |  |
| Can create content and folders |  |
| Can move content |  |
| Can edit content |  |
| Can delete content |  |
| Can share content |  |

Table 1: Permissions under *My Projects* and the activities allowed

## Spaces

Customers with [Teams or Enterprise licenses](https://www.simscale.com/product/pricing/) have access to *Spaces*. Spaces is a section that can be seen by multiple users; its members are controlled by a company administrator.

Spaces can be used to allow only certain users to access specific content. For example, you might have a space for each customer project (Customer A – HX1B, Customer B – RM101) or for each group at your company (Product, Simulation). Any content created within or moved to a space can only be accessed by members of that space and any users it has been directly shared with.

![spaces ui simscale](https://frontend-assets.simscale.com/media/2024/04/spaces.png)

Figure 8: In the above example a space named ‘SimScale’ is added under the Spaces space and it consists of 6 folders.

As an administrator, you can add and manage spaces. This is shown below:

![adding deleting and editing spaces in SimScale](https://frontend-assets.simscale.com/media/2025/07/adding-editing-and-deleting-spaces-2048x741.png)

Figure 9: Go to Manage Spaces to add or manage spaces. Only the admin has access to this tab.

Admin of an organization can set different sharing permissions which consist of *No sharing, Within space,* and *Within organization*.

Depending on the sharing permissions set by the admin individual projects can be shared with other users outside the space or your organization or made public. In this case, users will not gain access to see the folder or the space where the project is located.

It is also possible to share new and existing spaces across the entire organization by adjusting the *Organizational access* setting.

![sharing a space with an entire organization in simscale](https://frontend-assets.simscale.com/media/2025/07/organization-access.png)

Figure 10: The organization admin may choose to allow the entire organization access to a space with a given permission level.

This option is especially useful for projects involving the entire organization, or when members are added and removed frequently from the organization.

To manage an already existing space select the space (see Figure 9). This will open a panel similar to Figure 11 allowing you to rename and also control the sharing permissions as well as manage the space members.

To add a space click on the **‘+ Add space’** button (see Figure 9). This will open a panel where you can name the space, control the sharing permissions, choose the members you want the space to include, and control organization access. Don’t forget to save the settings.

![adding a new space for collaboration in simscale](https://frontend-assets.simscale.com/media/2025/07/adding-a-new-space.png)

Figure 11: The panel to add a new space to the space. Only admin can create a new space.

When creating a space, by default the access is *Restricted* to users that are added to the space.

Owners or members of a space get specific permissions for all projects contained in that space. In other words, the level of permissions granted is configurable. The following table shows what a space member is permitted to do if they have *Admin, Edit, Copy,* and *View* permissions:

| **Permission of a space member** | **Admin** | **Edit** | **Copy** | **View** |
| --- | --- | --- | --- | --- |
| Can view content |  |  |  |  |
| Can copy content |  |  |  |  |
| Can create content and folders |  |  |  |  |
| Can move content |  |  |  |  |
| Can edit content |  |  |  |  |
| Can delete content |  |  |  |  |
| Can share content (if allowed by space setting) |  |  |  |  |
| Can add/remove users to/from space |  |  |  |  |

Table 2: Different permissions in a space and the actions allowed

## Folders

A folder is a location to store your content, including projects and other folders. Folders in SimScale are managed in your dashboard, as discussed in the [*Dashboard* section within this document](https://www.simscale.com/docs/platform/dashboard-folders-and-spaces/#creating-folders). Every folder has an editable name.

To create a folder, navigate to a space that you have access to and select the icon in the upper right corner as shown. You will be prompted to provide a name for the folder.

![creating folders in simscale](https://frontend-assets.simscale.com/media/2025/07/creating-folders-2048x1116.png)

Figure 12: The blue arrows indicate bottons to create new folders/subfolders. After creating a folder, you can start organizing by moving projects into them.

Folders can be opened, moved, edited, and deleted. To access these options, you can right-click on the folder, or use the right-hand side panel after the folder is selected:

![editing folders dashboard](https://frontend-assets.simscale.com/media/2025/07/editing-folders-2048x1119.png)

Figure 13: You can access folder-related operations by either right-clicking on it, or selecting the folder and using the right-hand side panel

Important

When a folder is deleted, all contained folders and projects within it will be deleted.

## Organizational Account

Under *Manage Users*, admins of an organization can:

![managing users admin simscale](https://frontend-assets.simscale.com/media/2025/10/dashboard-view-2048x1022.png)

Figure 14: Admins can provide administrator access to others, invite or remove users. CPU and GPU budgets can be assigned to each user by clicking on the 3-dots menu.

1. See the organizational CPU hour and GPU hour availability
2. Manage administrator rights, i.e. set other members as admins
3. Invite users/colleagues to the account
	- The admin needs to confirm the invitations that are sent by the organization members.
		- Admins also have the right to cancel the invitation after the email is sent to the invitee.
![approve cancel user invite organization account simscale](https://frontend-assets.simscale.com/media/2024/10/image-3.png)

Figure 15: The admin has the right to approve or cancel any invitation sent.

Admins have access to the 3-dot menu on the right which allows them to:

- Remove users
- Set CPU and GPU budgets/spending limits for specific users

![adjust cpu gpu hours](https://frontend-assets.simscale.com/media/2024/04/adjust-budget.png)

Figure 16: Settings panel for controlling the CPU and GPU hour limit for specific users

Removing a User

If a user is removed from the organization the admin should select an inheritor user for all the projects that user owned. This includes projects in spaces and in personal space (*My Projects*).

## Analytics

Within the *Analytics* tab, organization admins have an overview of the organization’s activities in SimScale:

![analytics dashboard in simscale for organization admins](https://frontend-assets.simscale.com/media/2025/10/analytics-dashboard-1-2048x1116.png)

Figure 17: The analytics dashboard provides the admin with an overview of the organization’s activities

It is possible to check, amongst others:

- Number of users and active users
- Number of jobs and success rates for the whole organization and individual users
- Computing quota usage in total and for each project
- User invites

The data may also be filtered by a certain period of interest.

Important

The analytics tab contains activity and jobs data from June 2024 onwards.

> [What Are My Rights as an Administrator with an Organization Account in SimScale?](https://www.simscale.com/knowledge-base/organization-account-admin/)

Last updated: December 30th, 2025

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries