---
title: Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs du serveur de périphérie en tant que serveur à périphérie unique ou en tant qu’ordinateurs membres d’un pool de périphériques, vous pouvez configurer les paramètres de configuration de nom de serveur et d’adresse IP:'
ms.openlocfilehash: c9201cfde9f19391e1cee351de6d4efac00be9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302335"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Pour modifier les propriétés pour les ordinateurs du serveur de périphérie en tant que serveur à périphérie unique ou en tant qu’ordinateurs membres d’un pool de périphériques, vous pouvez configurer les paramètres de **configuration de nom de serveur et d’adresse IP** :
  
- **Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur tel qu’il est référencé dans le DNS (Domain Name System). 
    
- **Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau (NIC) interne de cet ordinateur.
    
- Vous configurez l' **adresse IPv4 externe** du **service Edge d’accès** associée à cet ordinateur.
    
    > [!IMPORTANT]
    > Si vous avez choisi d’utiliser une adresse IP unique pour la configuration de serveur Edge, vous pouvez uniquement modifier l’adresse IPv4 externe du service Edge d’accès. Les autres services Edge partageront la même adresse IPv4 que le service Edge d’accès. 
  
- S’il est possible de modifier, vous configurez l' **adresse IPv4 externe** du **service de conférence Web** associée à cet ordinateur.
    
- S’il est possible de procéder à la modification, vous configurez l' **adresse IPv4 externe** du service à l’extérieur **A/V** associée à cet ordinateur.
    
- S’il est possible de modifier, vous configurez l' **adresse IPv4 publique compatible NAT** associée à cet ordinateur.
    
    > [!IMPORTANT]
    > La propriété de configuration pour l' **adresse IPv4 publique compatible NAT** ne sera disponible qu’en modification si vous choisissez de fournir la traduction d’adresses réseau (NAT) pour le service Edge A/V.
  
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

