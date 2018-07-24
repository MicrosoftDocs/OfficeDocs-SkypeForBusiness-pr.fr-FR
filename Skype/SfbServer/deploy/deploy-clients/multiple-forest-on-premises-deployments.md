---
title: Déploiements locaux de plusieurs forêts Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
ms.openlocfilehash: 35a6d5401b2e554cbfaa1e97c42e9a88bc3558ed
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966058"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Déploiements locaux de plusieurs forêts Skype Room System
 
Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
  
> [!NOTE]
> Pour pouvoir déployer dans plusieurs forêts, Skype salle système requiert Exchange Server 2013 CU6 publié le 26 août 2014. Évitez de réutilisation d’une boîte aux lettres existant pour le système de salle Skype. Utiliser une nouvelle (ancienne boîte aux lettres de supprimer et recréer) boîte aux lettres de ressources de système de salle Skype. Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [Connect ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Après la création de la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations. Après avoir créé une boîte aux lettres de ressources Exchange Skype salle système, activez le compte pour Skype pour les entreprises en suivant les étapes de l’activation de comptes de système salle Skype pour Skype pour les entreprises dans les déploiements sur site de forêt unique.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1 : créer une nouvelle boîte aux lettres de ressources

Pour déployer le système de salle Skype dans un environnement à forêts multiples :
  
1. Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).
    
2. Exécutez les commandes suivantes dans le Exchange Server Management Shell :
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2 : Modifier une boîte aux lettres de salle à la boîte aux lettres de ressources (lié) de système de salle de Skype

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


