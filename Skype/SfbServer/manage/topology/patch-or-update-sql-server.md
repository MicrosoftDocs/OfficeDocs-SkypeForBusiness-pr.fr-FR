---
title: Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Résumé : Découvrez les étapes supplémentaires nécessaires après correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982985"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="f4c00-103">Correctifs ou mise à jour de SQL Server dans un groupe de disponibilité AlwaysOn dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f4c00-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="f4c00-104">**Résumé :** Découvrez les étapes supplémentaires après avoir des correctifs ou mise à niveau d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f4c00-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="f4c00-105">Après la mise à jour d’un serveur principal qui fait partie d’un groupe de disponibilité AlwaysOn, vous devez republier la topologie.</span><span class="sxs-lookup"><span data-stu-id="f4c00-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="f4c00-106">Mise à jour corrective ou la mise à jour de SQL Server qui fait partie d’un groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f4c00-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="f4c00-107">Installez la mise à jour sur votre Skype pour l’entreprise ou les serveurs.</span><span class="sxs-lookup"><span data-stu-id="f4c00-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="f4c00-108">Exécutez la commande PowerShell suivante dans votre Skype pour Business Management Shell (connecté avec un compte qui est correctement autorisé à appliquer les modifications apportées aux bases de données SQL AlwaysOn) comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4c00-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="f4c00-109">Où [sqlpool.contoso.com] est remplacé par le nom de domaine complet (FQDN) de votre groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f4c00-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

