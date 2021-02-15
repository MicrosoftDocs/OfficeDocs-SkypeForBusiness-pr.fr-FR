---
title: Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter d’autres bases de données Skype Entreprise Server à un groupe de disponibilité AlwaysOn existant et découvrez les étapes supplémentaires nécessaires après avoir corrigé ou mis à niveau un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn dans Skype Entreprise Server.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826364"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="25d89-103">Gérer les bases de données avec un groupe de disponibilité AlwaysOn dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="25d89-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="25d89-104">Utilisez les étapes de cet article pour ajouter d’autres bases de données Skype Entreprise Server à un groupe de disponibilité AlwaysOn existant dans Skype Entreprise Server, et découvrez les étapes supplémentaires nécessaires après avoir corrigé ou mis à niveau un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="25d89-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="25d89-105">Ajouter des bases de données à un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="25d89-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="25d89-106">Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="25d89-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="25d89-107">Retenter vers le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="25d89-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="25d89-108">Dans le Générateur de topologie, définissez SQL Server FQDN du groupe de disponibilité AlwaysOn sur le FQDN du nœud principal de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="25d89-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="25d89-109">Ouvrez le Générateur de topologie, **sélectionnez Télécharger** la topologie à partir d’un déploiement existant, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="25d89-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="25d89-110">Développez Skype Entreprise Server, développez votre topologie et **développez SQL Server Stores.**</span><span class="sxs-lookup"><span data-stu-id="25d89-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="25d89-111">Cliquez avec le bouton droit SQL magasin du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="25d89-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="25d89-112">En bas de la page, dans la zone **SQL Server FQDN,** tapez le FQDN du nœud principal du groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="25d89-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="25d89-113">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="25d89-113">Publish the topology.</span></span> <span data-ttu-id="25d89-114">Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.**</span><span class="sxs-lookup"><span data-stu-id="25d89-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="25d89-115">Ensuite, dans la page de confirmation, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="25d89-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="25d89-116">Utilisez SQL Server Management Studio pour ajouter la nouvelle base de données au groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="25d89-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="25d89-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span><span class="sxs-lookup"><span data-stu-id="25d89-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="25d89-118">Après avoir corrigé un serveur principal faisant partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.</span><span class="sxs-lookup"><span data-stu-id="25d89-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="25d89-119">Installez la mise à jour sur votre ou vos serveurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="25d89-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="25d89-120">Exécutez la commande PowerShell suivante dans votre Skype Entreprise Management Shell (connecté avec un compte autorisé à appliquer les modifications aux bases de données SQL AlwaysOn) comme suit :</span><span class="sxs-lookup"><span data-stu-id="25d89-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="25d89-121">Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="25d89-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
