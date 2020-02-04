---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les banques SQL Server qui fournissent des bases de données pour le serveur de chat permanent ou le pool de serveurs de chat permanent.
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685057"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="082c1-103">Ajouter un magasin SQL Server de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="082c1-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="082c1-104">Vous configurez les banques SQL Server qui fournissent des bases de données pour le serveur de chat permanent ou le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="082c1-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="082c1-105">**SQL Server Store**: sélectionnez un serveur SQL Server existant et éventuellement une instance pour la discussion permanente.</span><span class="sxs-lookup"><span data-stu-id="082c1-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="082c1-106">Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, éventuellement, une nouvelle instance pour les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="082c1-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="082c1-107">Cochez la case **activer la mise en miroir SQL Server Store** pour configurer une base de données SQL Server et une instance optionnelle qui fournira une base de données en miroir pour les données de conversation persistante.</span><span class="sxs-lookup"><span data-stu-id="082c1-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="082c1-108">Dans la liste, sélectionnez à partir de la liste **mettre en miroir SQL Server Store** , SQL Server et instance facultative, comme miroir SQL Server pour le serveur SQL chat permanent.</span><span class="sxs-lookup"><span data-stu-id="082c1-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="082c1-109">Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, si vous le souhaitez, une nouvelle instance de la mise en miroir du serveur de conversation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="082c1-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="082c1-110">Sélectionnez la liste **utiliser un témoin de mise en miroir SQL Server pour activer le basculement automatique vers** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="082c1-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="082c1-111">Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de chat permanent, mais vérifie qu’un seul serveur SQL dans une configuration en miroir est le serveur SQL Server actif à tout moment.</span><span class="sxs-lookup"><span data-stu-id="082c1-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="082c1-112">Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en miroir SQL Server chat permanent.</span><span class="sxs-lookup"><span data-stu-id="082c1-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="082c1-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="082c1-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="082c1-114">Cliquez sur **suivant** lorsque vous avez fini d’entrer les options pour la configuration du magasin SQL Server du pool et continuez avec la définition du pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="082c1-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="082c1-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="082c1-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="082c1-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="082c1-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="082c1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="082c1-117">See also</span></span>

[<span data-ttu-id="082c1-118">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="082c1-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="082c1-119">Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="082c1-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="082c1-120">Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="082c1-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="082c1-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="082c1-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="082c1-122">Concepts de base de topologie pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="082c1-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="082c1-123">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="082c1-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
