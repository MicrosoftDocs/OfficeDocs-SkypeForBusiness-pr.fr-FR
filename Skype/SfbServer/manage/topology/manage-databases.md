---
title: Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant et en savoir plus sur les étapes supplémentaires nécessaires après correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Serveur d’entreprise.'
ms.openlocfilehash: ca7a792e001c29e087b9b6ac1637029c90ea1ae9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222806"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="dff4b-103">Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="dff4b-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="dff4b-104">Utilisez les étapes de cet article pour ajouter plusieurs Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server et découvrez les étapes supplémentaires après avoir des correctifs ou mise à niveau d’un serveur principal qui fait partie d’un AlwaysOn Groupe de disponibilité dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="dff4b-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="dff4b-105">Ajouter des bases de données à un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dff4b-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="dff4b-106">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dff4b-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="dff4b-107">Basculer sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dff4b-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="dff4b-108">Dans le Générateur de topologie, définissez le nom de domaine complet SQL Server du groupe de disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="dff4b-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="dff4b-109">Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dff4b-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="dff4b-110">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dff4b-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="dff4b-111">Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="dff4b-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="dff4b-112">En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez dans le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dff4b-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="dff4b-113">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="dff4b-113">Publish the topology.</span></span> <span data-ttu-id="dff4b-114">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="dff4b-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="dff4b-115">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="dff4b-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="dff4b-116">Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="dff4b-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="dff4b-117">Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dff4b-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="dff4b-118">Après la mise à jour d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.</span><span class="sxs-lookup"><span data-stu-id="dff4b-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="dff4b-119">Installez la mise à jour sur votre Skype pour l’entreprise ou les serveurs.</span><span class="sxs-lookup"><span data-stu-id="dff4b-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="dff4b-120">Exécutez la commande PowerShell suivante dans votre Skype pour Business Management Shell (connecté avec un compte qui est correctement autorisé à appliquer les modifications apportées aux bases de données SQL AlwaysOn) comme suit :</span><span class="sxs-lookup"><span data-stu-id="dff4b-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="dff4b-121">Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="dff4b-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>