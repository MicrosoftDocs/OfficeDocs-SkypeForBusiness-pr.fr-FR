---
title: Ajouter un magasin SQL Server de conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="7ba37-103">Ajouter un magasin SQL Server de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="7ba37-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="7ba37-104">Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="7ba37-105">**Magasin SQL Server**: sélectionnez un serveur SQL Server existant et éventuellement une instance de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="7ba37-106">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="7ba37-107">Activez la case à cocher **Activer magasin SQL Server de mise en miroir** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="7ba37-108">Sélectionnez dans la liste **magasin SQL Server de la mise en miroir** un serveur SQL Server et une instance facultative agir en tant que miroir SQL Server pour le serveur SQL de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="7ba37-109">Cliquez sur **Nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir du serveur SQL de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7ba37-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="7ba37-110">Sélectionnez la liste **utiliser SQL Server témoin pour activer le basculement automatique de mise en miroir** SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="7ba37-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="7ba37-111">Le serveur témoin ne prend pas les données hôte ou de mise en miroir pour les serveurs de conversation permanente, mais elle garantit qu’un seul serveur SQL dans une configuration de mise en miroir SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="7ba37-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="7ba37-112">Cliquez sur **Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le serveur SQL de conversation permanente en témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="7ba37-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="7ba37-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="7ba37-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7ba37-114">Une fois que vous avez fini d’entrer les options de configuration de magasin SQL Server de ce pool et de procéder à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="7ba37-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7ba37-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="7ba37-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7ba37-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="7ba37-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ba37-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ba37-117">See also</span></span>

#### 

[<span data-ttu-id="7ba37-118">Planifier pour le serveur de conversation permanente dans Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ba37-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7ba37-119">Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie</span><span class="sxs-lookup"><span data-stu-id="7ba37-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7ba37-120">Configuration matérielle et logicielle requise pour Persistent Chat Server dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ba37-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7ba37-121">Configuration du serveur pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ba37-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7ba37-122">Concepts de base de topologie pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ba37-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="7ba37-123">Configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ba37-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

