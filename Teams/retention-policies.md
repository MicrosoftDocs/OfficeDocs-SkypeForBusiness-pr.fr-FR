---
title: Stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Découvrez comment les stratégies de rétention et comment les gérer dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d07629f41a54dcab1995f2aef2d7536479be25d
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464555"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="5938a-103">Stratégies de rétention dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5938a-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="5938a-104">Conversations équipes sont persistantes et conservés indéfiniment par défaut.</span><span class="sxs-lookup"><span data-stu-id="5938a-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="5938a-105">Avec l’introduction des stratégies de rétention, les administrateurs peuvent configurer des stratégies de rétention (conservation et suppression) dans le centre de conformité de & sécurité pour les messages de conversation et de canal équipes.</span><span class="sxs-lookup"><span data-stu-id="5938a-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="5938a-106">Cela permet aux organisations de conserver les données de conformité (à savoir, stratégie de conservation) pour une période spécifique ou de vous débarrasser de données (à savoir, stratégie de suppression) s’il est considéré comme un passif après une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="5938a-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="5938a-107">Stratégies de rétention équipes Assurez-vous que lorsque vous supprimez des données, il est supprimé de tous les emplacements de stockage des données permanentes dans le service d’équipes.</span><span class="sxs-lookup"><span data-stu-id="5938a-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="5938a-108">Pour gérer les stratégies de rétention équipes, utilisez les paramètres et les applets de commande dans le centre de conformité sous **La gouvernance des données**de & Office 365 sécurité > **rétention**.</span><span class="sxs-lookup"><span data-stu-id="5938a-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="5938a-109">Stratégies de rétention équipes prennent en charge :</span><span class="sxs-lookup"><span data-stu-id="5938a-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="5938a-110">Conservation : Conserver les données d’équipes pour une durée spécifiée et ne fait rien</span><span class="sxs-lookup"><span data-stu-id="5938a-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="5938a-111">Conservation et supprimer puis : conserver les données des équipes pendant une durée spécifiée, puis supprimer</span><span class="sxs-lookup"><span data-stu-id="5938a-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="5938a-112">Suppression : Supprimer des données d’équipes après une durée spécifiée</span><span class="sxs-lookup"><span data-stu-id="5938a-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="5938a-113">Stratégies de rétention équipes ne prennent pas encore charge :</span><span class="sxs-lookup"><span data-stu-id="5938a-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="5938a-114">Stratégies de rétention avancées ne s’appliquent pas conversation équipes et emplacements de message de canal équipes</span><span class="sxs-lookup"><span data-stu-id="5938a-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="5938a-115">Durée de moins de 30 jours</span><span class="sxs-lookup"><span data-stu-id="5938a-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="5938a-116">Administrateurs peuvent définir des stratégies de rétention distinct de salles de conversation privées équipes (1:1 ou 1:Many conversations) et les messages de canal équipes.</span><span class="sxs-lookup"><span data-stu-id="5938a-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="5938a-117">Dans de nombreux cas, aux organisations de considérer les données de conversation privée comme un passif que les messages de canal, qui sont généralement plus conversations liés au projet.</span><span class="sxs-lookup"><span data-stu-id="5938a-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="5938a-118">Configurer ces stratégies dans le centre de conformité, & de sécurité **la gouvernance des données** > **rétention**.</span><span class="sxs-lookup"><span data-stu-id="5938a-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="5938a-119">Activer de **messages du canal équipes** et **équipes conversations** , puis définissez les stratégies de rétention pour ces emplacements (également indiqués dans le diagramme ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="5938a-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="5938a-120">Lorsque vous activez des **messages du canal équipes**, vous pouvez spécifier les équipes auxquels cette stratégie s’applique.</span><span class="sxs-lookup"><span data-stu-id="5938a-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="5938a-121">Par exemple, pour les équipes X, Y et Z, l’administrateur peut définir les stratégies de suppression pendant 1 an (en sélectionnant individuellement ces équipes) et appliquer une stratégie de suppression de 3 ans pour le reste des équipes.</span><span class="sxs-lookup"><span data-stu-id="5938a-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="5938a-122">Faire la même chose pour **les équipes conversations** sélectionner des utilisateurs spécifiques et appliquer des stratégies de rétention unique.</span><span class="sxs-lookup"><span data-stu-id="5938a-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="5938a-124">Les emplacements de message de canal équipes et les emplacements de conversations équipes adresse uniquement les conversations équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres utilisateur et de groupe).</span><span class="sxs-lookup"><span data-stu-id="5938a-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="5938a-125">Les messages sont supprimés de tous les emplacements de stockage appropriées, à savoir les boîtes aux lettres, Network substrate et service de conversation.</span><span class="sxs-lookup"><span data-stu-id="5938a-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="5938a-126">Pour gérer les stratégies de rétention pour les fichiers d’équipes, qui sont stockés dans OneDrive pour l’activité et de SharePoint, utilisez les stratégies de rétention.</span><span class="sxs-lookup"><span data-stu-id="5938a-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="5938a-127">Par leur conception, les stratégies de suppression pour les fichiers d’équipes sont configurés par le biais de SharePoint Online et OneDrive pour des sites.</span><span class="sxs-lookup"><span data-stu-id="5938a-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="5938a-128">Par conséquent, il est possible qu’une stratégie peut supprimer un fichier référencé dans un message de conversation ou canal équipes avant la suppression d’obtient ces messages.</span><span class="sxs-lookup"><span data-stu-id="5938a-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="5938a-129">Dans ce cas, le fichier s’afficheront toujours dans le message d’équipes, mais si vous cliquez sur le fichier, vous obtiendrez une erreur « Fichier introuvable » (Cela peut également se produire en l’absence d’une stratégie, si un utilisateur supprime manuellement un fichier à partir de SharePoint Online ou OneDrive entreprise).</span><span class="sxs-lookup"><span data-stu-id="5938a-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="5938a-130">Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, consultez [vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="5938a-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
