---
title: Configurer l’analyse des appels pour Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurer l’analyse des appels par utilisateur afin d’identifier et de résoudre les Microsoft Teams de qualité des appels.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117132"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="8b4c8-103">Configurer l’analyse des appels pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b4c8-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="8b4c8-104">En tant qu Microsoft Teams utilisateur, vous pouvez utiliser les analyses des appels par utilisateur pour résoudre les problèmes Teams de qualité des appels et de connexion pour **les utilisateurs individuels.**</span><span class="sxs-lookup"><span data-stu-id="8b4c8-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="8b4c8-105">Pour tirer pleinement parti de l’analyse des appels, définissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b4c8-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="8b4c8-106">Attribuez des rôles de support spécialisés aux personnes, telles que les agents du support technique, pour leur permettre d’afficher les données d’analyse des appels pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="8b4c8-107">Ces rôles de support ne peuvent pas accéder au reste du Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="8b4c8-108">Ajoutez des informations sur le bâtiment, le site et le client à l’analyse des appels en téléchargeant un fichier de données .tsv .csv utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="8b4c8-109">Lorsque vous êtes prêt à utiliser l’analyse des appels par utilisateur, lisez Utiliser l’analyse des appels par utilisateur pour résoudre les problèmes de [qualité des appels.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="8b4c8-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="8b4c8-110">Accorder l’autorisation au personnel de support technique et de support technique</span><span class="sxs-lookup"><span data-stu-id="8b4c8-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="8b4c8-111">En tant qu Teams administrateur de services, vous avez un accès complet aux informations d’analyse des appels pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="8b4c8-112">Nous avons créé des rôles de Azure Active Directory spécialisés que vous pouvez affecter au personnel de support et aux agents du support technique pour leur permettre également d’accéder aux analyses des appels par utilisateur (sans avoir accès au reste du Centre d’administration Teams).</span><span class="sxs-lookup"><span data-stu-id="8b4c8-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="8b4c8-113">Affectez le **rôle de spécialiste Teams du support** aux communications aux utilisateurs qui doivent avoir un affichage limité de l’analyse des appels par utilisateur (support au niveau 1).</span><span class="sxs-lookup"><span data-stu-id="8b4c8-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="8b4c8-114">Attribuez le **rôle Teams support** aux communications aux utilisateurs qui ont besoin d’un accès total à l’analyse des appels par utilisateur (support de niveau 2).</span><span class="sxs-lookup"><span data-stu-id="8b4c8-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="8b4c8-115">Aucun rôle n’a accès au reste du Centre d’Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="8b4c8-116">Pour savoir ce que font chacun de ces rôles, lisez ce que Teams [rôle support fait-il](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="8b4c8-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="8b4c8-117">Pour plus d’informations sur Teams rôles d’administrateur, voir Utiliser Teams rôles d’administrateur [pour gérer Teams.](using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8b4c8-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="8b4c8-118">Pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="8b4c8-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="8b4c8-119">Pour découvrir comment attribuer des rôles d’Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="8b4c8-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="8b4c8-120">Télécharger fichier .tsv ou .csv ajouter des informations de bâtiment, de site et de client</span><span class="sxs-lookup"><span data-stu-id="8b4c8-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="8b4c8-121">Vous pouvez ajouter des informations sur le bâtiment, le site et le client à l’analyse des appels par utilisateur en téléchargeant un fichier .csv ou .tsv.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="8b4c8-122">Avec toutes ces informations, l’analyse des appels peut ma mail mail les adresses IP aux emplacements physiques.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="8b4c8-123">Les administrateurs et les agents du service d’aide peuvent utiliser ces informations pour détecter les tendances des problèmes d’appel.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="8b4c8-124">Par exemple, pourquoi les utilisateurs dans le même bâtiment ont-ils des problèmes de qualité d’appel similaires ?</span><span class="sxs-lookup"><span data-stu-id="8b4c8-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="8b4c8-125">Si vous êtes un administrateur Teams ou Skype Entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord de qualité des appels Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="8b4c8-126">Tout d’abord, vous téléchargez le fichier à partir du DQD, puis vous le chargez dans les données d’analyse des appels.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="8b4c8-127">Pour télécharger un fichier de données existant, rendez-vous sur le tableau de **bord** Microsoft Teams qualité des appels du centre d’administration  >    >  **Télécharger maintenant.**</span><span class="sxs-lookup"><span data-stu-id="8b4c8-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="8b4c8-128">Dans la **liste Mes téléchargements,** cliquez **sur Télécharger** en côté du fichier que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="8b4c8-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="8b4c8-129">Pour télécharger le nouveau fichier, sélectionnez emplacements du centre **Microsoft Teams,** puis sélectionnez Télécharger d’emplacement ou Remplacer les données  >   **d’emplacement.** </span><span class="sxs-lookup"><span data-stu-id="8b4c8-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="8b4c8-130">Si vous créez le fichier .tsv ou .csv à partir de zéro, consultez les informations relatives Télécharger [client et à la création.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="8b4c8-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8b4c8-131">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="8b4c8-131">Related topics</span></span>

[<span data-ttu-id="8b4c8-132">Utiliser les données d’analyse des appels par utilisateur pour résoudre les problèmes de qualité des appels médiocres</span><span class="sxs-lookup"><span data-stu-id="8b4c8-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="8b4c8-133">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="8b4c8-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)