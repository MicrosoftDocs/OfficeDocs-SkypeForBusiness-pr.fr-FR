---
title: Déploiements locaux de plusieurs forêts Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
ms.openlocfilehash: b5a0a2615f8174ea5e7d56dcaf0830765365bb48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Déploiements locaux de plusieurs forêts Skype Room System
 
Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
  
> [!NOTE]
> Pour le déploiement dans plusieurs forêts, Skype espace système nécessite Exchange Server 2013 CU6, publié le 26 août 2014. Évitez de nouveau à l’aide d’une boîte aux lettres existante pour système de salle de Skype. Utiliser une nouvelle (supprimer l’ancienne boîte aux lettres et les recréer) boîte aux lettres de ressources pour le système de salle de Skype. Pour restaurer les réunions perdues lors de la suppression de la boîte aux lettres, voir [se connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx). 
  
Après la création de la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations. Après la création d’une boîte aux lettres de ressource Exchange pour système de salle de Skype, activer le compte pour Skype pour entreprise, en suivant les étapes de l’activation de comptes de système salle Skype pour Skype pour les entreprises dans les déploiements sur site de forêt unique.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1 : créer une nouvelle boîte aux lettres de ressources

Pour déployer le système d’espace Skype dans un environnement à plusieurs forêts :
  
1. Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).
    
2. Exécutez les commandes suivantes dans le Exchange Server Management Shell :
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2 : Modifier une boîte aux lettres de salle existant pour la boîte aux lettres de la ressource (liée) système de salle de Skype

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1

```


