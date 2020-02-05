---
title: Déplacer des utilisateurs de l’organisation locale vers Skype entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs vers Skype entreprise online.
ms.openlocfilehash: 6653ca8fe7082f0cabd2057c078f7d0d8d6f0389
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726754"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer des utilisateurs de l’organisation locale vers Skype entreprise Online

Une fois que vous avez déplacé un utilisateur de l’environnement local vers Skype entreprise Online, l’utilisateur interagit avec Skype entreprise Online pour ses fonctionnalités. Tous les contacts qui existaient sur site seront disponibles dans Skype entreprise Online, et les réunions existantes organisées par l’utilisateur pour le futur seront mises à jour vers de sorte que les liens pointent vers Skype entreprise online. Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.  Pour déplacer des utilisateurs d’un environnement local vers Skype entreprise Online, utilisez l’applet de commande Move-CsUser ou le panneau de configuration de Skype entreprise Server, qui sont tous deux des outils locaux. 

Avant de déplacer des utilisateurs, veillez à passer en revue les [éléments prérequis](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer les utilisateurs vers le Cloud.
 
## <a name="move-users-with-move-csuser"></a>Déplacer des utilisateurs à l’aide de Move-CsUser 

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype entreprise Management Shell locale. Vous devez disposer de privilèges suffisants dans l’environnement local et dans le client Office 365, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un compte unique qui dispose de privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype entreprise Server Management Shell locale avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier des informations d’identification pour un compte Office 365 avec le rôle d’administration Office 365 nécessaire.

Pour déplacer un utilisateur vers en ligne à l’aide de Move-CsUser :

- Spécifier l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez le paramètre-Target avec la valeur «sipfed. online. Lync. <span>com».
- Si vous ne disposez pas d’un compte avec des autorisations suffisantes dans local et Office 365, utilisez le paramètre-Credential pour fournir un compte avec des autorisations suffisantes dans Office 365.
- Si le compte avec des autorisations dans Office 365 ne se termine pas par «sur. Microsoft. <span>com», vous devez spécifier le paramètre-HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

 > [!NOTE]
 > Vous devez déterminer la valeur HostedMigrationOverrideUrl correcte pour votre client. vous pouvez facilement effectuer cette opération en accédant au centre d’administration Skype entreprise hérité. déterminer le préfixe-XXXXXXX.online.lync.com et ajouter/HostedMigration/hostedmigrationservice.svc. par exemple : https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc une fois que vous avez identifié la valeur, utilisez-la pour la variable $URL comme indiqué ci-dessous.

La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers Skype entreprise Online et suppose que les informations d’identification Office 365 sont un compte distinct et fourni comme entrée pour l’invite Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Si le compte administrateur est activé pour l’authentification multifacteur (MFA), ne spécifiez pas le paramètre-Credential. L’administrateur sera invité à entrer les informations d’identification.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Déplacer des utilisateurs avec le panneau de configuration de Skype entreprise Server 

1. Ouvrez l’application du panneau de configuration de Skype entreprise Server.
2. Dans le volet de navigation de gauche, choisissez **utilisateurs**.
3. Utilisez **Rechercher** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers Skype entreprise online.
4. Sélectionnez le ou les utilisateurs, puis, dans la liste déroulante **action** située au-dessus de la liste, sélectionnez **déplacer les utilisateurs sélectionnés vers Skype entreprise Online**.
5. Dans l'Assistant, cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et qui dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis une **nouvelle** fois pour déplacer l’utilisateur.
8. Notez que les messages d’État concernant la réussite ou l’échec sont fournis en haut de l’application principale du panneau de configuration, et non dans l’Assistant.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
