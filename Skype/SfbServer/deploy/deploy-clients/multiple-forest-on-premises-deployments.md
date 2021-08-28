---
title: Skype Déploiements locaux à forêts multiples du système de salle
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.
ms.openlocfilehash: 944042777174539b9b9f0a1d49754d9234a1d255
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609941"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Déploiements locaux à forêts multiples du système de salle
 
Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.
  
> [!NOTE]
> Pour être déployé dans plusieurs forêts, Skype Room System nécessite Exchange Server 2013 CU6 publiée le 26 août 2014. Évitez de ré-utiliser une boîte aux lettres existante pour Skype Room System. Utilisez une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la re-créer) pour Skype Room System. Pour restaurer les réunions perdues en supprimant la boîte aux lettres, consultez [la Connecter ou restituer une boîte aux lettres supprimée.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres. Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous Déploiements locaux à forêt unique. Après avoir créé une boîte aux lettres de ressources Exchange pour Skype Room System, activez le compte pour Skype Entreprise en suivant les étapes de l’activation des comptes Skype Room System pour Skype Entreprise dans le cadre de déploiements locaux à forêt unique.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1 : Créer une boîte aux lettres de ressources

Pour déployer Skype Room System dans un environnement à forêts multiples :
  
1. Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).
    
2. Exécutez les commandes suivantes dans Exchange Server Management Shell :
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2 : Modifier une boîte aux lettres de salle existante Skype boîte aux lettres de ressources (liée) du système de salle

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```