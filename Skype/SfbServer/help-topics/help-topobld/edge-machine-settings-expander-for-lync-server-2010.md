---
title: Contour Machine paramètres Expander pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge sous la forme d’un seul serveur de transport Edge ou ordinateurs membres dans un pool d’arête, vous configurez le nom du serveur et les paramètres de configuration d’adresse IP :'
ms.openlocfilehash: d1bc35683ff70e1666a46d478aa97b3bcc3d5593
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Contour Machine paramètres Expander pour Lync Server 2010
 
Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge sous la forme d’un seul serveur de transport Edge ou ordinateurs membres dans un pool d’arête, vous configurez les paramètres de **configuration d’adresse IP et de nom de serveur** :
  
- **Nom interne ou le nom de domaine complet**: tapez le nom de l’ordinateur, car il est référencé dans le système de nom de domaine (DNS). 
    
- **Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) pour cet ordinateur.
    
- Vous configurez **service Edge d’accès** **adresse IPv4 externes** associés à cet ordinateur
    
    > [!IMPORTANT]
    > Si vous avez sélectionné utiliser une seule adresse IP pour la configuration du serveur de transport Edge, vous pourrez uniquement modifier l’adresse IPv4 externe pour le service Edge d’accès. Les autres services de bord partagent la même adresse IPv4 en tant que le service Edge d’accès. 
  
- Si elle est disponible pour les modifier, vous configurez **service de conférence Web** **adresse IPv4 externes** associés à cet ordinateur
    
- Si disponible pour les modifier, vous configurez la **A / V Edge service** **adresse IPv4 externes** associés à cet ordinateur
    
- Si elle est disponible pour les modifier, vous configurez **NAT activé les adresses IPv4 publiques** associées à cet ordinateur.
    
    > [!IMPORTANT]
    > La propriété de configuration pour **laquelle NAT est activé les adresses IPv4 publiques** n’est disponible pour modifier si vous avez choisi de fournir la traduction d’adresses réseau (NAT) pour l’un / V Edge service
  
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

