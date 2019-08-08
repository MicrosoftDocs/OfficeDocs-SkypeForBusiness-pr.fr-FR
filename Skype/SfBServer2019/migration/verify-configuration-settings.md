---
title: Vérifier les paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 Get-CsManagementStoreReplicationStatus sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur n’importe quel le domaine a été installé sur l’ordinateur sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi).
ms.openlocfilehash: 5beb3c80bbc4c2f9a73fe68b9d99d7752598c680
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240937"
---
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur un ordinateur appartenant à un domaine sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi). 
  
Les résultats initiaux risquent d’indiquer l’état «false» au lieu de «true» pour la réplication. Si tel est le cas, exécutez l’applet de connexion **Invoke-CsManagementStoreReplication** et attendez la fin de la réplication avant d’exécuter de nouveau **Get-CsManagementStoreReplicationStatus** . 
  

