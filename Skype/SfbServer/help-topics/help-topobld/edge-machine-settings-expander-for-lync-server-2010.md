---
title: Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge en tant qu’un serveur de périphérie unique ou en tant qu’ordinateurs membres d’un pool de serveurs Edge, vous configurez le nom du serveur et les paramètres de configuration d’adresses IP :'
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891539"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge en tant qu’un serveur de périphérie unique ou en tant qu’ordinateurs membres d’un pool de serveurs Edge, configurer les paramètres de **configuration d’adresse IP et de nom de serveur** :
  
- **Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur car il est référencé dans le système de nom de domaine (DNS). 
    
- **Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) pour cet ordinateur.
    
- Vous configurez **service Edge d’accès** **adresse IPv4 externe** associé à cet ordinateur
    
    > [!IMPORTANT]
    > Si vous avez sélectionné à utiliser une adresse IP unique pour la configuration du serveur Edge, vous pourrez uniquement modifier l’adresse IPv4 externe pour le service Edge d’accès. Autres services Edge partagent la même adresse IPv4 en tant que service Edge d’accès. 
  
- Si elle est disponible pour le modifier, vous configurez **service de conférence Web** **adresse IPv4 externe** associé à cet ordinateur
    
- Si Modifier disponible, configurez la **A / V Edge service** **adresse IPv4 externe** associé à cet ordinateur
    
- Si elle est disponible pour modifier, vous configurez l' **adresse IPv4 publique du NAT activé** associée à cet ordinateur.
    
    > [!IMPORTANT]
    > La propriété de configuration pour **laquelle NAT est activé les adresse IPv4 publique** ne seront disponible pour modifier si vous avez choisi pour fournir la traduction d’adresses réseau (NAT) a / V Edge service
  
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

