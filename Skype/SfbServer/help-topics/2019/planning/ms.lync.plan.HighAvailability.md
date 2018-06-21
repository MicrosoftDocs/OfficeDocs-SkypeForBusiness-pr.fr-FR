---
title: Haute disponibilité (outil de planification)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server repose sur la redondance des serveurs via un regroupement. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977263"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="c861f-104">Haute disponibilité (outil de planification)</span><span class="sxs-lookup"><span data-stu-id="c861f-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="c861f-105">Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server repose sur la redondance des serveurs via un regroupement.</span><span class="sxs-lookup"><span data-stu-id="c861f-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="c861f-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="c861f-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="c861f-107">Skype pour Business Server nécessite au moins deux serveurs frontaux afin d’activer la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c861f-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="c861f-108">L’outil de planification utilise les critères suivants pour déterminer si elle ajoute des serveurs supplémentaires afin de prendre en charge la haute disponibilité :</span><span class="sxs-lookup"><span data-stu-id="c861f-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="c861f-109">Si le déploiement contient deux ou plusieurs serveurs frontaux, l’outil de planification n’ajoute pas un serveur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c861f-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="c861f-110">Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté.</span><span class="sxs-lookup"><span data-stu-id="c861f-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="c861f-111">Si le déploiement contient la conversation permanente, l’outil de planification ajouter un serveur supplémentaire, mais pas augmenter le nombre de pool.</span><span class="sxs-lookup"><span data-stu-id="c861f-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="c861f-112">Par exemple, si le déploiement déjà contient quatre serveurs, l’outil de planification suggère Ajout d’un serveur supplémentaire (pour un total de cinq serveurs) mais conserve un seul pool.</span><span class="sxs-lookup"><span data-stu-id="c861f-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="c861f-113">L’outil de planification ajoute également une base de données miroir SQL pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="c861f-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="c861f-114">Par exemple, s’il existe une base de données du serveur frontal SQL, l’outil de planification seront ajoutez la base de données en tant que la base de données miroir pour celle-ci et nommez-le comme « Front-End miroir SQL base de données.</span><span class="sxs-lookup"><span data-stu-id="c861f-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="c861f-115">Pour plus d’informations sur la préparation de votre environnement pour une haute disponibilité, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="c861f-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

