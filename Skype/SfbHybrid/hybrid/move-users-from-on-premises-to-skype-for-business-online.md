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
description: Découvrez comment déplacer des utilisateurs vers Skype Entreprise Online.
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237960"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online

Après avoir fait passer un utilisateur de l’local vers Skype Entreprise Online, l’utilisateur interagit avec Skype Entreprise Online pour sa fonctionnalité. Tous les contacts qui existaient en local seront disponibles dans Skype Entreprise Online, et toutes les réunions existantes organisées par l’utilisateur à l’avenir sont mises à jour de sorte que les liens pointent vers Skype Entreprise Online. Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.  Pour déplacer des utilisateurs d’un environnement local vers Skype Entreprise Online, utilisez la cmdlet Move-CsUser ou le Panneau de Skype Entreprise Server, qui sont tous deux des outils locaux. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Avant de déplacer des utilisateurs, veillez à passer en revue les conditions préalables pour déplacer les [utilisateurs](move-users-between-on-premises-and-cloud.md#prerequisites) vers le cloud.
 
## <a name="move-users-with-move-csuser"></a>Déplacer des utilisateurs avec Move-CsUser 

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Management Shell sur site. Vous devez avoir des privilèges suffisants à la fois dans l’environnement local et dans l’organisation Microsoft 365/Office 365 comme décrit dans Informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Vous pouvez utiliser un seul compte spécifiant des privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype Entreprise Server Management Shell sur site avec des informations d’identification sur site et utiliser le paramètre pour spécifier les informations d’identification d’un compte Microsoft 365 ou Office 365 avec le rôle d’administration `-Credential` nécessaire.

Pour déplacer un utilisateur en ligne à l’aide de Move-CsUser :

- Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez le paramètre -Target avec la valeur « sipfed.online.lync. <span> com ».
- Si vous n’avez pas un compte avec des autorisations suffisantes à la fois sur site et dans Office 365, utilisez le paramètre -credential pour fournir à un compte des autorisations suffisantes dans Office 365.
- Si le compte avec des autorisations dans Office 365 ne se termine pas par « .onmicrosoft. <span> com », puis vous devez spécifier le paramètre -HostedMigrationOverrideUrl, avec la valeur correcte comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La séquence de cmdlet suivante peut être utilisée pour déplacer un utilisateur vers Skype Entreprise Online. Il part du principe que Microsoft 365 ou Office 365'identification est un compte distinct et fourni en tant qu’entrée pour l’invite Get-Credential'utilisateur.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Si le compte d’administrateur est activé pour l’authentification multifacteur, ne spécifiez pas le paramètre -Credential. L’administrateur est invité à obtenir des informations d’identification.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Déplacer des utilisateurs avec Skype Entreprise Server panneau de commande 

1. Ouvrez l Skype Entreprise Server du Panneau de Skype Entreprise Server.
2. Dans le navigation de gauche, sélectionnez **Utilisateurs.**
3. Utilisez **Find** pour localiser les utilisateurs que vous souhaitez déplacer vers Skype Entreprise Online.
4. Sélectionnez le(s) utilisateur(s), puis, dans la liste dropdown **Action** au-dessus de la liste, sélectionnez Déplacer les utilisateurs sélectionnés **vers Skype Entreprise Online**.
5. Dans l'Assistant, cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous Microsoft 365 ou Office 365 un compte qui se termine par .onmicrosoft.com et dispose d’autorisations suffisantes.
7. Cliquez **sur** Suivant, puis **sur Suivant** une fois de plus pour déplacer l’utilisateur.
8. Notez que les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale du Panneau de contrôle, et non dans l’Assistant.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](/powershell/module/skype/move-csuser)