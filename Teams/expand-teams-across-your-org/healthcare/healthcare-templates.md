---
title: "Templates for healthcare organizations"
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
  - Microsoft Teams
  - Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: 
  - M365-collaboration
  - Teams_ITAdmin_Healthcare
  - microsoftcloud-healthcare
appliesto: 
  - Microsoft Teams
ms.reviewer: 
description: Use Microsoft Teams templates with Microsoft Graph to quickly and easily create teams by providing a predefined template of settings, channels, and apps.
ms.custom: seo-marvel-mar2020
---

# Get started with Teams templates for healthcare organizations

Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.

For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams. Templates also allow administrators to deploy consistent teams across their organizations. This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.

We currently offer two first-party healthcare templates that you can use for a variety of situations. To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).

## Ward template

The ward template is meant for communication and collaboration within a ward, pod, or department. The template can be used to facilitate patient management, as well as the operational needs of a ward. For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*. If you're looking to streamline your ward operations, then this template is for you.

|Base Template Type |baseTemplateId |Baseline Template channels|
|:--- |:---|:---|
|Healthcare - Ward | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Announcements\* <br> Huddles\* <br> Rounds\* <br> Staffing\* <br> Training\* |
|     | |         |

\* Auto-favorited

## Hospital template

The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital. Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking. For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel. We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation. Users generally favorite any channels that they find relevant.

|Base Template Type |baseTemplateId |Baseline Template channels|
|:--- |:---|:---|
|Healthcare - Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Announcements\* <br> Compliance\* <br> Custodial <br> Human Resources <br> Pharmacy |
| | |  |

\* Auto-favorited 

## How to use first-party templates

To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.  For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> The channels in the template will automatically be created under the General Tab.

### Example: Hospital template extension script

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

## Related topics

[Get started with Teams templates](../../get-started-with-teams-templates.md)

[Get started with Teams for Healthcare organizations](teams-in-hc.md)

[Get started with Teams templates in the admin console](../../get-started-with-teams-templates-in-the-admin-console.md)
