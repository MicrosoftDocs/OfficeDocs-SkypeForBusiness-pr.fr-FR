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
ms.openlocfilehash: 140f413644360e8c776c48dbde5979cb4b57b04a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990120"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="6063c-104">Haute disponibilité (outil de planification)</span><span class="sxs-lookup"><span data-stu-id="6063c-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="6063c-105">Le jeu de haute disponibilité principal pour la plupart des rôles de serveur dans Skype pour Business Server repose sur la redondance des serveurs via un regroupement.</span><span class="sxs-lookup"><span data-stu-id="6063c-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="6063c-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="6063c-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="6063c-107">Skype pour Business Server nécessite au moins deux serveurs frontaux afin d’activer la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6063c-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="6063c-108">L’outil de planification utilise les critères suivants pour déterminer si elle ajoute des serveurs supplémentaires afin de prendre en charge la haute disponibilité :</span><span class="sxs-lookup"><span data-stu-id="6063c-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="6063c-109">Si le déploiement contient deux ou plusieurs serveurs frontaux, l’outil de planification n’ajoute pas un serveur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6063c-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="6063c-110">Si le déploiement contient un serveur Edge, un serveur supplémentaire est ajouté.</span><span class="sxs-lookup"><span data-stu-id="6063c-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="6063c-111">Si le déploiement contient la conversation permanente, l’outil de planification ajouter un serveur supplémentaire, mais pas augmenter le nombre de pool.</span><span class="sxs-lookup"><span data-stu-id="6063c-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="6063c-112">Par exemple, si le déploiement déjà contient quatre serveurs, l’outil de planification suggère Ajout d’un serveur supplémentaire (pour un total de cinq serveurs) mais conserve un seul pool.</span><span class="sxs-lookup"><span data-stu-id="6063c-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="6063c-113">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6063c-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6063c-114">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="6063c-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="6063c-115">Pour plus d’informations, voir [Skype pour les entreprises aux équipes Microsoft de mise à niveau](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="6063c-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="6063c-116">Si vous devez utiliser la conversation permanente, vos choix est à migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes ou continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6063c-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="6063c-117">L’outil de planification ajoute également une base de données miroir SQL pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="6063c-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="6063c-118">Par exemple, s’il existe une base de données du serveur frontal SQL, l’outil de planification seront ajoutez la base de données en tant que la base de données miroir pour celle-ci et nommez-le comme « Front-End miroir SQL base de données.</span><span class="sxs-lookup"><span data-stu-id="6063c-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="6063c-119">Pour plus d’informations sur la préparation de votre environnement pour une haute disponibilité, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="6063c-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

