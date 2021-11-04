---
title: Configurer l’administrateur pour l’application Microsoft Parents pour l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams d’article pour l’ÉDUCATION - Conditions préalables et configurer PowerShell pour l’application Parents.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785147"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Déploiement de l’application parents dans Microsoft Teams

L’application parent permet aux enseignants de communiquer et de s’impliquer en toute sécurité avec les parents et tuteurs des étudiants dans leurs cours à l’aide d’une conversation Teams qui s’échellera au sein de l’organisation enseignant. Toutes les données des parents et tuteurs sont approvisionnementées à l’Synchronisation des données scolaires, ce qui permet aux enseignants et au personnel administratif de configurer les choses en douceur.

## <a name="requirements"></a>Conditions requises

### <a name="school-data-sync"></a>Synchronisation des données scolaires

- Vous devez Synchronisation des données scolaires (SDS) pour remplir les informations de contact associées à **chaque** étudiant.
  - [Déployer la SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Si vous avez besoin d’aide pour la configuration de SDS et l’activation des contacts parents dans votre client, contactez l’équipe Edu Customer Success en :
  - Finalisation du processus d’fafa à [FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - Ouverture d’un ticket au [support.](https://aka.ms/sdssupport)

### <a name="teams-admins-center---policies"></a>Teams Centre d’administration - Stratégies

- Le propriétaire de la classe doit activer la conversation
- Le propriétaire de la classe doit avoir un accès externe **avec Teams non gérés par une organisation.** 
  - Ce paramètre est accessible dans Utilisateurs > Accès externe pour le niveau client, ou si vous voulez activer pour un certain ensemble d’utilisateurs, consultez powerShell ci-dessous.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Activation d’une conversation fédérée par utilisateur

1. Installez la dernière version Microsoft Teams prévisualisation du module PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. À l’aide d’informations d’identification qui ont des privilèges d’administrateur, exécutez la commande suivante dans une fenêtre de commande :

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Le paramètre de stratégie qui Teams un accès externe grand public au niveau de l’utilisateur (EnableTeamsConsumerAccess) est activé par défaut pour toutes les stratégies d’accès externe au niveau utilisateur. Le paramètre au niveau du client (AllowTeamsConsumer) et le paramètre de stratégie au niveau utilisateur doivent être activés pour qu’un utilisateur Teams un accès externe grand public. Si vous ne souhaitez pas que tous les membres de votre client activent l’accès externe grand public, vous devez mettre à jour les stratégies d Teams’accès externe au niveau utilisateur à vos utilisateurs avant d’activer le paramètre au niveau du client.

Si vous avez besoin de vérifier quelles stratégies d’accès externe utilisateur existent et à qui elles sont affectées, vous pouvez utiliser les étapes suivantes :
    
3. Vérifiez quelles stratégies d’accès externe utilisateur existent.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Pour chaque stratégie autre que la stratégie « globale » , vérifiez quels utilisateurs ont affecté la stratégie. Remarque : tous les utilisateurs qui n’ont pas de stratégie spécifique sont de nouveau affectés à la stratégie « Global »

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Options PowerShell supplémentaires

Étant donné que toutes les stratégies d’accès externe au niveau utilisateur ont activé Par défaut EnableTeamsConsumerAccess, si vous voulez mettre à jour l’une de ces stratégies pour ajuster le paramètre EnableTeamsConsumerAccess, vous pouvez créer des stratégies d’accès externe avec des paramètres ajustés, ou réattribuer des utilisateurs à des stratégies nouvelles ou existantes via PowerShell :

- Créer une stratégie d’accès externe (cela crée une stratégie d’accès externe et définit les paramètres) : [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personnaliser une stratégie d’accès externe existante (modifie les paramètres d’une stratégie d’accès externe existante, notamment la stratégie globale) : [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Les abonnements par défaut suivants ne peuvent pas être modifiés : « FederationAndPICDefault », « FederationOnly », « NoFederationAndPIC ». Si vous devez modifier les paramètres de stratégie pour les utilisateurs à qui ces stratégies sont attribuées, affectez différentes stratégies avec les paramètres corrects à ces utilisateurs.

- Affecter une stratégie d’accès externe à un utilisateur unique : [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Attribuer une stratégie à un ensemble d’utilisateurs [: New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Une fois que vous êtes certain que vos stratégies d’accès externe au niveau utilisateur sont correctement définies pour tous vos utilisateurs, vous pouvez activer le paramètre au niveau du client qui contrôle l’accès externe du client Teams grand public à l’aide de l’cmdlet suivante :

- Définir les paramètres de configuration de la fédération pour votre client (paramètre AllowTeamsConsumer sur true) : [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Désactivation de l’application Parents

L’application Parents est activée par défaut, afin que tous les propriétaires de classe voient l’application dans leur équipe de classe. L’application peut être désactivée [](manage-apps.md#allow-and-block-apps) au niveau du client à l’aide de l’application Autoriser et bloquer des applications dans le Microsoft Teams d’administration. Si cette autorisation est désactivée au niveau du client, elle sera bloquée pour tous les utilisateurs, même si l’autorisation au niveau utilisateur est activée.

Cela peut également être désactivé au niveau de l’utilisateur à l’aide de [Gérer les stratégies d’autorisation d’application dans Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Affectation de votre stratégie à un utilisateur](/powershell/module/skype/grant-csexternalaccesspolicy)
