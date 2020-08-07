---
title: Configurer l’analyse des appels pour Microsoft teams
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
description: Définissez une analyse d’appel par utilisateur pour identifier et résoudre les problèmes de qualité d’appel dans Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581105"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="6f69b-103">Configurer l’analyse des appels pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6f69b-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="6f69b-104">En tant qu’administrateur de Microsoft Teams, vous pouvez utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de qualité d’appel et de connexion d’équipes pour **les utilisateurs individuels**.</span><span class="sxs-lookup"><span data-stu-id="6f69b-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="6f69b-105">Pour tirer pleinement parti de l’analyse des appels, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6f69b-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="6f69b-106">Attribuez des rôles de support spécialisés aux utilisateurs, tels que les agents de support technique, pour leur permettre d’afficher les données d’analyse pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f69b-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="6f69b-107">Ces rôles d’assistance ne peuvent pas accéder au reste du centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="6f69b-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="6f69b-108">Ajoutez des informations de bâtiment, de site et de client à une analyse d’appel par utilisateur en chargeant un fichier de données. TSV ou. csv.</span><span class="sxs-lookup"><span data-stu-id="6f69b-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="6f69b-109">Lorsque vous êtes prêt à commencer à utiliser une analyse d’appel par utilisateur, voir [utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="6f69b-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="6f69b-110">Accorder l’autorisation d’assistance et au personnel du support technique</span><span class="sxs-lookup"><span data-stu-id="6f69b-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="6f69b-111">En tant qu’administrateur Teams, vous disposez d’un accès total aux informations d’analyse des appels pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f69b-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="6f69b-112">Nous avons créé quelques rôles Azure Active Directory spécialisés que vous pouvez affecter au personnel de support technique et aux agents de support technique pour qu’ils puissent également accéder aux analyses d’appel par utilisateur (sans avoir accès au reste du centre d’administration Teams).</span><span class="sxs-lookup"><span data-stu-id="6f69b-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="6f69b-113">Affectez au rôle de spécialiste de la **prise en charge des communications équipe** aux utilisateurs qui doivent disposer d’un affichage limité d’une analyse d’appel par utilisateur (prise en charge de niveau 1).</span><span class="sxs-lookup"><span data-stu-id="6f69b-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="6f69b-114">Affectez au rôle de **technicien de support communications** de l’équipe aux utilisateurs qui ont besoin d’un accès total à une analyse d’appel par utilisateur (prise en charge de niveau 2).</span><span class="sxs-lookup"><span data-stu-id="6f69b-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="6f69b-115">Aucun des rôles n’a accès au reste du centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="6f69b-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="6f69b-116">Pour plus d’informations sur chacun de ces rôles, voir [qu’est-ce que chaque équipe prend en charge](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="6f69b-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="6f69b-117">Pour plus d’informations sur les rôles d’administrateur d’équipe, voir [utiliser des rôles d’administrateur d’équipes pour gérer teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6f69b-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="6f69b-118">Pour plus d’informations sur l’attribution de rôles d’administrateur dans Azure Active Directory, voir [afficher et affecter des rôles dans Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="6f69b-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="6f69b-119">Pour plus d’informations sur l’attribution de rôles d’administrateur dans Azure Active Directory, voir [afficher et affecter des rôles dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="6f69b-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="6f69b-120">Télécharger un fichier. TSV ou. csv pour ajouter des informations de bâtiment, de site et de client</span><span class="sxs-lookup"><span data-stu-id="6f69b-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="6f69b-121">Vous pouvez ajouter des informations de bâtiment, de site et de client à une analyse d’appel par utilisateur en chargeant un fichier. csv ou. TSV.</span><span class="sxs-lookup"><span data-stu-id="6f69b-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="6f69b-122">À l’aide de ces informations, l’analyse des appels permet de mapper les adresses IP aux emplacements physiques.</span><span class="sxs-lookup"><span data-stu-id="6f69b-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="6f69b-123">Les administrateurs et les techniciens du support technique peuvent utiliser ces informations pour détecter les tendances en matière de problèmes d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f69b-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="6f69b-124">Par exemple, pourquoi les utilisateurs dans le même bâtiment rencontrent-ils des problèmes de qualité d’appel similaires ?</span><span class="sxs-lookup"><span data-stu-id="6f69b-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="6f69b-125">Si vous êtes un administrateur teams ou Skype entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord des équipes ou de la qualité des appels de Skype entreprise (bord).</span><span class="sxs-lookup"><span data-stu-id="6f69b-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="6f69b-126">Tout d’abord, vous devez télécharger le fichier à partir de bord, puis le charger pour appeler Analytics.</span><span class="sxs-lookup"><span data-stu-id="6f69b-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="6f69b-127">Pour télécharger un fichier de données existant, accédez au **Centre d’administration Microsoft teams**de  >  **qualité des appels**  >  **Upload now**.</span><span class="sxs-lookup"><span data-stu-id="6f69b-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="6f69b-128">Dans la liste **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier souhaité.</span><span class="sxs-lookup"><span data-stu-id="6f69b-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="6f69b-129">Pour télécharger le nouveau fichier, accédez à emplacements du **Centre d’administration de Microsoft teams**  >  **Locations**, puis sélectionnez charger les **données d’emplacement** ou remplacer les **données d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="6f69b-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="6f69b-130">Si vous créez le fichier. TSV ou. csv à partir de zéro, voir [Télécharger le client et générer des données](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="6f69b-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6f69b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f69b-131">Related topics</span></span>

[<span data-ttu-id="6f69b-132">Utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de mauvaise qualité d’appel</span><span class="sxs-lookup"><span data-stu-id="6f69b-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="6f69b-133">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="6f69b-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
