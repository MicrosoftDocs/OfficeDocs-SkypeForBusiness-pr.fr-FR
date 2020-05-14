---
title: Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online
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
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221114"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online

Une fois que vous avez déplacé un utilisateur de l’environnement local vers Skype entreprise Online, l’utilisateur interagit avec Skype entreprise Online pour ses fonctionnalités. Tous les contacts qui existaient sur site seront disponibles dans Skype entreprise Online, et les réunions existantes organisées par l’utilisateur pour le futur seront mises à jour vers de sorte que les liens pointent vers Skype entreprise online. Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.  Pour déplacer des utilisateurs d’un environnement local vers Skype entreprise Online, utilisez l’applet de commande Move-CsUser ou le panneau de configuration de Skype entreprise Server, qui sont tous deux des outils locaux. 

Avant de déplacer des utilisateurs, veillez à passer en revue les [éléments prérequis](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer les utilisateurs vers le Cloud.
 
## <a name="move-users-with-move-csuser"></a>Déplacer des utilisateurs à l’aide de Move-CsUser 

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype entreprise Management Shell locale. Vous devez disposer de privilèges suffisants dans l’environnement local et dans l’organisation Microsoft 365/Office 365, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un compte unique doté de privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype entreprise Server Management Shell locale avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier les informations d’identification d’un compte Microsoft 365 ou Office 365 avec le rôle d’administration nécessaire.

Pour déplacer un utilisateur vers en ligne à l’aide de Move-CsUser :

- Spécifier l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez le paramètre-Target avec la valeur «sipfed. online. Lync. <span> com».
- Si vous ne disposez pas d’un compte avec des autorisations suffisantes dans local et Office 365, utilisez le paramètre-Credential pour fournir un compte avec des autorisations suffisantes dans Office 365.
- Si le compte avec des autorisations dans Office 365 ne se termine pas par «. onmicrosoft. <span> com», vous devez spécifier le paramètre-HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers Skype entreprise online. Il part du principe que les informations d’identification Microsoft 365 ou Office 365 sont un compte distinct et sont fournies comme entrée pour l’invite Get-Credential.

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
6. Si vous y êtes invité, connectez-vous à Microsoft 365 ou Office 365 avec un compte qui se termine par. onmicrosoft.com et qui dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis une **nouvelle** fois pour déplacer l’utilisateur.
8. Notez que les messages d’État concernant la réussite ou l’échec sont fournis en haut de l’application principale du panneau de configuration, et non dans l’Assistant.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
