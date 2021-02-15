---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server 2015 est basé sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: a866784f94dd2e2c861aa93c482b40946da7ac7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829004"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="f3f14-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="f3f14-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="f3f14-105">Le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Skype Entreprise Server 2015 est basé sur la redondance des serveurs via la mise en pool.</span><span class="sxs-lookup"><span data-stu-id="f3f14-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="f3f14-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="f3f14-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="f3f14-107">Skype Entreprise Server 2015 nécessite au moins deux serveurs frontux pour activer la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f3f14-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="f3f14-108">L’outil de planification utilise les critères suivants pour déterminer s’il ajoutera des serveurs supplémentaires afin de prendre en charge la haute disponibilité :</span><span class="sxs-lookup"><span data-stu-id="f3f14-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="f3f14-109">Si le déploiement contient au moins deux serveurs frontux, l’outil de planification n’ajoute pas de serveur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f3f14-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="f3f14-110">Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté.</span><span class="sxs-lookup"><span data-stu-id="f3f14-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="f3f14-111">Si le déploiement contient une conversation permanente, l’outil de planification ajoute un serveur supplémentaire, mais n’augmente pas le nombre de pool.</span><span class="sxs-lookup"><span data-stu-id="f3f14-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="f3f14-112">Par exemple, si le déploiement contient déjà quatre serveurs, l’outil de planification suggère l’ajout d’un serveur supplémentaire (pour un total de cinq serveurs), mais maintient un pool unique.</span><span class="sxs-lookup"><span data-stu-id="f3f14-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="f3f14-113">L’outil de planification ajoute également une base de données SQL miroir pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="f3f14-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="f3f14-114">Par exemple, s’il existe une base de données SQL Server frontale, l’outil de planification ajoute l’autre base de données en tant que base de données miroir pour celle-ci et la nomme « base de données SQL frontale.</span><span class="sxs-lookup"><span data-stu-id="f3f14-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="f3f14-115">Pour plus d’informations sur la préparation de votre environnement pour la haute disponibilité, voir [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="f3f14-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

