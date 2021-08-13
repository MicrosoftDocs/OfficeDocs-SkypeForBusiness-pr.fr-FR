---
title: Expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés des ordinateurs serveurs Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, vous configurez les paramètres de configuration du nom du serveur et de l’adresse IP :'
ms.openlocfilehash: 6a66c84be19636410259eac953b099942dc3c1a41b6d3f75faf926d469795e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333636"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Pour modifier les propriétés des ordinateurs serveurs Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, vous configurez les paramètres de configuration du nom du serveur et de l’adresse **IP** :
  
- **Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur tel qu’il est référencé dans le DNS (Domain Name System). 
    
- **Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) de cet ordinateur.
    
- Vous configurez l’adresse **IPv4** externe du **service Edge** d’accès associé à cet ordinateur
    
    > [!IMPORTANT]
    > Si vous avez choisi d’utiliser une adresse IP unique pour la configuration du serveur Edge, vous ne pourrez modifier que l’adresse IPv4 externe pour le service Edge d’accès. Les autres services Edge partagent la même adresse IPv4 que le service Edge d’accès. 
  
- Si vous pouvez le modifier, vous configurez l’adresse **IPv4** externe du service de conférence **Web** associée à cet ordinateur
    
- Si disponible pour modification, vous configurez l’adresse **IPv4** externe du **service Edge A/V** associée à cet ordinateur
    
- Si vous pouvez le modifier, vous configurez l’adresse **IPv4 publique activée** pour NAT associée à cet ordinateur.
    
    > [!IMPORTANT]
    > La propriété de configuration de l’adresse **IPv4** publique activée pour NAT ne pourra être modifiée que si vous avez choisi de fournir la traduction d’adresses réseau (NAT) pour le service Edge A/V.
  
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

