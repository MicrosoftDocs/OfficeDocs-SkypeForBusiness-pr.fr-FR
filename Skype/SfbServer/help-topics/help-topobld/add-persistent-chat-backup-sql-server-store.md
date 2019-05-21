---
title: Ajouter un magasin SQL Server de stockage de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Vous configurez les banques SQL Server de sauvegarde qui fournissent des bases de données de sauvegarde pour le serveur de chat permanent ou le pool de serveurs de chat permanent.
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304652"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="b8ce2-103">Ajouter un magasin SQL Server de stockage de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b8ce2-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="b8ce2-104">Vous configurez les banques SQL Server de sauvegarde qui fournissent des bases de données de sauvegarde pour le serveur de chat permanent ou le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="b8ce2-105">**SQL Server Store**: sélectionnez un serveur SQL Server existant et éventuellement une instance pour la discussion permanente.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="b8ce2-106">Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, éventuellement, une nouvelle instance pour les données de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="b8ce2-107">Cochez la case **activer la mise en miroir SQL Server Store** pour configurer une base de données SQL Server et une instance optionnelle qui fournira une base de données en miroir pour les données de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="b8ce2-108">Dans la liste, sélectionnez à partir de la liste **mettre en miroir SQL Server Store** un serveur SQL Server et une instance facultative pour faire office de miroir SQL Server pour le serveur SQL Server de sauvegarde de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="b8ce2-109">Cliquez sur **nouveau** pour définir un nouveau serveur SQL et, si vous le souhaitez, une nouvelle instance de la mise en miroir du serveur de conversation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="b8ce2-110">Sélectionnez la liste **utiliser un témoin de mise en miroir SQL Server pour activer le basculement automatique vers** un serveur SQL qui fera office de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="b8ce2-111">Le serveur témoin ne met pas en miroir ou n’héberge pas de données pour les serveurs de chat permanent, mais vérifie qu’un seul serveur SQL dans une configuration en miroir est le serveur SQL Server actif à tout moment.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="b8ce2-112">Cliquez sur **nouveau** pour définir un nouveau témoin SQL Server en option une instance pour le témoin de mise en miroir SQL Server du serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="b8ce2-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b8ce2-114">Cliquez sur **suivant** lorsque vous avez fini d’entrer les options pour la configuration de sauvegarde du magasin SQL Server du pool et de continuer avec la définition du pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="b8ce2-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="b8ce2-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="b8ce2-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8ce2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8ce2-117">See also</span></span>

[<span data-ttu-id="b8ce2-118">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8ce2-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b8ce2-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8ce2-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="b8ce2-120">Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8ce2-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="b8ce2-121">Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8ce2-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
