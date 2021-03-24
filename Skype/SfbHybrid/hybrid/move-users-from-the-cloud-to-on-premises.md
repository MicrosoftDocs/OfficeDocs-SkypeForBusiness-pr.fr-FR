---
title: Déplacer des utilisateurs du cloud vers l’local
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
description: Découvrez comment déplacer des utilisateurs de Skype Entreprise Online vers l’entreprise sur site.
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110610"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Déplacer des utilisateurs du cloud vers l’local 

Si nécessaire, vous pouvez déplacer un utilisateur qui a été précédemment migré de l’local vers le cloud (que vous utilisiez Skype Entreprise Online ou Teams uniquement) vers l’local. Pour déplacer les utilisateurs du mode Skype Entreprise Online ou TeamsOnly vers un déploiement local de Skype Entreprise Server, utilisez la cmdlet Move-CsUser ou le Panneau de contrôle Skype Entreprise Server, qui sont tous deux des outils locaux. Lorsque vous déplacez un utilisateur vers un déploiement local, vous devez décider du pool vers lequel déplacer l’utilisateur.

> [!Important]
> Si l’utilisateur était auparavant en mode TeamsOnly et que vous utilisez une version antérieure à Skype Entreprise Server 2015 avec cu8, vous devez également supprimer l’affectation du mode TeamsOnly de TeamsUpgradePolicy pour cet utilisateur. Les utilisateurs locaux ne doivent pas avoir le mode = TeamsOnly.  Les versions ultérieures de Skype Entreprise Server suppriment automatiquement cette affectation. Pour plus d’informations, [voir Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Conditions préalables

- Azure AD Connect doit être correctement configuré pour l’organisation et synchroniser tous les attributs pertinents pour l’utilisateur, comme décrit dans [configurer Azure AD Connect](configure-azure-ad-connect.md).
- L’utilisateur en cours de revenir en ligne vers l’local doit déjà exister dans l’annuaire Active Directory local.
- Skype Entreprise hybride doit être configuré, comme décrit dans [Configurer Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Déplacement des utilisateurs vers l’local

Une fois que vous avez retenté un utilisateur du cloud vers l’ordinateur local :

- L’utilisateur interagit avec votre déploiement Skype Entreprise Server pour sa fonctionnalité. 
- Tous les contacts qui existaient dans Skype Entreprise Online ou Teams sont migrés vers Skype Entreprise Server. Les deux ensembles de contacts sont fusionnés, puis migrés vers l’local.  En outre, les contacts qui existent déjà dans Teams restent dans Teams.
- Si l’utilisateur utilise également Teams, il n’aura pas la possibilité d’interopérer avec les utilisateurs de Skype Entreprise, ni de communiquer avec les utilisateurs des organisations fédérées.
- Les réunions dans Skype Entreprise Online *ne* sont pas automatiquement migrées vers l’local. Les utilisateurs doivent reprogrammer leurs réunions ou, si vous le souhaitez, utiliser l’outil [de migration de réunion.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)

### <a name="move-users-with-move-csuser"></a>Déplacer des utilisateurs avec Move-CsUser

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Management Shell sur site. Vous devez avoir des privilèges suffisants dans l’environnement local, ainsi que dans l’organisation de service cloud (Microsoft 365 ou Office 365), comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Vous pouvez utiliser un seul compte spécifiant des privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype Entreprise Server Management Shell sur site avec des informations d’identification sur site et utiliser le paramètre pour spécifier les informations d’identification d’un compte `-Credential` Microsoft 365 ou Office 365 avec le rôle d’administration nécessaire.

Pour déplacer un utilisateur vers l’ordinateur local à l’aide de Move-CsUser :

- Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez le paramètre -Target avec le nom de domaine complet du pool local souhaité qui hébergera l’utilisateur.
- Si vous n’avez pas un compte avec des autorisations suffisantes à la fois sur site et dans le service cloud (Microsoft 365 ou Office 365), utilisez le paramètre -credential pour fournir un compte avec des autorisations suffisantes dans Microsoft 365 ou Office 365.
- Si le compte spécifiant des autorisations dans Microsoft 365 ou Office 365 ne se termine pas par « on.microsoft.com », vous devez spécifier le paramètre -HostedMigrationOverrideUrl, avec la valeur correcte comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La séquence de cmdlet suivante peut être utilisée pour déplacer un utilisateur vers Skype Entreprise Server et suppose que les informations d’identification Microsoft 365 ou Office 365 sont un compte distinct et fournies en tant qu’entrées pour l’invite Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Déplacer des utilisateurs avec le Panneau de contrôle Skype Entreprise Server

1. Ouvrez l’application Panneau de contrôle Skype Entreprise Server.
2. Dans le navigation de gauche, sélectionnez **Utilisateurs.**
3. Utilisez **Find** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers l’ordinateur local.
4. Sélectionnez le(s) utilisateur(s), puis, dans la liste dropdown **Action** au-dessus de la liste, sélectionnez Déplacer les **utilisateurs sélectionnés vers l’local.**
5. Dans l’Assistant, sélectionnez le pool d’utilisateurs qui hébergera l’utilisateur, puis cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous à Microsoft 365 ou Office 365 avec un compte qui se termine par .onmicrosoft.com et dispose d’autorisations suffisantes.
7. Cliquez **sur** Suivant, puis **sur Suivant** une fois de plus pour déplacer l’utilisateur.
8. Notez que les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale du Panneau de contrôle, et non dans l’Assistant.

### <a name="removing-teamsonly-mode"></a>Suppression du mode TeamsOnly

Si vous utilisez une version antérieure à Skype Entreprise 2015 avec cu8 et que l’utilisateur est déplacé vers l’ordinateur local en mode TeamsOnly, vous devez supprimer l’instance UpgradeToTeams avant de déplacer l’utilisateur en `TeamsUpgradePolicy` local. Vous pouvez accorder explicitement une stratégie avec un autre mode ou simplement supprimer l’attribution de stratégie existante pour que cet utilisateur utilise la stratégie globale (tant que la stratégie globale de votre client n’est pas UpgradeToTeams).

Pour supprimer l’affectation de TeamsUpgradePolicy à l’utilisateur, exécutez l’cmdlet suivante à partir d’une fenêtre PowerShell Skype Entreprise Online :

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Sinon, pour affecter une autre instance de TeamsUpgradePolicy qui n’a pas de mode=TeamsOnly, vous pouvez spécifier le nom de l’instance souhaitée comme valeur du paramètre PolicyName dans l’cmdlet. Pour voir la liste des instances disponibles de TeamsUpgradePolicy, exécutez Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Voir aussi

[Move-CsUser](/powershell/module/skype/move-csuser)