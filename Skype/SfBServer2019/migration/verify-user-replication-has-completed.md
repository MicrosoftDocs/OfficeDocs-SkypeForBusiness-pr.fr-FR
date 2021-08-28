---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Lors de l’exécution de la cmdlet Move-CsUser, vous pouvez être en panne car les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype Entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service réplicateur d’utilisateurs Skype Entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Skype Entreprise Server 2019. Le Skype Entreprise Server synchronisation initiale du service réplicateur d’utilisateurs 2019 se produit lorsque le serveur frontal Skype Entreprise Server 2019 est démarré pour la première fois. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Exécutez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d'Move-CsUser cmdlet.
ms.openlocfilehash: 893702b18b376edc32e946998aeead122bf3ed68
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599699"
---
# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

Lors de l’exécution de l’cmdlet **Move-CsUser,** vous pouvez être en panne si les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype Entreprise Server 2019 ne sont pas synchronisées car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service réplicateur d’utilisateurs Skype Entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Skype Entreprise Server 2019. Le Skype Entreprise Server synchronisation initiale du service réplicateur d’utilisateurs 2019 se produit lorsque le serveur frontal Skype Entreprise Server 2019 est démarré pour la première fois. Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Exécutez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d’exécutez l’cmdlet **Move-CsUser.** 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Pour vérifier que la réplication utilisateur est terminée

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
2. Cliquez sur le menu **Démarrer**, puis sur **Exécuter**. 
    
3. Entrez **eventvwr.exe**, puis cliquez sur **OK**.
    
4. Dans l’Observateur d’événements, cliquez sur **les journaux Applications et services** pour le développer, puis sélectionnez Skype Entreprise Server. 
    
5. Dans le volet **Actions**, cliquez sur **Filtrer le journal actuel**.
    
6. Dans la liste **Sources de l’événement**, cliquez sur **LS User Replicator**.
    
7. Dans **\<All Event IDs\>** , entrez **30024,** puis cliquez sur **OK**. 
    
8. Dans la liste des événements filtrés, sous l’onglet **Général,** recherchez une entrée qui indique que la réplication utilisateur s’est correctement terminée. 
    

