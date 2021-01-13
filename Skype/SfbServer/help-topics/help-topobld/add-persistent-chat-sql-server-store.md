---
title: Ajouter un magasin SQL Server de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818654"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="21ffd-103">Ajouter un magasin SQL Server de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="21ffd-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="21ffd-104">Vous configurez les magasins SQL Server qui fourniront des bases de données pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="21ffd-105">**SQL Server :** sélectionnez un SQL Server existant et éventuellement une instance pour la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="21ffd-106">Cliquez **sur** Nouveau pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="21ffd-107">Activez **la case à cocher Activer SQL Server** de mise en miroir pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="21ffd-108">Sélectionnez dans la liste Mise en **miroir SQL Server** une instance SQL Server et facultative pour agir en tant que miroir SQL Server pour le SQL Server de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="21ffd-109">Cliquez **sur** Nouveau pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="21ffd-110">Sélectionnez la liste Utiliser **SQL Server** témoin de mise en miroir pour activer le SQL Server automatique qui agit en tant que serveur témoin dans les scénarios de failover.</span><span class="sxs-lookup"><span data-stu-id="21ffd-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="21ffd-111">Le serveur témoin ne reflète pas ou n’héberge pas de données pour les serveurs de conversation permanente, mais s’assure qu’une seule SQL Server dans une configuration en miroir est la SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="21ffd-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="21ffd-112">Cliquez **sur Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en miroir SQL Server conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="21ffd-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="21ffd-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="21ffd-114">Cliquez **sur** Suivant une fois que vous avez terminé d’entrer les options pour la configuration du magasin SQL Server de ce pool et pour passer à la définition du pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="21ffd-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="21ffd-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="21ffd-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="21ffd-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="21ffd-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21ffd-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21ffd-117">See also</span></span>

[<span data-ttu-id="21ffd-118">Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="21ffd-119">Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="21ffd-120">Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="21ffd-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="21ffd-122">Topology Basics for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="21ffd-123">Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ffd-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
