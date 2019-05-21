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
# <a name="verify-configuration-settings"></a>Vérifier les paramètres de configuration

Vous pouvez valider la réplication des informations de configuration sur le serveur de périphérie en exécutant l’applet de contrôle Skype entreprise Server 2019 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion ou sur un ordinateur appartenant à un domaine sur lequel sont installés les composants principaux de Skype entreprise Server 2019 (OcsCore. msi). 
  
Les résultats initiaux risquent d’indiquer l’état «false» au lieu de «true» pour la réplication. Si tel est le cas, exécutez l’applet de connexion **Invoke-CsManagementStoreReplication** et attendez la fin de la réplication avant d’exécuter de nouveau **Get-CsManagementStoreReplicationStatus** . 
  

