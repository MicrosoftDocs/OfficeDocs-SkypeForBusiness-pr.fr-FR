---
title: Ajouter un magasin SQL Server de stockage de conformité de conversation permanente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez la conformité de sauvegarde que magasins SQL Server qui fournit des bases de données de sauvegarde pour le serveur de conversation permanente ou de la conformité Persistent Chat Server que magasins SQL Server.
ms.openlocfilehash: 2142ef6eba84d0f6645d735c1117b0be07a2a84f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875594"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="5a5a6-103">Ajouter un magasin SQL Server de stockage de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5a5a6-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="5a5a6-104">Vous configurez la conformité de sauvegarde que magasins SQL Server qui fournit des bases de données de sauvegarde pour le serveur de conversation permanente ou de la conformité Persistent Chat Server que magasins SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="5a5a6-105">**Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="5a5a6-106">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conformité de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="5a5a6-107">Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conformité de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="5a5a6-108">Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour la conversation permanente conformité de sauvegarde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="5a5a6-109">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="5a5a6-110">Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="5a5a6-111">Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="5a5a6-112">Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour la sauvegarde conformité de conversation permanente témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="5a5a6-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="5a5a6-114">Une fois que vous avez fini d’entrer les options de configuration de la banque de ce pool de sauvegarde SQL Server et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="5a5a6-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="5a5a6-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="5a5a6-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="5a5a6-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a5a6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a5a6-117">See also</span></span>

[<span data-ttu-id="5a5a6-118">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a5a6-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5a5a6-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a5a6-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="5a5a6-120">Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a5a6-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="5a5a6-121">Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a5a6-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="5a5a6-122">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a5a6-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
