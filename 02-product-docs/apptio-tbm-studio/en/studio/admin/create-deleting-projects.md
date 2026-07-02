---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create, manage, and delete projects"
breadcrumb: []
source_path: "studio/admin/create-deleting-projects.html"
images:
  - "resources/images/icons/icon-settings.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create, manage, and delete projects

**Applies to**: TBM Studio 12.0 and later

When you create a new project, you have two options:

- **Create an application project.** Application projects serve as templates
  for new projects. When you create an application project, the application automatically creates data
  sets, metrics, models, and reports based on the application template. The application templates
  include: Costing Standard.
- **Create a custom project.** A blank project has no data sets, models,
  metrics, or reports. Create a new custom project if you do not want to build on previous work.

In the following sections, we will discuss about creating new custom projects. For information,
see the various application guides:

- [Create a custom project](#Createmanageanddeleteprojects__Createacustomproject)
- [Make a project visible to users](#Createmanageanddeleteprojects__Makeaprojectvisibletousers)
- [Edit global project information](#Createmanageanddeleteprojects__Editglobalprojectinformation)
- [Navigate between projects](#Createmanageanddeleteprojects__Navigatebetweenprojects)
- [Delete a project](#Createmanageanddeleteprojects__Deleteaproject)
- [Rename a project](#Createmanageanddeleteprojects__Renameaproject)

## Create a custom project

When you create one of the above types of projects, except for a custom project, the application
creates data sets, models, and reports that are specific to the type of project you selected. If you
create a custom project, there will be no content. There will be no data sets, metrics, models,
objects, or reports. You will have to create these. There are many reasons to create a new project:

- There are several different application users and each of them is in a different department. You
  want the freedom of working on your project without worrying about another user changing your data
  sets, model, metrics, and reports.
- You need to address actual costs as well as forecasting future costs. The best practice would be
  to create an actuals project and a forecast project.
- You are reviewing several different enterprise software products such as an ERP or CRM system,
  and you want to run what-if cost comparisons.

Your Apptio license allows you to create an unlimited number of projects. To create a custom project:

1. Open the Settings menu ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) in the
   upper-right corner of the screen and click **New Project**.
2. In the New Project dialog box, enter the information for the new project.
3. To create the project and close the dialog, click **OK**.
4. Check in the project.When you check in the project, an entry is made in the Access Administration console as shown below. The project initially will not be visible to
   users (the project will not be displayed in the Applications menu). This is handy if you want to
   fully configure the project before making it visible to users.

   ![](../../resources/images/studio_images/studioimages/studio_access%20admin_applications_sui.png)

## Make a project visible to users

When you are ready to make a project visible to users, follow the steps below:

1. Open the Access Administration console by clicking the **Settings**
   menu ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) in the upper-right corner of the
   screen and then clicking **Access Administration**.
2. On the **Applications** tab, locate your project and click **Edit visibility**.
3. Click the roles that you want to give access to the project.
4. Click **Save**.
5. Click **Show**.

## Edit global project information

After you create a project, you can edit the project's information.

1. Check out the project.
2. On the **Project** tab, in the **Project Setup** group, click **Project Settings**. The
   Edit Project Settings dialog box appears.

   ![](../../resources/images/studio_images/studioimages/studio_project%20setup_project%20settings_sui.png)
3. Make the edits and click **OK**.

## Navigate between projects

In the application, you can have only one project open at a time. You open projects from the
Projects menu.

![](../../resources/images/studio_images/studioimages/studio_bank%20demo%20menu_bankdemo_sui.png)

In TBM Studio v12.3.1 and later, you can:

- Specify which version to use for component upgrades ([specify-version-component.html](specify-version-component.html "(Opens in a new tab or window)"))
- Specify your domain's default project ([change\_default\_project.htm](change_default_project.htm "(Opens in a new tab or window)"))

## Delete a project

Only Apptio system Admins can delete projects. If you want to delete a project, check with your
Admin.

## Rename a project

You cannot rename a project from within the product. If you want to rename a project, contact
your Apptio system Admin and request the name change.
