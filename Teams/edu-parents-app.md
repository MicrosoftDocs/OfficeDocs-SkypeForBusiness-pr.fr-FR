---
title: Administration configuration des parents dans Teams pour l'éducation
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Article Microsoft Teams documentant les prérequis et la configuration des parents dans Teams pour l'éducation.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkTEAMS
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2d0d916028a026d7706fd317ba25d16af213a81
ms.sourcegitcommit: 55d2f515f5040b4c083f529d7b818c84d42378a0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2022
ms.locfileid: "69147481"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurer la connexion parente dans Microsoft Teams pour l'éducation

La connexion parente dans Teams pour l'éducation permet aux enseignants de se connecter et de s’engager en toute sécurité avec les parents et les tuteurs des étudiants dans leurs équipes de classe à l’aide de Teams.

Cet article fournit des conseils aux professionnels de l’informatique de l’éducation sur les exigences et la configuration de la connexion parente.

## <a name="share-guardian-and-educator-resources"></a>Partager des ressources de tuteur et d’enseignant

Voici quelques ressources que les administrateurs informatiques peuvent partager avec les tuteurs et les enseignants sur la façon dont ils peuvent commencer à utiliser la connexion parente.

- Pour obtenir des conseils sur la configuration des gardiens, consultez [Se connecter avec des enseignants dans Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Pour obtenir des conseils sur la configuration des enseignants, consultez [Communiquer avec les tuteurs dans Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Avantages de la connexion parente

La connexion parents permet aux enseignants et aux tuteurs de discuter, d’envoyer un e-mail et d’appeler à l’aide de Teams.

- Les enseignants peuvent lancer des conversations avec les gardiens.
  - Si le tuteur n’a pas de compte de consommateur Teams ou n’a pas encore rejoint Teams, il reçoit le message de l’enseignant ainsi qu’un e-mail d’invitation pour accéder à Teams. Cela s’applique uniquement dans les cas où les limites d’invitation n’ont pas été atteintes et que la conversation est une nouvelle conversation ou une conversation existante qui a été réinscrite à partir de la connexion parente.
- Il fonctionne avec la conversation supervisée. Pour plus d’informations, consultez [Utiliser des conversations supervisées dans Microsoft Teams](supervise-chats-edu.md).
  - Par défaut, les gardiens disposent d’autorisations restreintes, de sorte qu’ils ne peuvent pas discuter avec des étudiants ou supprimer des utilisateurs des conversations.
  - Ce paramètre peut être modifié par l’administrateur du locataire.
- Les enseignants peuvent sélectionner l’e-mail d’un tuteur pour leur envoyer un e-mail à l’aide de leur client de messagerie natif.
- Les enseignants peuvent sélectionner le numéro de téléphone d’un tuteur pour les appeler dans Teams.

> [!IMPORTANT]
> Pour cliquer pour appeler la fonctionnalité dans Teams, votre locataire a besoin des éléments suivants :
>
> - Fonctionnalités PBX (Public Branch Exchange).
> - Connexion au réseau RTC.
>
> les plans Microsoft 365 A1 et A3 n’incluent pas de fonctionnalités PBX ni de connexion RTC. Vous pouvez acheter des [licences d’extension pour chacun de ces éléments](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
>
> Microsoft 365 A5 plans incluent uniquement des fonctionnalités PBX à l’aide du système téléphonique Teams. Vous devrez toujours [acheter un forfait d’appels Teams ou utiliser une solution tierce](pstn-connectivity.md) pour vous connecter à des numéros externes sur le RTC.
>
> Pour plus d’informations sur toutes vos options pour obtenir la connectivité RTC, consultez [Options de connectivité RTC](pstn-connectivity.md).
>
> Pour plus d’informations sur les licences d’appel Teams, consultez [Options de licence](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) des modules complémentaires Teams.

## <a name="requirements"></a>Conditions requises

Vous devez utiliser Microsoft Graph ou School Data Sync (SDS) pour renseigner les informations de contact relatives au parent et au tuteur de chaque étudiant.

### <a name="graph-api"></a>API Graph

Si vous utilisez déjà le [Kit de développement logiciel (SDK) Microsoft Graph PowerShell](/powershell/microsoftgraph/overview) pour créer des identités d’étudiant, vous pouvez facilement inclure le [type de ressource RelatedContact](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>School Data Sync

Les données de contact du tuteur Teams restent à jour avec SIS à l’aide de School Data Sync (SDS), lorsque SDS est configuré pour se synchroniser régulièrement.

Si le tuteur est supprimé des enregistrements *d’un étudiant* , toutes les conversations existantes les impliquant contiennent une bannière visible par le propriétaire de la conversation. Cette bannière informera le propriétaire de la conversation de la modification, en lui demandant de supprimer le tuteur de la conversation. Microsoft ne met pas automatiquement à jour l’appartenance à la conversation pour supprimer le tuteur.

- Vous avez besoin de School Data Sync (SDS) pour renseigner les informations de **contact relatives au** parent et au tuteur de chaque étudiant.
  - [Déployer la SDS](/schooldatasync/parents-and-guardians-in-sds)

- Si vous avez besoin d’aide pour configurer SDS et remplir les **contacts parent** et tuteur pour les étudiants de votre locataire, contactez l’équipe edu Customer Success en :
  - Fin du processus RFA dans [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Ouverture d’un ticket au [support](https://aka.ms/sdssupport).

- Actuellement, SDS prend uniquement en charge l’ingestion de données csv pour les contacts parents ; Toutefois, vous pouvez utiliser [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) pour toutes les données de liste, et simplement ajouter des contacts parents à l’aide de CSV.
  - Créez un deuxième profil de synchronisation au [format CSV SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds) ou [au format CSV SDS v2.1](/schooldatasync/sds-v2.1-csv-file-format-classic).
  - Extrayez les deux [fichiers parent](/schooldatasync/parent-contact-sync-file-format) remplis avec le reste des fichiers v1/v2.1 vides (uniquement les en-têtes).
    - User.csv
    - Guardianrelationship.csv
      - La valeur *Role* doit être renseignée pour chaque parent et tuteur afin d’indiquer s’il s’agit d’un `parent` ou `guardian`.
        - Seules les valeurs de `parent` ou `guardian` sont prises en charge dans l’application. D’autres valeurs entraînent des erreurs.
        - Pour le format SDS v1, il sera **étiqueté rôle,** mais pour le format SDS v2.1, il sera étiqueté comme **relationshipRole**.
  - Pour afficher un exemple d’ensemble de fichiers CSV, consultez les [fichiers GitHub Attributs minimum requis](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Si vous souhaitez automatiser l’extraction des fichiers CSV après la synchronisation initiale, lisez notre [document CSV File Sync Automation](/schooldatasync/csv-file-sync-automation).
  - Pour obtenir de l’aide sur la configuration de votre synchronisation de données SDS, contactez [notre équipe de réussite client](https://www.microsoft.com/fasttrack?rtc=1) ou [ouvrez un ticket de support](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Stratégies du centre d’administration Teams

- La conversation Teams doit être activée pour les propriétaires d’équipe de classe.
- Les propriétaires d’équipe de classe doivent disposer d’un accès externe avec des **comptes Teams non gérés par une organisation** activés.
  - Cette option doit être activée au niveau du locataire et au niveau de l’utilisateur. Le paramètre au niveau du locataire se trouve dans **Utilisateurs > Accès externe** dans le Centre d’administration Teams. Ce paramètre est également accessible via PowerShell. Les stratégies d’accès externe au niveau de l’utilisateur sont accessibles uniquement via PowerShell. Pour plus d’informations, consultez les [commandes PowerShell ci-dessous](#allow-external-access-with-teams-accounts-not-managed-by-an-organization).
- Pour autoriser la création de réunion à partir de l’application Parent Connection, les stratégies suivantes doivent être activées :
  - [Autoriser la planification de réunions privées](meeting-policies-in-teams.md#allow-scheduling-private-meetings).
  - [Autoriser les utilisateurs anonymes à rejoindre la réunion](meeting-policies-participants-and-guests.md#let-anonymous-people-join-a-meeting).

#### <a name="parent-and-guardian-restrictions"></a>Restrictions relatives aux parents et tuteurs

Les parents et tuteurs sont classés comme *des utilisateurs externes* dans la connexion parents, ce qui signifie qu’ils ne disposent pas de droits de locataire complets. Ils ont uniquement accès à la conversation ou aux conversations dont ils font partie, ainsi qu’aux fichiers, images et autres contenus partagés dans la conversation.

Pour les conversations externes, les utilisateurs internes et externes peuvent ajouter des utilisateurs à la conversation. Pour en savoir plus sur l’expérience de conversation externe, consultez [Gérer les réunions et les conversations externes dans Microsoft Teams](manage-external-access.md).

En outre, les utilisateurs externes peuvent voir la présence (hors connexion, disponible, occupé, etc.) des utilisateurs de votre organisation, mais cela peut être désactivé à l’aide de PowerShell pour protéger la confidentialité des utilisateurs. Dans PowerShell, utilisez [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) et définissez ``EnablePrivacyMode=true``.

Même si les parents et les tuteurs sont des utilisateurs externes, leurs contributions aux conversations sont détectables. Découvrez comment mener une enquête eDiscovery Teams en lisant [Mener une investigation eDiscovery du contenu dans Microsoft Teams](ediscovery-investigation.md).

> [!IMPORTANT]
> Les administrateurs informatiques doivent informer tous les propriétaires de classe des meilleures pratiques pour le partage d’informations sur les étudiants par conversation, y compris les risques pour la confidentialité des étudiants.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Blocage d’un parent ou d’un tuteur dans une conversation

Les enseignants peuvent bloquer un tuteur dans la conversation lancée dans la connexion parente.

Le propriétaire de classe peut :

1. Ouvrez la carte de profil du tuteur, sélectionnez l’ellipse et **Bloquer l’utilisateur**.
2. Ensuite, supprimez le tuteur de la conversation.

L’utilisateur bloqué ne pourra pas démarrer d’autres conversations avec le propriétaire de la classe.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Autoriser l’accès externe avec des comptes Teams non gérés par une organisation

Pour permettre aux enseignants de communiquer avec les parents et les tuteurs dans Teams, l’administrateur informatique du locataire éducation doit mettre à jour les stratégies du locataire afin d’autoriser l’accès externe pour les comptes Teams en dehors du locataire. Pour plus d’informations sur la gestion de l’accès externe, consultez [Gérer l’accès externe dans Microsoft Teams](manage-external-access.md).

Voici les étapes à suivre pour activer l’accès externe pour les parents et les tuteurs.

1. Installez le dernier module Microsoft Teams PowerShell ici [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. À l’aide d’informations d’identification disposant de privilèges d’administrateur, exécutez les commandes suivantes :

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    Le paramètre de stratégie qui active l’accès externe avec les comptes Teams non gérés par une organisation au niveau de l’utilisateur (`EnableTeamsConsumerAccess`) est activé par défaut pour toutes les stratégies d’accès externe au niveau de l’utilisateur. Le paramètre au niveau du locataire et le paramètre de stratégie au niveau de l’utilisateur doivent être activés pour qu’un utilisateur dispose d’un accès externe avec des comptes Teams non gérés par une organisation. Si vous ne souhaitez pas que chaque utilisateur de votre locataire ait cet accès activé, vous devez vous assurer que votre paramètre au niveau du locataire est désactivé, mettre à jour les stratégies d’accès externe de niveau utilisateur attribuées à vos utilisateurs, puis activer le paramètre au niveau du locataire.

    Pour vérifier quelles stratégies d’accès externe de niveau utilisateur existent et à qui elles sont affectées, vous pouvez effectuer les étapes suivantes :

3. Vérifiez qu’il existe des stratégies d’accès externe au niveau de l’utilisateur.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Pour chaque stratégie autre que la stratégie « globale », vérifiez les utilisateurs auxquels la stratégie est affectée.

    > [!NOTE]
    > Tous les utilisateurs qui n’ont pas de stratégie spécifique affectée reviennent à la stratégie « Globale ». La stratégie « Globale » est affectée à tous les nouveaux utilisateurs ajoutés au locataire.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Étant donné que toutes les stratégies d’accès externe au niveau de l’utilisateur ont `EnableTeamsConsumerAccess` la valeur true par défaut, si vous souhaitez ajuster le `EnableTeamsConsumerAccess` paramètre pour des utilisateurs spécifiques, vous pouvez créer/modifier des stratégies d’accès externe existantes avec des paramètres ajustés et/ou réaffecter des utilisateurs à des stratégies nouvelles ou existantes à l’aide des applets de commande PowerShell suivantes :

- Créer une stratégie d’accès externe : [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personnaliser une stratégie d’accès externe existante (y compris la stratégie « Globale ») : [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Les stratégies d’abonnement par défaut suivantes ne peuvent pas être modifiées : « FederationAndPICDefault », « FederationOnly », « NoFederationAndPIC ». La stratégie « FederationAndPICDefault » était affectée par défaut à tous les utilisateurs, mais les nouveaux utilisateurs se voient désormais attribuer la stratégie « Globale » par défaut. Si vous devez modifier les paramètres de stratégie pour les utilisateurs auxquels ces stratégies d’abonnement par défaut sont affectées, affectez des stratégies différentes avec les paramètres appropriés à ces utilisateurs.

- Attribuer une stratégie d’accès externe à un seul utilisateur : [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Affecter une stratégie à un ensemble d’utilisateurs : [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Une fois que les stratégies d’accès externe au niveau de l’utilisateur sont correctement définies pour les utilisateurs de votre locataire, vous pouvez activer le paramètre au niveau du locataire (`AllowTeamsConsumer`) pour le locataire à l’aide de l’applet de commande suivante :

- Définir les paramètres de configuration de fédération pour votre locataire : [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Activer l’application Parents dans le Centre d’administration Teams

L’application Parents étant désactivée par défaut, les propriétaires d’équipe de classe ne la voient pas dans leurs équipes de classe tant qu’elle n’est pas autorisée par le biais du Centre d’administration Teams. L’application Parents est activée dans le Centre d’administration Teams à l’aide [de l’option Autoriser les applications bloquées par les développeurs](manage-apps.md#allow-and-block-apps).

À tout moment, l’application peut être désactivée au niveau du locataire à l’aide [de l’option Autoriser et bloquer les applications](manage-apps.md#allow-and-block-apps) dans le Centre d’administration Teams. S’il est désactivé au niveau du locataire, il est bloqué pour tous les utilisateurs, même si les autorisations au niveau de l’utilisateur sont activées.

L’application Parents peut également être désactivée au niveau de l’utilisateur à l’aide [de Gérer les stratégies d’autorisation d’application dans Microsoft Teams](teams-app-permission-policies.md).

## <a name="set-a-preferred-invitation-channel"></a>Définir un canal d’invitation préféré

Les administrateurs peuvent choisir un e-mail ou un SMS comme canal d’invitation de connexion parent par défaut.

Les messages envoyés aux parents et tuteurs seront en texte brut, sans html, mise en forme ou styles appliqués.

> [!NOTE]
> Si vous choisissez SMS comme canal préféré pour envoyer des invitations de connexion parent aux parents et tuteurs, sachez que :
>
> - Les numéros de téléphone parents et tuteurs doivent être au format E.164 pour que les invitations par SMS et la recherche de profil fonctionnent.
>   - Par exemple, mettez en forme les numéros de téléphone en , `+[country code][area code][phone number]`comme `+12223334444`.
> - Les tarifs sms de l’opérateur mobile peuvent être facturés aux parents et tuteurs qui reçoivent des invitations par SMS.

### <a name="set-a-preferred-invite-channel-in-the-teams-admin-center"></a>Définir un canal d’invitation préféré dans le Centre d’administration Teams

1. Connectez-vous au [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
1. Accédez à **Éducation** > **Paramètres parent et tuteur**.
1. Dans le champ **Méthode de contact préférée**, sélectionnez **Email** ou **Téléphone mobile - SMS**.
1. Enregistrez vos modifications.

### <a name="set-a-preferred-invite-channel-using-powershell"></a>Définir un canal d’invitation préféré à l’aide de PowerShell

1. Installez la *version 4.9.0 ou ultérieure* du module Teams PowerShell à l’adresse [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Exécutez la commande ci-dessous et connectez-vous avec les informations d’identification d’administrateur.

    ```powershell
    Connect-MicrosoftTeams
    ```

1. Exécutez la commande ci-dessous pour afficher la valeur actuelle de `ParentGuardianPreferredContactMethod`.

    ```powershell
    Get-CsTeamsEducationConfiguration
    ```

1. Exécutez l’une des commandes ci-dessous pour modifier la valeur.

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod Email
    ```

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod SMS
    ```

## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
