---
title: Configuration de l’administrateur pour l’application Parents de Microsoft EDU dans Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams pour l’éducation article documentant les conditions préalables et la configuration de l’application Parents.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9243dfedb11c9102673e821bd2fac9d06cf3c834
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887292"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Déploiement de l’application Parents dans Microsoft Teams

L’application Parents permet aux enseignants de communiquer et de s’impliquer en toute sécurité avec les parents et tuteurs des étudiants dans leurs équipes de classe à l’aide d’une conversation Teams qui s’échellera au sein de l’organisation de l’enseignant. Toutes les données des parents et tuteurs sont approvisionnementées à l’Synchronisation des données scolaires, ce qui permet au personnel de l’it de configurer les choses en douceur.

## <a name="requirements"></a>Conditions requises

### <a name="school-data-sync"></a>Synchronisation des données scolaires

- Vous devez Synchronisation des données scolaires SDS pour remplir les informations de contact associées au parent et tuteur de **chaque** étudiant.
  - [Déployer la SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Si vous avez besoin d’aide pour définir SDS et remplir les **contacts** parents et tuteurs liés aux étudiants de votre client, contactez l’équipe Edu Customer Success en :
  - Finalisation du processus d’fafa à [FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - Ouverture d’un ticket au [support.](https://aka.ms/sdssupport)

### <a name="teams-admin-center---policies"></a>Teams Centre d’administration - Stratégies

- Les propriétaires d’équipe de classe Teams conversation instantanée activée.
- Les propriétaires d’équipe de classe doivent avoir un accès externe **avec Teams comptes non gérés par une organisation.** 
  - Celle-ci doit être activée au niveau du client et de l’utilisateur. Le paramètre au niveau du client est accessible dans la page **Utilisateurs > accès** externe dans le Teams d’administration. Ce paramètre est également accessible via PowerShell. Les stratégies d’accès externe au niveau utilisateur sont accessibles uniquement via PowerShell. Pour plus d’informations, voir les commandes PowerShell ci-dessous.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Activation de l’accès externe Teams comptes non gérés par une organisation

1. Installez la dernière version Microsoft Teams prévisualisation du module PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. À l’aide d’informations d’identification qui ont des privilèges d’administrateur, exécutez les commandes suivantes :

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Le paramètre de stratégie qui active l’accès externe avec des comptes Teams non gérés par une organisation au niveau de l’utilisateur () est activé par défaut pour toutes les stratégies d’accès externe au niveau `EnableTeamsConsumerAccess` utilisateur. Le paramètre au niveau du client et le paramètre de stratégie au niveau utilisateur doivent être activés pour qu’un utilisateur accède à des comptes Teams non gérés par une organisation. Si vous ne souhaitez pas que tous les utilisateurs de votre client activent cet accès, vous devez vous assurer que votre paramètre au niveau du client est désactivé, mettre à jour les stratégies d’accès externe au niveau utilisateur attribuées à vos utilisateurs, puis activer le paramètre au niveau du client.

Pour vérifier les stratégies d’accès externe au niveau utilisateur et à qui elles sont affectées, vous pouvez utiliser la procédure suivante :
    
3. Vérifiez quelles stratégies d’accès externe utilisateur existent.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Pour chaque stratégie autre que la stratégie « globale » , vérifiez quels utilisateurs ont affecté la stratégie. Remarque : tous les utilisateurs qui n’ont pas de stratégie spécifique sont de nouveau affectés à la stratégie « Globale ». La stratégie « Global » est affectée à tous les nouveaux utilisateurs ajoutés au client.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Toutes les stratégies d’accès externe au niveau utilisateur ayant la valeur True par défaut, si vous voulez ajuster le paramètre pour des utilisateurs spécifiques, vous pouvez créer/modifier des stratégies d’accès externe existantes avec des paramètres ajustés et/ou réattribuer des utilisateurs à des stratégies nouvelles ou existantes à l’aide des `EnableTeamsConsumerAccess` `EnableTeamsConsumerAccess` cmdlets PowerShell suivantes :

- Créer une stratégie d’accès externe : [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personnaliser une stratégie d’accès externe existante (notamment la stratégie « Global » ) : [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Les stratégies d’abonnement par défaut suivantes ne peuvent pas être modifiées : 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. La stratégie « FederationAndPICDefault » était assignée par défaut à tous les utilisateurs, mais les nouveaux utilisateurs se voit désormais attribuer la stratégie « Global » par défaut. Si vous devez modifier les paramètres de stratégie pour les utilisateurs à qui ces stratégies d’abonnement par défaut sont attribuées, affectez différentes stratégies avec les paramètres corrects à ces utilisateurs.

- Affecter une stratégie d’accès externe à un utilisateur unique : [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Attribuer une stratégie à un ensemble d’utilisateurs [: New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Une fois que les stratégies d’accès externe au niveau utilisateur sont correctement définies pour les utilisateurs de votre client, vous pouvez activer le paramètre au niveau du client () à l’aide de `AllowTeamsConsumer` l’cmdlet suivante :

- Définir les paramètres de configuration de la fédération pour votre client [: Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="disabling-the-parents-app"></a>Désactivation de l’application Parents

L’application Parents est activée par défaut, afin que tous les propriétaires d’équipe de classe voient l’application dans leurs équipes de classe. 

L’application peut être désactivée [](manage-apps.md#allow-and-block-apps) au niveau du client à l’aide de l’application Autoriser et bloquer des applications dans le Microsoft Teams d’administration. Si l’application est désactivée au niveau du client, elle est bloquée pour tous les utilisateurs, même si les autorisations au niveau utilisateur sont activées.

L’application peut également être désactivée au niveau de l’utilisateur à l’aide des stratégies [d’autorisation d’application Microsoft Teams.](teams-app-permission-policies.md)

## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
