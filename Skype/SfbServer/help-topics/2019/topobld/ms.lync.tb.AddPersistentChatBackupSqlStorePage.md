---
title: Ajouter un magasin SQL Server de stockage de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Vous configurez les magasins de sauvegarde SQL Server qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: feb4b212c24bc6764dc35f3b4f238be655d50c7e
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="e01b7-103">Ajouter un magasin SQL Server de stockage de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="e01b7-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="e01b7-104">Vous configurez les magasins de sauvegarde SQL Server qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e01b7-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="e01b7-105">**Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e01b7-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="e01b7-106">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e01b7-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="e01b7-107">Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e01b7-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="e01b7-108">Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour la conversation permanente sauvegarde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e01b7-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="e01b7-109">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e01b7-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="e01b7-110">Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="e01b7-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="e01b7-111">Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e01b7-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="e01b7-112">Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour la conversation permanente sauvegarde SQL Server témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="e01b7-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="e01b7-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="e01b7-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="e01b7-114">Une fois que vous avez fini d’entrer les options de configuration de la banque de ce pool de sauvegarde SQL Server et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="e01b7-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="e01b7-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="e01b7-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="e01b7-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="e01b7-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e01b7-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e01b7-117">See also</span></span>

#### 

[<span data-ttu-id="e01b7-118">Planifier pour le serveur de conversation permanente dans Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01b7-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e01b7-119">Configuration du serveur pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01b7-119">Server requirements for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="e01b7-120">Configuration matérielle et logicielle requise pour Persistent Chat Server dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01b7-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="e01b7-121">Configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01b7-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

