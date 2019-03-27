---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsque vous exécutez l’applet de commande Move-CsUser, vous pouvez rencontrer une défaillance, car les informations utilisateur entre les Services de domaine Active Directory (AD DS) et le Skype pour les bases de données métiers Server 2019 ne sont pas synchronisés, car la réplication initiale est incomplète. Le temps que nécessaire à la réussite de la Skype pour la synchronisation initiale du service Business Server 2019 User Replicator varie selon le nombre de contrôleurs de domaine qui sont hébergées dans la forêt Active Directory qui héberge le Skype pour les entreprises Pool de serveur 2019. Le Skype pour le processus de synchronisation initiale du service Business Server 2019 réplicateur se produit lorsque le Skype pour Business Server 2019 serveur frontal est démarré pour la première fois. Après cela, la synchronisation puis repose sur l’intervalle du réplicateur d’utilisateurs. Effectuez les étapes suivantes pour vérifier la réplication utilisateur est terminée avant d’exécuter l’applet de commande Move-CsUser.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889507"
---
# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

Lorsque vous exécutez l’applet de commande **Move-CsUser** , vous pouvez rencontrer une défaillance si les informations utilisateur entre les Services de domaine Active Directory (AD DS) et le Skype pour les bases de données métiers Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps que nécessaire à la réussite de la Skype pour la synchronisation initiale du service Business Server 2019 User Replicator varie selon le nombre de contrôleurs de domaine qui sont hébergées dans la forêt Active Directory qui héberge le Skype pour les entreprises Pool de serveur 2019. Le Skype pour le processus de synchronisation initiale du service Business Server 2019 réplicateur se produit lorsque le Skype pour Business Server 2019 serveur frontal est démarré pour la première fois. Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Effectuez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d’exécuter l’applet de commande **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Pour vérifier que la réplication utilisateur est terminée

1. Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    
2. Cliquez sur le menu **Démarrer** , puis cliquez sur **exécuter**. 
    
3. Entrez **eventvwr.exe**, puis cliquez sur **OK**.
    
4. Dans l’Observateur d’événements, cliquez sur **journaux des Applications et des Services** pour le développer, puis sélectionnez Skype pour Business Server. 
    
5. Dans le volet **Actions** , cliquez sur **Filtrer le journal actuel**.
    
6. Dans la liste de **sources d’événements** , cliquez sur **LS User Replicator**.
    
7. Dans ** \<tous les ID d’événement\>**, entrez **30024**, puis cliquez sur **OK**. 
    
8. Dans la liste des événements filtrés, sous l’onglet **Général** , recherchez une entrée qui indique que la réplication utilisateur a réussi. 
    

