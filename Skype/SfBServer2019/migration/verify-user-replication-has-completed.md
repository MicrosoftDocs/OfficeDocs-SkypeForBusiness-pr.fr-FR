---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsque vous exécutez l’applet de contrôle Move-CsUser, il est possible que vous constatiez un échec en raison du fait que les informations utilisateur entre les services de domaine Active Directory (AD DS) et celles de Skype entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service de réplicateur d’utilisateurs Skype entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le Skype entreprise. Pool serveur 2019. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Skype entreprise Server 2019 se produit lorsque le serveur frontal de Skype entreprise Server 2019 est démarré pour la première fois. Après cela, la synchronisation est alors basée sur l’intervalle du réplicateur d’utilisateurs. Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet de commande Move-CsUser.
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280645"
---
# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

Lorsque vous exécutez l’applet de contrôle **Move-Csuser** , il est possible que vous soyez en panne si les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service de réplicateur d’utilisateurs Skype entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le Skype entreprise. Pool serveur 2019. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Skype entreprise Server 2019 se produit lorsque le serveur frontal de Skype entreprise Server 2019 est démarré pour la première fois. Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet **de commande Move-Csuser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Pour vérifier que la réplication des utilisateurs est terminée

1. Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
    
2. Cliquez sur le menu **Démarrer** , puis sur **exécuter**. 
    
3. Entrez **eventvwr. exe**, puis cliquez sur **OK**.
    
4. Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Skype entreprise Server. 
    
5. Dans le volet **actions** , cliquez sur **filtrer le journal actuel**.
    
6. Dans la liste **sources d’événements** , cliquez sur réplicateur d' **utilisateurs LS**.
    
7. Dans ** \<tous les ID\>d’événement**, entrez **30024**, puis cliquez sur **OK**. 
    
8. Dans la liste des événements filtrés, sous l’onglet **général** , recherchez une entrée indiquant que la réplication des utilisateurs s’est déroulée correctement. 
    

