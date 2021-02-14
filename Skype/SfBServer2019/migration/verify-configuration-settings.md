---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Get-CsManagementStoreReplicationStatus Skype Entreprise Server 2019 sur l’ordinateur interne sur lequel se trouve le magasin central de gestion, ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752146"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="ef648-103">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="ef648-103">Verify configuration settings</span></span>

<span data-ttu-id="ef648-104">Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’cmdlet Skype Entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion, ou sur tout ordinateur joint à un domaine sur lequel Skype Entreprise Server 2019 Core Components (OcsCore.msi) est installé.</span><span class="sxs-lookup"><span data-stu-id="ef648-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="ef648-105">Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ».</span><span class="sxs-lookup"><span data-stu-id="ef648-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="ef648-106">Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="ef648-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

