---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Le schéma principal de haute disponibilité pour la plupart des rôles serveur dans Skype entreprise Server 2015 est basé sur la redondance du serveur via le regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 53b98b72c70fcb624ab59fc7bfc3fbffadbd231a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685437"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="1a504-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="1a504-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="1a504-105">Le schéma principal de haute disponibilité pour la plupart des rôles serveur dans Skype entreprise Server 2015 est basé sur la redondance du serveur via le regroupement.</span><span class="sxs-lookup"><span data-stu-id="1a504-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="1a504-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="1a504-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="1a504-107">Skype entreprise Server 2015 nécessite au moins deux serveurs frontaux pour garantir une haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1a504-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="1a504-108">L’outil de planification utilise les critères suivants pour déterminer s’il ajoute des serveurs supplémentaires afin de prendre en charge une haute disponibilité :</span><span class="sxs-lookup"><span data-stu-id="1a504-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="1a504-109">Si le déploiement comporte au moins deux serveurs front-end, l’outil de planification n’ajoute pas de serveur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1a504-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="1a504-110">Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté.</span><span class="sxs-lookup"><span data-stu-id="1a504-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="1a504-111">Si le déploiement contient une conversation permanente, l’outil de planification ajoutera un serveur supplémentaire, mais n’augmentera pas le numéro de la liste.</span><span class="sxs-lookup"><span data-stu-id="1a504-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="1a504-112">Par exemple, si le déploiement comporte déjà quatre serveurs, l’outil de planification suggère l’ajout d’un serveur supplémentaire (pour un total de 5 serveurs), mais conserve un pool unique.</span><span class="sxs-lookup"><span data-stu-id="1a504-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="1a504-113">L’outil de planification ajoute également une base de données SQL miroir pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="1a504-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="1a504-114">Par exemple, si vous disposez d’une base de données SQL Server frontale, l’outil de planification ajoutera l’autre base de données en tant que base de données miroir pour celle-ci et la nommera en tant que base de données SQL miroir frontale.</span><span class="sxs-lookup"><span data-stu-id="1a504-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="1a504-115">Pour plus d’informations sur la préparation de votre environnement en vue d’une haute disponibilité, voir [prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="1a504-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

