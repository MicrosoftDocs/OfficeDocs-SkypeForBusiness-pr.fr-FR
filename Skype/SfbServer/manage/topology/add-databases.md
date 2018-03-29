---
title: Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Apprenez à ajouter plus de Skype pour bases de données de serveur de l’entreprise à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="bf7ed-103">Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bf7ed-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf7ed-104">**Résumé :** Découvrez comment ajouter plusieurs Skype pour bases de données de serveur d’entreprise à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server 2015.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="bf7ed-105">Ajout de bases de données à un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="bf7ed-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="bf7ed-106">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="bf7ed-107">Basculer sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="bf7ed-108">Dans le Générateur de topologies, définissez le FQDN de SQL Server du groupe de disponibilité AlwaysOn pour le nom de domaine complet du nœud principal de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="bf7ed-109">Ouvrir le Générateur de topologies, sélectionnez **Télécharger la topologie de déploiement existant**et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="bf7ed-110">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bf7ed-111">Avec le bouton droit de la banque SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="bf7ed-112">Au bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="bf7ed-p103">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="bf7ed-116">Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bf7ed-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

