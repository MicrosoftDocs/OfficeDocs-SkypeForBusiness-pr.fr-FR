---
title: Déploiements locaux à forêts multiples de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805744"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Déploiements locaux à forêts multiples de Skype Room System
 
Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.
  
> [!NOTE]
> Pour pouvoir être déployé dans plusieurs forêts, Skype Room System nécessite Exchange Server 2013 CU6 publiée le 26 août 2014. Évitez de ré-utiliser une boîte aux lettres existante pour Skype Room System. Utilisez une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la re-créer) pour Skype Room System. Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir Connecter ou [restaurer une boîte aux lettres supprimée.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres. Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous Déploiements locaux à forêt unique. Après avoir créé une boîte aux lettres de ressources Exchange pour Skype Room System, activez le compte pour Skype Entreprise en suivant les étapes de la procédure d’activation des comptes Skype Room System pour Skype Entreprise dans le cadre de déploiements locaux à forêt unique.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1 : Créer une boîte aux lettres de ressources

Pour déployer Skype Room System dans un environnement à forêts multiples :
  
1. Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).
    
2. Exécutez les commandes suivantes dans Exchange Server Management Shell :
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2 : Modifier une boîte aux lettres de salle existante en boîte aux lettres de ressources Skype Room System (liée)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


