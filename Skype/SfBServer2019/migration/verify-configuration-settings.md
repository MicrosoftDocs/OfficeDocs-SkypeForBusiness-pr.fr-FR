---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur n’importe quel le domaine a été installé sur l’ordinateur sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi).
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307034"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="bfabd-103">Vérifier les paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="bfabd-103">Verify configuration settings</span></span>

<span data-ttu-id="bfabd-104">Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur un ordinateur appartenant à un domaine sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="bfabd-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="bfabd-105">Les résultats initiaux risquent d’indiquer l’état «false» au lieu de «true» pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="bfabd-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="bfabd-106">Si tel est le cas, exécutez l’applet de connexion **Invoke-CsManagementStoreReplication** et attendez la fin de la réplication avant d’exécuter de nouveau **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="bfabd-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

