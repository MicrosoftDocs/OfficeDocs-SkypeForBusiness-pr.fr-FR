---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server est basé sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819794"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="8f29a-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="8f29a-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="8f29a-105">Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server est basé sur la redondance des serveurs via la mise en pool.</span><span class="sxs-lookup"><span data-stu-id="8f29a-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="8f29a-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="8f29a-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="8f29a-107">Skype Entreprise Server nécessite au moins deux serveurs frontux pour activer la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="8f29a-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="8f29a-108">L’outil de planification utilise les critères suivants pour déterminer s’il ajoutera des serveurs supplémentaires afin de prendre en charge la haute disponibilité :</span><span class="sxs-lookup"><span data-stu-id="8f29a-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="8f29a-109">Si le déploiement contient au moins deux serveurs frontux, l’outil de planification n’ajoute pas de serveur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8f29a-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="8f29a-110">Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté.</span><span class="sxs-lookup"><span data-stu-id="8f29a-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="8f29a-111">Si le déploiement contient une conversation permanente, l’outil de planification ajoute un serveur supplémentaire, mais n’augmente pas le nombre de pool.</span><span class="sxs-lookup"><span data-stu-id="8f29a-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="8f29a-112">Par exemple, si le déploiement contient déjà quatre serveurs, l’outil de planification suggère l’ajout d’un serveur supplémentaire (pour un total de cinq serveurs), mais maintient un pool unique.</span><span class="sxs-lookup"><span data-stu-id="8f29a-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="8f29a-113">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8f29a-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8f29a-114">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8f29a-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="8f29a-115">Pour plus d’informations, voir [mise à niveau de Skype Entreprise vers Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="8f29a-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="8f29a-116">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8f29a-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="8f29a-117">L’outil de planification ajoute également une base de données SQL miroir pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="8f29a-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="8f29a-118">Par exemple, s’il existe une base de données SQL Server frontale, l’outil de planification ajoute l’autre base de données en tant que base de données miroir pour celle-ci et la nomme « base de données SQL frontale.</span><span class="sxs-lookup"><span data-stu-id="8f29a-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="8f29a-119">Pour plus d’informations sur la préparation de votre environnement pour la haute disponibilité, voir Planifier la haute disponibilité et la récupération d’urgence [dans Skype Entreprise Server.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="8f29a-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

