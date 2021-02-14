---
title: Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Vous configurez les magasins de conformité SQL Server sauvegarde qui fourniront des bases de données de sauvegarde pour les magasins de conformité du serveur de conversation permanente ou du serveur de SQL Server de conversation permanente.
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818714"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="7b3ce-103">Ajouter un magasin SQL Server de sauvegarde de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="7b3ce-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="7b3ce-104">Vous configurez les magasins de conformité SQL Server sauvegarde qui fourniront des bases de données de sauvegarde pour les magasins de conformité du serveur de conversation permanente ou du serveur de SQL Server de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="7b3ce-105">**SQL Server :** sélectionnez un SQL Server existant et éventuellement une instance pour la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="7b3ce-106">Cliquez **sur Nouveau** pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour les données de conformité de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="7b3ce-107">Activez la case **à cocher Activer SQL Server** de mise en miroir pour configurer une base de données SQL Server et une instance facultative qui fournira une base de données en miroir pour les données de conformité de sauvegarde de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="7b3ce-108">Dans la liste Mise en **miroir, SQL Server** stockez une instance SQL Server et facultative pour agir en tant que miroir SQL Server pour le service de conformité de la SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="7b3ce-109">Cliquez **sur** Nouveau pour définir une nouvelle SQL Server et éventuellement une nouvelle instance pour la mise en miroir SQL Server conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="7b3ce-110">Sélectionnez la liste Utiliser **SQL Server** témoin de mise en miroir pour activer le SQL Server automatique qui agit en tant que serveur témoin dans les scénarios de failover.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="7b3ce-111">Le serveur témoin ne reflète pas ou n’héberge pas de données pour les serveurs de conversation permanente, mais s’assure qu’une seule SQL Server dans une configuration en miroir est la SQL Server active à tout moment.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="7b3ce-112">Cliquez **sur Nouveau** pour définir un nouveau témoin SQL Server éventuellement une instance pour le témoin de mise en miroir de la SQL Server de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="7b3ce-113">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7b3ce-114">Cliquez **sur** Suivant une fois que vous avez terminé d’entrer les options pour la configuration du magasin de SQL Server de sauvegarde de ce pool et pour passer à la définition du pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7b3ce-115">Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7b3ce-116">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="7b3ce-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b3ce-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b3ce-117">See also</span></span>

[<span data-ttu-id="7b3ce-118">Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b3ce-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7b3ce-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b3ce-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7b3ce-120">Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b3ce-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7b3ce-121">Configurer le service de conformité pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b3ce-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="7b3ce-122">Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b3ce-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
