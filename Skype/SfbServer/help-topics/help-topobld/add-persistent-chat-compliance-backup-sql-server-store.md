---
title: Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez les magasins SQL Server de conformité de sauvegarde qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou les magasins SQL Server de conformité du serveur de conversation permanente.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218695"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="09a25-103">Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="09a25-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="09a25-104">Vous configurez les magasins SQL Server de conformité de sauvegarde qui fourniront des bases de données de sauvegarde pour le serveur de conversation permanente ou les magasins SQL Server de conformité du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="09a25-105">**Magasin SQL Server**: sélectionnez un serveur SQL Server existant et, éventuellement, une instance pour la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="09a25-106">Cliquez sur **nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour les données de conformité de la sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="09a25-107">Activez la case à cocher **activer la mise en miroir du magasin SQL Server** pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données mise en miroir pour les données de conformité de la sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="09a25-108">Dans la liste **magasin SQL Server de mise en miroir** , sélectionnez un serveur SQL Server et une instance facultative pour agir en tant que miroir SQL Server pour le serveur SQL Server de conformité de la sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="09a25-109">Cliquez sur **nouveau** pour définir un nouveau serveur SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="09a25-110">Sélectionnez la liste **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="09a25-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="09a25-111">Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de conversation permanente, mais garantit qu’un seul serveur SQL Server dans une configuration mise en miroir est le serveur SQL actif à tout moment.</span><span class="sxs-lookup"><span data-stu-id="09a25-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="09a25-112">Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server, éventuellement une instance pour le témoin de mise en miroir SQL Server de la sauvegarde de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="09a25-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="09a25-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="09a25-114">Une fois que vous avez terminé d’entrer les options pour la configuration du magasin SQL Server de sauvegarde de ce pool, cliquez sur **suivant** pour continuer la définition du pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="09a25-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="09a25-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="09a25-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="09a25-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="09a25-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09a25-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09a25-117">See also</span></span>

[<span data-ttu-id="09a25-118">Planifier le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="09a25-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="09a25-119">Configuration requise pour le serveur pour Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="09a25-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="09a25-120">Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="09a25-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="09a25-121">Configurer le service de conformité pour le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="09a25-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="09a25-122">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="09a25-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
