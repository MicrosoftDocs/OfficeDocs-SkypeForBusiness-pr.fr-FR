---
title: Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server.'
ms.openlocfilehash: e5217ba16234ea96f205d8ee89b6d31ac6b2df6c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372059"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="51299-103">Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="51299-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="51299-104">**Résumé :** Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="51299-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="51299-105">Ajout de bases de données à un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="51299-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="51299-106">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="51299-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="51299-107">Basculer sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="51299-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="51299-108">Dans le Générateur de topologie, définissez le nom de domaine complet SQL Server du groupe de disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="51299-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="51299-109">Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="51299-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="51299-110">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="51299-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="51299-111">Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="51299-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="51299-112">En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez dans le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="51299-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="51299-p103">Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="51299-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="51299-116">Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="51299-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

