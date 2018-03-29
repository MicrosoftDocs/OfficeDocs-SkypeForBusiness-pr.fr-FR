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
description: Vous configurez les magasins de sauvegarde de SQL Server qui fourniront les bases de données de sauvegarde pour le serveur de Chat permanent ou d’un pool de serveur de conversation persistant.
ms.openlocfilehash: 67dc09cca54f0079fc4b7bac16355bbd8dc64633
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="de8c3-103">Ajouter un magasin SQL Server de stockage de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="de8c3-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="de8c3-104">Vous configurez les magasins de sauvegarde de SQL Server qui fourniront les bases de données de sauvegarde pour le serveur de Chat permanent ou d’un pool de serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="de8c3-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="de8c3-105">**Stockage de SQL Server**: sélectionnez un SQL Server existant et éventuellement d’une instance de Chat persistant.</span><span class="sxs-lookup"><span data-stu-id="de8c3-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="de8c3-106">Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance pour les données de sauvegarde Chat persistant.</span><span class="sxs-lookup"><span data-stu-id="de8c3-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="de8c3-107">Activez la case à cocher **mise en miroir de la banque d’informations de SQL Server permettent** de configurer une base de données de SQL Server et l’instance en option qui offre une mise en miroir de la base de données pour les données de sauvegarde Chat persistant.</span><span class="sxs-lookup"><span data-stu-id="de8c3-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="de8c3-108">Sélectionnez dans la liste **de SQL Server mise en miroir stocker** une de SQL Server et une instance facultatif en tant que la mise en miroir de SQL Server pour le Chat persistant de sauvegarde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de8c3-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="de8c3-109">Cliquez sur **Nouveau** pour définir une nouvelle de SQL Server et éventuellement une nouvelle instance de la mise en miroir de SQL Server de la conversation permanent.</span><span class="sxs-lookup"><span data-stu-id="de8c3-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="de8c3-110">Sélectionnez la liste **témoin pour permettre le basculement automatique de la mise en miroir de SQL Server d’utiliser** un SQL Server qui jouera le rôle de serveur témoin dans les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="de8c3-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="de8c3-111">Le serveur témoin est pas les données en miroir ou d’hôte pour les serveurs Chat persistants, mais garantit que seul SQL Server dans une configuration en miroir est le SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="de8c3-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="de8c3-112">Cliquez sur **Nouveau** pour définir un nouveau rappel de SQL Server éventuellement une instance pour la de SQL Server sauvegarde de conversation permanent témoin de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="de8c3-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="de8c3-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="de8c3-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="de8c3-114">Une fois que vous avez terminé d’entrer les options de configuration de la banque de ce pool de sauvegarde de SQL Server et de procéder à la définition de pool persistant Chat Server, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="de8c3-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="de8c3-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="de8c3-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="de8c3-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="de8c3-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de8c3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de8c3-117">See also</span></span>

#### 

[<span data-ttu-id="de8c3-118">Plan pour un serveur de conversation permanents dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="de8c3-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="de8c3-119">Configuration serveur requise pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="de8c3-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="de8c3-120">Matérielle et logicielle requise pour le serveur Chat persistant dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="de8c3-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="de8c3-121">Configuration de haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="de8c3-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

