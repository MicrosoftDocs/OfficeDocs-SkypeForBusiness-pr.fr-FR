---
title: Gérer l’accès des utilisateurs à Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gérez l’accès des utilisateurs à Education Insights dans Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145934"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="6abed-103">Gérer l’accès des utilisateurs à Education Insights</span><span class="sxs-lookup"><span data-stu-id="6abed-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="6abed-104">Ce document indique les étapes nécessaires pour gérer l’accès des utilisateurs à [Education Insights dans Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="6abed-105">Vous devez accorder des autorisations aux responsables de l’éducation, aux chefs de district, aux directeurs d’école, aux chefs d’établissement, aux conseillers, aux responsables de domaine d’étude, aux responsables de programmes, aux travailleurs sociaux et aux psychologues.</span><span class="sxs-lookup"><span data-stu-id="6abed-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="6abed-106">Les enseignants bénéficient *automatiquement* d’une autorisation lorsqu’ils sont propriétaires d’une équipe de classe.</span><span class="sxs-lookup"><span data-stu-id="6abed-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="6abed-107">Pour fournir des informations au niveau de l’organisation, vous devez [importer des données du système d'informations sur les élèves (SIE)](education-insights-sis-data-sync.md). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée.</span><span class="sxs-lookup"><span data-stu-id="6abed-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="6abed-108">Seul l’administrateur général peut gérer l’accès des utilisateurs à Insights.</span><span class="sxs-lookup"><span data-stu-id="6abed-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="6abed-109">Nous vous recommandons d’activer Insights pour tous les responsables de l’éducation. Ainsi, ils disposeront des données permettant de comprendre chaque établissement scolaire, et pourront identifier rapidement les problèmes, puis fournir un support aux enseignants concernés.</span><span class="sxs-lookup"><span data-stu-id="6abed-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="6abed-110">Même si vous gérez un pilote, il peut être utile de maintenir Insights activé pour tous les responsables de l’éducation, mais de cibler les communications uniquement sur le groupe pilote d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6abed-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="6abed-111">Accorder des autorisations</span><span class="sxs-lookup"><span data-stu-id="6abed-111">Grant permissions</span></span>

* <span data-ttu-id="6abed-112">Ouvrez l’application Insights, cliquez **Paramètres**, puis sélectionnez **Autorisations utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="6abed-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="Paramètres":::

* <span data-ttu-id="6abed-114">Sélectionnez **Ajouter des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6abed-114">Select **Add users**.</span></span>
* <span data-ttu-id="6abed-115">Entrez le nom d’utilisateur ou l’adresse e-mail de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6abed-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="6abed-116">Sélectionnez le niveau d’autorisation :</span><span class="sxs-lookup"><span data-stu-id="6abed-116">Select the permission level:</span></span>
  * <span data-ttu-id="6abed-117">**L’accès à toute l’organisation** signifie que l’utilisateur a accès à toutes les unités de l’organisation à tous les niveaux.</span><span class="sxs-lookup"><span data-stu-id="6abed-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="6abed-118">**L’accès à des établissements spécifiques** signifie que l’utilisateur a accès aux établissements scolaires sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="6abed-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="6abed-119">Commencez à taper, puis sélectionnez l’établissement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6abed-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="6abed-120">Vous pouvez ajouter plusieurs établissements scolaires simultanément.</span><span class="sxs-lookup"><span data-stu-id="6abed-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="6abed-121">Cliquez sur **Ajouter de nouveaux utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6abed-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="Accorder des autorisations":::

> [!NOTE]
> <span data-ttu-id="6abed-123">Accordez uniquement les autorisations aux responsables de l’éducation qui en ont besoin, ainsi qu’aux unités d’organisation dont ils sont responsables.</span><span class="sxs-lookup"><span data-stu-id="6abed-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="6abed-124">Si vous ne savez pas si une autorisation d’utilisateur est nécessaire pour une organisation spécifique, veuillez consulter les experts en matière de confidentialité de votre établissement, tels que le personnel juridique ou celui des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="6abed-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="6abed-125">Modifier les autorisations</span><span class="sxs-lookup"><span data-stu-id="6abed-125">Edit permissions</span></span>
* <span data-ttu-id="6abed-126">Sélectionnez un utilisateur spécifique, puis sélectionnez **Modifier les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="6abed-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="6abed-127">Mettez à jour le niveau d’autorisation ou la liste des établissements scolaires, puis cliquez sur **Mettre à jour les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="6abed-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="Modifier les autorisations":::

## <a name="remove-permissions"></a><span data-ttu-id="6abed-129">Supprimer les autorisations</span><span class="sxs-lookup"><span data-stu-id="6abed-129">Remove permissions</span></span>
* <span data-ttu-id="6abed-130">Sélectionnez les utilisateurs à supprimer, puis sélectionnez **Supprimer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6abed-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="6abed-131">Ces utilisateurs n’auront plus accès à Insights au niveau de l’organisation, mais pourront toujours accéder à Insights au niveau de la classe s’ils sont membres d’une équipe de classe.</span><span class="sxs-lookup"><span data-stu-id="6abed-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="Supprimer des autorisations":::
