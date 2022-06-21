---
title: Administration configuration des parents dans Teams pour l'éducation
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams article documentant les prérequis et la configuration des parents dans Teams pour l'éducation.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a38bfbcc8ec7de5e9c1535b1a597b534e46d009
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190616"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurer la connexion parente dans Microsoft Teams pour l'éducation

La connexion parente dans Teams pour l'éducation aide les enseignants à se connecter et à communiquer en toute sécurité avec les parents et les tuteurs des élèves dans leurs équipes de classe à l’aide de Teams.

Cet article fournit des conseils aux professionnels de l’informatique de l’éducation sur les exigences et la configuration de la connexion parente.

## <a name="share-guardian-and-educator-resources"></a>Partager des ressources de tuteur et d’éducateur

Voici quelques ressources que les administrateurs informatiques peuvent partager avec les tuteurs et les enseignants sur la façon dont ils peuvent commencer à utiliser la connexion parente.

- Pour obtenir des conseils sur la configuration des tuteurs, consultez [Connecter avec les enseignants dans Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Pour obtenir des conseils sur la configuration des enseignants, consultez [Communiquer avec les tuteurs dans Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Avantages de la connexion parente

La connexion parents permet aux enseignants et aux tuteurs de discuter, d’envoyer des e-mails et d’appeler à l’aide de Teams.

- Les enseignants peuvent lancer des conversations avec des tuteurs.
  - Si le tuteur n’a pas de compte de consommateur Teams, il reçoit le message initial de l’enseignant et une invitation par e-mail à accéder à Teams.
- Il fonctionne avec la conversation supervisée. Pour plus d’informations, consultez [Utiliser des conversations supervisées dans Microsoft Teams](supervise-chats-edu.md).
  - Par défaut, les tuteurs disposent d’autorisations restreintes, de sorte qu’ils ne peuvent pas discuter avec des étudiants ou supprimer des utilisateurs des conversations.
  - Ce paramètre peut être modifié par l’administrateur du locataire.
- Les enseignants peuvent cliquer sur l’e-mail d’un tuteur pour les envoyer par e-mail à l’aide de leur client de messagerie natif.
- Les enseignants peuvent cliquer sur le numéro de téléphone d’un tuteur pour les appeler dans Teams.

> [!IMPORTANT]
> Pour qu’un clic appelle la fonctionnalité dans Teams, votre locataire a besoin des informations suivantes :
>
> - Fonctionnalités Exchange de la branche publique (PBX).
> - Connexion au rtc.
>
> Microsoft 365 A1 et les plans A3 n’incluent pas les fonctionnalités PBX ni la connexion PSTN. Vous pouvez acheter [des licences de module complémentaire pour chacune de ces licences](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
>
> Microsoft 365 A5 plans incluent uniquement des fonctionnalités PBX à l’aide de Teams Système téléphonique. Vous devrez toujours [acheter un plan d’appel Teams ou utiliser une solution tierce](pstn-connectivity.md) pour vous connecter à des numéros externes sur le rtc.
>
> Pour plus d’informations sur toutes vos options pour obtenir une connectivité RTC, consultez les [options de connectivité RTC](pstn-connectivity.md).
>
> Pour plus d’informations sur Teams licences d’appel, consultez [Teams options de licence de module](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) complémentaire.

## <a name="requirements"></a>Conditions requises

Vous devez utiliser Microsoft Graph ou Synchronisation des données scolaires (SDS) pour renseigner les informations de contact associées aux parents et aux tuteurs de chaque étudiant.

### <a name="graph-api"></a>API Graph

Si vous utilisez déjà [le Kit de développement logiciel (SDK) Microsoft Graph PowerShell](/powershell/microsoftgraph/overview) pour créer des identités Student, vous pouvez facilement inclure le [type de ressource RelatedContact](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>Synchronisation des données scolaires

Teams données de contact du tuteur restent à jour avec SIS à l’aide de Synchronisation des données scolaires (SDS), lorsque SDS est configuré pour la synchronisation régulièrement.

Si guardian est supprimé des enregistrements *d’un étudiant* , toutes les conversations existantes les impliquant contiendront une bannière visible par le propriétaire de la conversation. Cette bannière informera le propriétaire de la conversation de la modification, en lui demandant de supprimer le tuteur de la conversation. Microsoft ne met pas automatiquement à jour l’appartenance à la conversation pour supprimer le tuteur.

- Vous avez besoin de Synchronisation des données scolaires (SDS) pour renseigner les informations de **contact associées aux** parents et aux tuteurs de chaque étudiant.
  - [Déployer la SDS](/schooldatasync/parents-and-guardians-in-sds)

- Si vous avez besoin d’aide pour configurer SDS et remplir **les contacts parents et tuteurs pour les** étudiants de votre locataire, contactez l’équipe de réussite du client EDU en :
  - Exécution du processus DFA au [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Ouverture d’un ticket au [support technique](https://aka.ms/sdssupport).

- Actuellement, SDS prend uniquement en charge l’ingestion de données basée sur CSV pour les contacts parents. Toutefois, vous pouvez utiliser [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) pour toutes les données de liste de présence, et simplement ajouter des contacts parents à l’aide de CSV.
  - Créez un deuxième profil de synchronisation à l’aide du [format de synchronisation CSV SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Extrayez les deux [fichiers parents](/schooldatasync/parent-contact-sync-file-format) remplis avec le reste des fichiers v1 vides (uniquement les en-têtes).
    - User.csv
    - Guardianrelationship.csv
  - Pour afficher un exemple d’ensemble des fichiers CSV v1, consultez les [fichiers GitHub attributs requis minimum](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Si vous souhaitez automatiser l’extraction des fichiers CSV après la synchronisation initiale, lisez notre [document CSV File Sync Automation](/schooldatasync/csv-file-sync-automation).
  - Pour obtenir de l’aide sur la configuration de votre SDS synchronisation des données, contactez [notre équipe de réussite ou](https://www.microsoft.com/fasttrack?rtc=1) [ouvrez un ticket de support](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Teams stratégies du Centre d’administration

- Les propriétaires d’équipe de classe doivent avoir Teams conversation activée.
- Les propriétaires d’équipe de classe doivent disposer d’un accès externe avec **Teams comptes non gérés par une organisation** activés.
  - Cette option doit être activée au niveau du locataire et de l’utilisateur. Le paramètre de niveau client se trouve dans **Users > External Access** dans le centre d’administration Teams. Ce paramètre est également accessible via PowerShell. Les stratégies d’accès externe au niveau de l’utilisateur sont accessibles uniquement via PowerShell. Pour plus d’informations, consultez les commandes PowerShell ci-dessous.

#### <a name="parent-and-guardian-restrictions"></a>Restrictions relatives aux parents et aux tuteurs

Les parents et les tuteurs sont classés en tant *qu’utilisateurs externes* dans la connexion parents, ce qui signifie qu’ils n’ont pas de droits de locataire complets. Ils ont uniquement accès à la conversation ou aux conversations dont ils font partie et aux fichiers, images et autres contenus partagés dans la conversation.

Pour les conversations externes, les utilisateurs internes et externes peuvent ajouter des utilisateurs à la conversation. Pour en savoir plus sur l’expérience de conversation externe, consultez [Gérer les réunions externes et la conversation dans Microsoft Teams](manage-external-access.md).

En outre, les utilisateurs externes peuvent voir la présence (hors connexion, disponible, occupée, etc.) des utilisateurs de votre organisation, mais cela peut être désactivé à l’aide de PowerShell pour protéger la confidentialité des utilisateurs. Dans PowerShell, utilisez [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) et définissez ``EnablePrivacyMode=true``.

Même si les parents et les tuteurs sont des utilisateurs externes, leurs contributions aux conversations sont détectables. Découvrez comment effectuer une enquête Teams eDiscovery en lisant [Effectuer une enquête eDiscovery sur le contenu dans Microsoft Teams](ediscovery-investigation.md).

> [!IMPORTANT]
> Les administrateurs informatiques doivent informer tous les propriétaires de classes sur les meilleures pratiques pour partager des informations sur les étudiants via une conversation, y compris les risques pour la confidentialité des étudiants.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Blocage d’un parent ou d’un tuteur dans une conversation

Les enseignants peuvent bloquer un tuteur dans la conversation initiée dans la connexion parente.

Le propriétaire de la classe peut :

1. Ouvrez la carte de profil du tuteur, sélectionnez l’ellipse et **Bloquer l’utilisateur**.
2. Ensuite, supprimez le tuteur de la conversation.

L’utilisateur bloqué ne pourra pas démarrer des conversations supplémentaires avec le propriétaire de la classe.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Autoriser l’accès externe avec des comptes Teams non gérés par une organisation

Pour permettre aux enseignants de communiquer avec les parents et les tuteurs dans Teams, l’administrateur informatique du locataire de l’éducation doit mettre à jour les stratégies du locataire afin d’autoriser l’accès externe à Teams comptes en dehors du locataire. Pour plus d’informations sur la gestion de l’accès externe, consultez [Gérer l’accès externe dans Microsoft Teams](manage-external-access.md).

Voici les étapes à suivre pour activer l’accès externe pour les parents et les tuteurs.

1. Installez la dernière Microsoft Teams préversion du module PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. À l’aide d’informations d’identification disposant de privilèges d’administrateur, exécutez les commandes suivantes :

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    Le paramètre de stratégie qui active l’accès externe avec Teams comptes non gérés par une organisation au niveau de l’utilisateur (`EnableTeamsConsumerAccess`) est activé par défaut pour toutes les stratégies d’accès externe au niveau de l’utilisateur. Le paramètre au niveau du locataire et le paramètre de stratégie au niveau de l’utilisateur doivent être activés pour qu’un utilisateur dispose d’un accès externe avec Teams comptes non gérés par une organisation. Si vous ne souhaitez pas que cet accès soit activé pour tous les utilisateurs de votre locataire, assurez-vous que votre paramètre au niveau du locataire est désactivé, mettez à jour les stratégies d’accès externe au niveau de l’utilisateur affectées à vos utilisateurs, puis activez le paramètre au niveau du locataire.

    Pour vérifier les stratégies d’accès externe au niveau de l’utilisateur et les personnes auxquelles elles sont affectées, vous pouvez effectuer les étapes suivantes :

3. Vérifiez qu’il existe des stratégies d’accès externe au niveau de l’utilisateur.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Pour chaque stratégie autre que la stratégie « Global », vérifiez les utilisateurs auxquels la stratégie est affectée.

   > [!NOTE]
   > Tous les utilisateurs qui n’ont pas de stratégie spécifique affectée reviendront à la stratégie « Global ». La stratégie « Global » est affectée à tous les nouveaux utilisateurs qui sont ajoutés au locataire.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Étant donné que toutes les stratégies d’accès externe au niveau utilisateur ont `EnableTeamsConsumerAccess` la valeur true par défaut, si vous souhaitez ajuster le `EnableTeamsConsumerAccess` paramètre pour des utilisateurs spécifiques, vous pouvez créer/modifier des stratégies d’accès externe existantes avec des paramètres ajustés et/ou réaffecter des utilisateurs à des stratégies nouvelles ou existantes à l’aide des applets de commande PowerShell suivantes :

- Créer une stratégie d’accès externe : [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personnaliser une stratégie d’accès externe existante (y compris la stratégie « Global » ) : [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Les stratégies par défaut d’abonnement suivantes ne peuvent pas être modifiées : « FederationAndPICDefault », « FederationOnly », « NoFederationAndPIC ». La stratégie « FederationAndPICDefault » était auparavant affectée à tous les utilisateurs par défaut, mais la stratégie « Global » est désormais attribuée aux nouveaux utilisateurs par défaut. Si vous devez modifier les paramètres de stratégie pour les utilisateurs auxquels ces stratégies d’abonnement par défaut sont affectées, affectez des stratégies différentes avec les paramètres appropriés à ces utilisateurs.

- Affecter une stratégie d’accès externe à un seul utilisateur : [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Affecter une stratégie à un ensemble d’utilisateurs : [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Une fois que les stratégies d’accès externe au niveau utilisateur sont correctement définies pour les utilisateurs de votre locataire, vous pouvez activer le paramètre au niveau du locataire (`AllowTeamsConsumer`) pour le locataire à l’aide de l’applet de commande suivante :

- Définissez les paramètres de configuration de fédération pour votre locataire : [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Activer l’application Parents dans le centre d’administration Teams

L’application Parents est désactivée par défaut, de sorte que les propriétaires d’équipe de classe ne la voient pas dans leurs équipes de classes tant qu’elle n’est pas autorisée par le biais du centre d’administration Teams. L’application Parents est activée dans le centre d’administration Teams à l’aide [d’Autoriser les applications bloquées par les éditeurs](manage-apps.md#apps-blocked-by-publishers).

À tout moment, l’application peut être désactivée au niveau du locataire à l’aide des [applications Autoriser et bloquer](manage-apps.md#allow-and-block-apps) dans le centre d’administration Teams. S’il est désactivé au niveau du locataire, il est bloqué pour tous les utilisateurs, même si les autorisations au niveau de l’utilisateur sont activées.

L’application Parents peut également être désactivée au niveau de l’utilisateur à l’aide des [stratégies gérer les autorisations d’application dans Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
