---
title: Configuration administrateur de Parents dans Teams pour l'éducation
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams article qui décrit les conditions préalables et la configuration de Parents dans Teams pour l'éducation.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d1b84fc78558fcbb1945cbc56b311b5e06234a5
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062528"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurer la connexion parent dans Microsoft Teams pour l'éducation

La connexion parent dans Teams pour l'éducation permet aux enseignants de communiquer et de s’impliquer en toute sécurité avec les parents et tuteurs des étudiants dans leurs équipes de classe à l’aide d’une conversation Teams qui s’échellera au sein de l’organisation de l’enseignant. Toutes les données des parents et tuteurs sont approvisionnementées à l’Synchronisation des données scolaires, ce qui permet au personnel du service it de configurer les choses en douceur.

Une fois que les enseignants et tuteurs légaux sont configurer, ils peuvent discuter entre eux à l’aide Teams conversation instantanée. 

Pour obtenir des instructions sur la connexion des parents et tuteurs avec les enseignants, voir [Connecter avec les enseignants du Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

Pour obtenir des instructions sur la manière dont les enseignants sont en train de communiquer avec les parents et tuteurs, voir Communiquer avec les [tuteurs dans Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

Les parents travaillent également avec la conversation encadrée. Les parents et tuteurs ne peuvent pas avoir les autorisations de Teams complètes, ce qui signifie qu’ils ne peuvent pas démarrer de conversations avec des étudiants ou supprimer des utilisateurs à autorisations complètes (comme les enseignants) des conversations. Pour plus d’informations sur la conversation supervise, voir [Utiliser les conversations surveillées dans Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>Conditions requises

### <a name="school-data-sync"></a>Synchronisation des données scolaires

- Vous devez Synchronisation des données scolaires SDS pour remplir les informations de contact associées au parent et tuteur **de chaque étudiant**.
  - [Déployer la SDS](/schooldatasync/parents-and-guardians-in-sds)

- Si vous avez besoin d’aide pour définir SDS et remplir les **contacts** parents et tuteurs liés aux étudiants de votre client, contactez l’équipe Edu Customer Success en :
  - Finalisation du processus d’fafa à [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Ouverture d’un ticket au [support](https://aka.ms/sdssupport).

- Actuellement, SDS prend uniquement en charge l’ingestion de données basée sur CSV pour les contacts parents ; Toutefois, vous pouvez utiliser la synchronisation [d’API PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou la synchronisation [d’API OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) pour toutes les données de liste, et ajouter simplement les contacts parents à l’aide du fichier CSV.
  - Créez un deuxième profil de synchronisation en utilisant le format de synchronisation [CSV SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Tirez les deux fichiers [parents avec](/schooldatasync/parent-contact-sync-file-format) le reste des fichiers v1 vides (uniquement les en-têtes).
    - User.csv
    - Guardianrelationship.csv
  - Pour afficher un exemple de jeu de fichiers CSV v1, consultez les [attributs minimum requis GitHub fichiers](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Si vous voulez automatiser l’tirant les fichiers CSV après la synchronisation initiale, lisez notre document Automation de synchronisation de fichiers [CSV](/schooldatasync/csv-file-sync-automation).
  - Pour obtenir de l’aide sur la configuration de la synchronisation de vos données [](https://www.microsoft.com/fasttrack?rtc=1) SDS, recherchez notre équipe de réussite client ou ouvrez [un ticket de support](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams d’administration - Stratégies

- Les propriétaires d’équipe de classe Teams conversation instantanée.
- Les propriétaires d’équipe de classe doivent avoir un accès externe **avec Teams comptes non gérés par une organisation**.
  - Cette fonction doit être désactivée au niveau du client et de l’utilisateur. Le paramètre au niveau du client est accessible dans la page **Utilisateurs > accès** externe dans le Teams d’administration. Ce paramètre est également accessible via PowerShell. Les stratégies d’accès externe au niveau utilisateur sont accessibles uniquement via PowerShell. Pour plus d’informations, voir les commandes PowerShell ci-dessous.

> [!NOTE]
>Les parents et tuteurs légaux sont considérés comme utilisateurs externes dans la fonctionnalité Parents, ce qui signifie qu’ils ne disposent pas de droits de locataire complets. Ils ont uniquement accès aux conversations à qui ils sont ajoutés, ainsi qu’aux fichiers, images et autres contenus partagés dans la conversation.
>
>Par ailleurs, les utilisateurs externes peuvent voir la présence (hors connexion, disponible, occupé, etc.) des utilisateurs de votre organisation, mais cette fonctionnalité peut être désactivée à l’aide de PowerShell pour protéger la confidentialité des utilisateurs. Dans PowerShell, utilisez [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) et set ``EnablePrivacyMode=true``.
>
>Même si les parents et tuteurs sont des utilisateurs externes, leurs contributions aux conversations sont découvrons. Découvrez comment effectuer une enquête Teams de découverte électronique en lisant Mener une enquête de découverte électronique sur du contenu [dans Microsoft Teams](ediscovery-investigation.md).

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Autoriser l’accès externe avec Teams non gérés par une organisation

Pour permettre aux enseignants de communiquer avec des parents et tuteurs dans Teams, l’administrateur informatique du client éducation doit mettre à jour les stratégies du client pour autoriser l’accès externe pour les comptes Teams en dehors du client. Pour plus d’informations sur la gestion de l’accès externe, voir [Gérer l’accès externe dans Microsoft Teams](manage-external-access.md).

Voici les étapes à suivre pour activer l’accès externe pour les parents et tuteurs légaux.

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

    Le paramètre de stratégie qui met en place l’accès externe avec des comptes Teams non gérés par une organisation au niveau de l’utilisateur (`EnableTeamsConsumerAccess`) est désactivé par défaut pour toutes les stratégies d’accès externe au niveau utilisateur. Le paramètre au niveau du client et le paramètre de stratégie au niveau utilisateur doivent être désactivés pour qu’un utilisateur accède à l’extérieur avec des comptes Teams non gérés par une organisation. Si vous ne souhaitez pas que tous les utilisateurs de votre client doivent activer cet accès, vous devez vous assurer que votre paramètre au niveau du client est désactivé, mettre à jour les stratégies d’accès externe au niveau utilisateur attribuées à vos utilisateurs, puis activer le paramètre au niveau du client.

    Pour vérifier les stratégies d’accès externe au niveau utilisateur et les personnes à lesquelles elles sont affectées, vous pouvez utiliser les étapes suivantes :

3. Vérifiez l’existence de stratégies d’accès externe au niveau utilisateur.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Pour chaque stratégie autre que la stratégie « globale » , vérifiez quels utilisateurs ont affecté la stratégie.

   > [!NOTE]
   > Les utilisateurs qui n’ont pas de stratégie spécifique sont de nouveau affectés à la stratégie « Globale ». La stratégie « Global » est affectée à tous les nouveaux utilisateurs ajoutés au client.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Toutes les stratégies d’accès externe au niveau utilisateur ayant la valeur True par défaut, `EnableTeamsConsumerAccess` si vous voulez ajuster le paramètre pour des utilisateurs spécifiques, vous pouvez créer/modifier des stratégies d’accès externe existantes avec des paramètres ajustés et/ou réattribuer des utilisateurs à des stratégies nouvelles ou existantes à l’aide des cmdlets PowerShell suivantes :

- Créer une stratégie d’accès externe : [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personnaliser une stratégie d’accès externe existante (notamment la stratégie « Global » ) : [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Les stratégies d’abonnement par défaut suivantes ne peuvent pas être modifiées : 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. La stratégie « FederationAndPICDefault » était assignée par défaut à tous les utilisateurs, mais les nouveaux utilisateurs se voit désormais attribuer la stratégie « Global » par défaut. Si vous devez modifier les paramètres de stratégie pour les utilisateurs à qui ces stratégies d’abonnement par défaut sont attribuées, affectez différentes stratégies avec les paramètres corrects à ces utilisateurs.

- Affecter une stratégie d’accès externe à un utilisateur unique : [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Attribuer une stratégie à un ensemble [d’utilisateurs : New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Une fois que les stratégies d’accès externe au niveau utilisateur sont correctement définies pour les utilisateurs de votre client, vous pouvez activer le paramètre au niveau du client (`AllowTeamsConsumer`) à l’aide de l’cmdlet suivante :

- Définir les paramètres de configuration de la fédération pour votre client [: Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Activer l’application Parents dans le Centre d’Teams’administration de famille

L’application Parents est désactivée par défaut, de sorte que les propriétaires d’équipe de classe ne la voient pas dans leurs équipes de classe tant qu’elle n’est pas autorisée via le Teams d’administration. L’application Parents est désactivée dans le Centre Teams’administration à l’aide [des applications autoriser bloquées par les éditeurs](manage-apps.md#apps-blocked-by-publishers).

À tout moment, l’application peut être désactivée au niveau du client [](manage-apps.md#allow-and-block-apps) à l’aide de l’application Autoriser et bloquer des applications dans le Teams d’administration. Si elle est désactivée au niveau du client, elle est bloquée pour tous les utilisateurs, même si les autorisations au niveau utilisateur sont désactivées.

L’application Parents peut également être désactivée au niveau de l’utilisateur à l’aide [des stratégies d’autorisation d’application Gérer dans Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
