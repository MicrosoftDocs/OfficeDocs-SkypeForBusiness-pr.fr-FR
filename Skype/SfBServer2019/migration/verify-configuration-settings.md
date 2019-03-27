---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration pour le serveur Edge en exécutant la Skype pour l’applet de commande Business Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve le magasin Central de gestion, ou sur tout ordinateur sur lequel est installé Skype pour les composants principaux (OcsCore.msi) de Business Server 2019 joint au domaine.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889675"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="c296b-103">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="c296b-103">Verify configuration settings</span></span>

<span data-ttu-id="c296b-104">Vous pouvez valider la réplication des informations de configuration pour le serveur Edge en exécutant la Skype pour l’applet de commande Business Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin Central de gestion, ou Skype pour les composants principaux (OcsCore.msi) de Business Server 2019 est installé sur tout ordinateur sur lequel liés à un domaine.</span><span class="sxs-lookup"><span data-stu-id="c296b-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="c296b-105">Résultats initiale peuvent indiquer l’état en tant que valeur « False » au lieu de la valeur « True » pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="c296b-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="c296b-106">Dans ce cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** et attendez que la réplication soit terminée avant d’exécuter de nouveau la **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="c296b-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

