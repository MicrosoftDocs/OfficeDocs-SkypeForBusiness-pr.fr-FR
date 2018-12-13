---
title: Déplacer les utilisateurs vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs vers Skype pour Business Online.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243996"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer les utilisateurs vers Skype Entreprise Online

Une fois que vous déplacez un utilisateur sur site à Skype pour Business Online, l’utilisateur interagit avec Skype pour Business Online pour ses fonctionnalités. Les contacts qui existaient sur site sera disponibles dans Skype pour Business Online, et toutes les réunions organisée par l’utilisateur pour l’avenir existantes sont mises à jour afin que les liens pointent sur Skype pour Business Online. Si l’utilisateur est activé pour une audioconférence, les réunions inclut également les coordonnées du rendez-vous.  Pour déplacer les utilisateurs d’un environnement sur site vers Skype pour Business Online, utilisez l’applet de commande Move-CsUser ou le Skype pour Business Server Control Panel, qui sont tous deux outils locale. 

Avant de déplacer des utilisateurs, veillez à consulter les [conditions requises](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer des utilisateurs vers le nuage.
 
## <a name="move-users-with-move-csuser"></a>Déplacer les utilisateurs avec Move-CsUser 

Move-CsUser est disponible à partir d’un Skype locale de fenêtre Business Management Shell PowerShell. Vous devez disposer de privilèges suffisants dans les deux l’environnement local ainsi que dans le client Office 365 comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un seul compte disposant de privilèges dans les deux environnements, ou vous pouvez démarrer une Skype dans les locaux de fenêtre Business Server Management Shell avec des informations d’identification dans les locaux et utiliser le `-Credential` paramètre pour spécifier les informations d’identification pour un Office 365 compte doté du rôle d’administration Office 365 nécessaire.

Pour déplacer un utilisateur en ligne à l’aide de Move-CsUser :

- Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez-paramètre cible avec la valeur « sipfed.online.lync. <span>com ».
- Si vous ne disposez pas d’un compte disposant des autorisations suffisantes dans les locaux et Office 365, utilisez le paramètre - credential pour fournir un compte disposant des autorisations suffisantes dans Office 365.
- Si le compte possédant des autorisations dans Office 365 ne se termine pas par « on.microsoft. <span>com », vous devez spécifier le paramètre - HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La séquence d’applet de commande suivante permet de déplacer un utilisateur à Skype pour Business Online et suppose que les informations d’identification Office 365 est un compte distinct et fourni comme entrée pour l’invite de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>Déplacer les utilisateurs avec Skype pour Business Server Control Panel 

1. Ouvrez le Skype pour le contrôle serveur Business application du Panneau de configuration.
2. Dans la navigation de gauche, choisissez **utilisateurs**.
3. Utiliser la **recherche** pour localiser les utilisateurs que vous souhaitez déplacer vers Skype pour Business Online.
4. Sélectionnez l’ou les utilisateurs, puis, dans la liste déroulante **Action** au-dessus de la liste, cliquez sur **déplacer les utilisateurs sélectionnés à Skype pour Business Online**.
5. Dans l’Assistant, cliquez sur **suivant**.
6. Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis **suivant** une fois plus de déplacer l’utilisateur.
8. Notez que les messages d’état en ce qui concerne la réussite ou l’échec sont fournis dans la partie supérieure de l’application le panneau de configuration principale, pas dans l’Assistant.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)