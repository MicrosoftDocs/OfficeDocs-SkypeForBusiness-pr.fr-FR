---
title: Gérer des bases de données à l’aide d’un groupe de disponibilité AlwaysOn dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter des bases de données Skype entreprise Server à un groupe de disponibilité AlwaysOn existant et en savoir plus sur les étapes supplémentaires nécessaires après le correctif ou la mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.'
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991539"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="7e304-103">Gérer des bases de données à l’aide d’un groupe de disponibilité AlwaysOn dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7e304-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="7e304-104">Suivez les étapes décrites dans cet article pour ajouter d’autres bases de données Skype entreprise Server à un groupe de disponibilité AlwaysOn existant dans Skype entreprise Server et en savoir plus sur les étapes supplémentaires nécessaires après le correctif ou la mise à niveau d’un serveur principal qui fait partie d’un serveur AlwaysOn. Groupe disponibilité dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7e304-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="7e304-105">Ajouter des bases de données à un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7e304-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="7e304-106">Ouvrez SQL Server Management Studio, puis accédez au groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7e304-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="7e304-107">Basculez vers le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7e304-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="7e304-108">Dans le générateur de topologie, définissez le nom de domaine complet SQL Server du groupe disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="7e304-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="7e304-109">Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e304-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="7e304-110">Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7e304-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="7e304-111">Cliquez avec le bouton droit sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7e304-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="7e304-112">En bas de la page, dans la zone **nom de domaine complet (FQDN) SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal du groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7e304-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="7e304-113">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="7e304-113">Publish the topology.</span></span> <span data-ttu-id="7e304-114">Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="7e304-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="7e304-115">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7e304-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="7e304-116">Utilisez SQL Server Management Studio pour ajouter la nouvelle base de données dans le groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7e304-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="7e304-117">Correctif ou mise à jour d’un serveur SQL Server dans un groupe disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7e304-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="7e304-118">Après avoir corrigé un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.</span><span class="sxs-lookup"><span data-stu-id="7e304-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="7e304-119">Installez la mise à jour sur votre serveur ou vos serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7e304-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="7e304-120">Exécutez la commande PowerShell suivante dans votre shell de gestion de Skype entreprise (connectez-vous à l’aide d’un compte qui a été approprié pour appliquer les modifications aux bases de données SQL AlwaysOn) comme suit :</span><span class="sxs-lookup"><span data-stu-id="7e304-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="7e304-121">Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7e304-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
