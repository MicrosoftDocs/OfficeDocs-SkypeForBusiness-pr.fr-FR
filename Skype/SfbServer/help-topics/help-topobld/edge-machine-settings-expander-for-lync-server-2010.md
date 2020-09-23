---
title: Expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Pour modifier les propriétés des ordinateurs de serveur Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, configurez le nom du serveur et les paramètres de configuration de l’adresse IP :'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218925"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Pour modifier les propriétés des ordinateurs de serveur Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, configurez le **nom du serveur et les paramètres de configuration de l’adresse IP** :
  
- **Nom interne ou nom de domaine complet (FQDN**) : tapez le nom de l’ordinateur tel qu’il est référencé dans le DNS (Domain Name System). 
    
- **Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau (NIC) interne pour cet ordinateur.
    
- Vous configurez l' **adresse IPv4 externe** du **service Edge d’accès** associée à cet ordinateur
    
    > [!IMPORTANT]
    > Si vous avez choisi d’utiliser une adresse IP unique pour la configuration du serveur Edge, vous pourrez uniquement modifier l’adresse IPv4 externe du service Edge d’accès. Les autres services Edge partageront la même adresse IPv4 que le service Edge d’accès. 
  
- S’il est possible de modifier, vous configurez l' **adresse IPv4 externe** du **service de conférence Web** associée à cet ordinateur.
    
- S’il est possible de modifier, vous configurez l' **adresse IPv4 externe** du **service Edge A/V** associée à cet ordinateur.
    
- Si ce dernier est disponible pour la modification, vous configurez l' **adresse IPv4 publique à extension NAT** associée à cet ordinateur.
    
    > [!IMPORTANT]
    > La propriété de configuration de l' **adresse IPv4 publique à extension NAT** ne pourra être modifiée que si vous avez choisi de fournir une traduction d’adresses réseau (NAT) pour le service Edge A/V.
  
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

