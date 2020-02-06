---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur n’importe quel le domaine a été installé sur l’ordinateur sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi).
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812752"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="ba666-103">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="ba666-103">Verify configuration settings</span></span>

<span data-ttu-id="ba666-104">Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’applet de contrôle Skype entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur n’importe quel ordinateur appartenant à un domaine sur lequel les composants principaux de Skype entreprise Server 2019 (OcsCore. msi) sont installés.</span><span class="sxs-lookup"><span data-stu-id="ba666-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="ba666-105">Les résultats initiaux risquent d’indiquer l’état « false » au lieu de « true » pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="ba666-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="ba666-106">Si tel est le cas, exécutez l’applet de connexion **Invoke-CsManagementStoreReplication** et attendez la fin de la réplication avant d’exécuter de nouveau **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="ba666-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

