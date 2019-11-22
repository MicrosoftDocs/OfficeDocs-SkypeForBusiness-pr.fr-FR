---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Apprenez-en davantage sur les stratégies de rétention et la façon de les gérer dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793520"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="203ab-103">Stratégies de conservation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="203ab-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="203ab-104">Les conversations d’équipes sont permanentes et conservées définitivement par défaut.</span><span class="sxs-lookup"><span data-stu-id="203ab-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="203ab-105">Avec la présentation des stratégies de rétention, les administrateurs peuvent configurer des stratégies de rétention (conservation et suppression) dans le centre de sécurité & conformité pour les conversations et les messages de canal.</span><span class="sxs-lookup"><span data-stu-id="203ab-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="203ab-106">Cela permet aux organisations de conserver les données relatives à la conformité (politique de conservation) pour une période donnée ou d’éliminer les données (c’est-à-dire, la politique de suppression) si elle est considérée comme une responsabilité après une période donnée.</span><span class="sxs-lookup"><span data-stu-id="203ab-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="203ab-107">Les stratégies de rétention de teams garantissent que, lorsque vous supprimez des données, les emplacements de stockage des données permanentes du service équipes sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="203ab-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="203ab-108">Nous ne prenons pas encore en charge la configuration de la conservation des messages de canal privé.</span><span class="sxs-lookup"><span data-stu-id="203ab-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="203ab-109">La conservation des fichiers partagés dans des canaux privés est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="203ab-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="203ab-110">Pour gérer les stratégies de rétention aux équipes, utilisez les paramètres et les applets de la section sécurité du centre de sécurité & conformité d’Office 365 sous**rétention**de la **gouvernance** > des informations.</span><span class="sxs-lookup"><span data-stu-id="203ab-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="203ab-111">Les stratégies de rétention teams prennent en charge :</span><span class="sxs-lookup"><span data-stu-id="203ab-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="203ab-112">Préservation : conserver les données d’équipe pour une durée spécifiée et ne rien faire</span><span class="sxs-lookup"><span data-stu-id="203ab-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="203ab-113">Préservation et suppression : conservez les données d’équipe pour une durée spécifiée, puis supprimez</span><span class="sxs-lookup"><span data-stu-id="203ab-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="203ab-114">Suppression : supprimer les données de l’équipe après une durée spécifiée</span><span class="sxs-lookup"><span data-stu-id="203ab-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="203ab-115">Les stratégies de rétention Teams ne sont pas encore prises en charge :</span><span class="sxs-lookup"><span data-stu-id="203ab-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="203ab-116">Les stratégies de rétention avancées ne s’appliquent pas aux emplacements discussions et équipes des messages de canal</span><span class="sxs-lookup"><span data-stu-id="203ab-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="203ab-117">Durée de moins de 30 jours</span><span class="sxs-lookup"><span data-stu-id="203ab-117">Duration of fewer than 30 days</span></span>

<span data-ttu-id="203ab-118">Les administrateurs peuvent configurer des stratégies de rétention distinctes pour les discussions privées d’équipes (1:1 ou 1 : nombreux messages de discussion) et équipes de canal.</span><span class="sxs-lookup"><span data-stu-id="203ab-118">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="203ab-119">Dans de nombreux cas, une entreprise considère qu’il s’agit d’une plus grande responsabilité par le biais de messages de canal, qui sont généralement davantage des conversations relatives au projet.</span><span class="sxs-lookup"><span data-stu-id="203ab-119">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="203ab-120">Définissez ces stratégies dans le centre de sécurité & conformité, \*\*\*\* > **rétention**de la gouvernance des informations.</span><span class="sxs-lookup"><span data-stu-id="203ab-120">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="203ab-121">Activez les **messages du canal équipes** et les **discussions d’équipe** , puis définissez les stratégies de rétention pour ces emplacements (également illustrées ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="203ab-121">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="203ab-122">Lorsque vous activez **les messages de canal teams**, vous pouvez spécifier les équipes auxquelles s’applique cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="203ab-122">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="203ab-123">Par exemple, pour les équipes X, Y et Z, l’administrateur peut définir les stratégies de suppression pour 1 an (en les sélectionnant individuellement) et appliquer une stratégie de suppression de 3 ans au reste des équipes.</span><span class="sxs-lookup"><span data-stu-id="203ab-123">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="203ab-124">Vous pouvez effectuer la même opération pour les **discussions d’équipe** en sélectionnant des utilisateurs spécifiques et en appliquant des stratégies de rétention uniques.</span><span class="sxs-lookup"><span data-stu-id="203ab-124">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="203ab-126">Les emplacements des messages du canal équipes et des discussions d’équipes sont uniquement conformes aux conversations d’équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres d’utilisateur et de groupe).</span><span class="sxs-lookup"><span data-stu-id="203ab-126">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="203ab-127">Les messages sont supprimés des emplacements de stockage appropriés, à savoir les boîtes aux lettres, le substrat et le service Chat.</span><span class="sxs-lookup"><span data-stu-id="203ab-127">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="203ab-128">Pour gérer les stratégies de rétention pour les fichiers teams stockés dans OneDrive entreprise et SharePoint, utilisez leurs stratégies de rétention.</span><span class="sxs-lookup"><span data-stu-id="203ab-128">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="203ab-129">Par conception, les stratégies de suppression des fichiers d’équipe sont configurées par le biais des emplacements SharePoint Online et OneDrive entreprise.</span><span class="sxs-lookup"><span data-stu-id="203ab-129">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="203ab-130">Par conséquent, il est possible qu’une stratégie supprime un fichier référencé dans une conversation ou un message de canal teams avant que ces messages soient supprimés.</span><span class="sxs-lookup"><span data-stu-id="203ab-130">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="203ab-131">Dans ce cas, le fichier s’affichera toujours dans le message Teams, mais si vous cliquez sur le fichier, vous recevez un message d’erreur « fichier introuvable » (cela peut également se produire en l’absence d’une stratégie, si une personne a supprimé manuellement un fichier à partir de SharePoint Online ou OneDrive entreprise).</span><span class="sxs-lookup"><span data-stu-id="203ab-131">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="203ab-132">Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, voir [vue d’ensemble des stratégies de](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)rétention.</span><span class="sxs-lookup"><span data-stu-id="203ab-132">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
