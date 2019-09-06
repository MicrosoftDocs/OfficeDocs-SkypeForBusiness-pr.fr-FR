---
title: Déploiements locaux de plusieurs forêts Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775039"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Déploiements locaux de plusieurs forêts Skype Room System
 
Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
  
> [!NOTE]
> Pour effectuer un déploiement dans plusieurs forêts, le système de salle Skype nécessite Exchange Server 2013 CU6 publiée le 26 août 2014. Évitez d’utiliser une boîte aux lettres existante pour le système de salle Skype. Utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et recréer) pour les systèmes de salle Skype. Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Après la création de la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations. Après la création d’une boîte aux lettres de ressources Exchange pour le système de salle Skype, activez le compte pour Skype entreprise en suivant les étapes de la rubrique activation de comptes de votre système de salle Skype pour Skype entreprise dans le cadre de déploiements locaux d’une seule forêt.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1 : créer une nouvelle boîte aux lettres de ressources

Pour déployer le système de salle Skype dans un environnement multiforêt :
  
1. Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).
    
2. Exécutez les commandes suivantes dans le Exchange Server Management Shell :
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2 : remplacer une boîte aux lettres de salle existante par une boîte aux lettres de ressources liée au système de salle Skype

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


