---
title: Mise en service de Microsoft Teams à grande échelle pour les employés de terrain
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Instructions sur l’utilisation d’un script pour déployer ou mettre en service Microsoft Teams pour les employés de terrain.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a57de3528ac9ef0f950c7034b3c6ee3860b53ea
ms.sourcegitcommit: ad82786076cc965e75b1ec5ffd4bc9bf75437340
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45028170"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>Mettre en service Microsoft Teams à grande échelle pour les employés de terrain

Avez-vous besoin d’intégrer rapidement un grand nombre d’utilisateurs à Microsoft Teams et de configurer une expérience uniformisée pour eux ? Vous pouvez mettre rapidement en service des identités et des équipes, et attribuer toutes les stratégies appropriées pour contrôler l’expérience des utilisateurs finaux en suivant les instructions suivantes.

Dans cette procédure pas à pas, vous apprendrez à :

- Créer un grand nombre d’utilisateurs.
- Créer un grand nombre d’équipes et configurer les canaux appropriés.
- Attribuer une licence à grande échelle.
- Créer des stratégies de messagerie, de configuration d’application et d’autorisation d’application d’équipes appropriées.
- Appliquer ces stratégies à grande échelle à des utilisateurs.
- Affecter un grand nombre d’utilisateurs à une équipe désignée.

> [!NOTE]
> Si vous avez passé en revue ces informations et si vous avez besoin d’aide ou si vous avez des questions, vous pouvez [**cliquez ici**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u) pour contacter le support pour les gants blancs.

## <a name="prerequisites"></a>Conditions préalables

Téléchargez les actifs à partir de [cet emplacement](https://aka.ms/flwteamsscale).

> [!IMPORTANT]
> Les scripts proposés dans le lien fourni ci-dessus sont fournis tels quels par Microsoft et doivent être modifiés en fonction de vos besoins individuels.

## <a name="technical-requirements"></a>Exigences techniques

- Votre client doit disposer du nombre approprié de licences disponibles qui incluent Microsoft Teams. Si vous n’avez pas déjà ces licences, consultez [Exploratoire Teams](teams-exploratory.md) pour bénéficier d’un abonnement d’évaluation gratuit.
- Les utilisateurs qui prennent ces mesures doivent se voir attribuer ces rôles : administrateur général, administrateur d’utilisateur et administrateur de service Teams, dans Azure AD.
- L’utilisateur doit disposer des droits permettant d’installer et de configurer le logiciel sur son ordinateur local.

## <a name="step-by-step-process-overview"></a>Vue d’ensemble du processus étape par étape

1. **Configuration de votre environnement**
    1. Télécharger à partir du référentiel GitHub contenant les exemples de scripts PowerShell et la documentation
    1. Configurer l’environnement local
    1. Configurer les informations d’identification
    1. Configurer les modules PowerShell et les variables d’environnement
1. **Création et configuration d’équipes**
    1. Créer des équipes
    1. Étapes de création d’équipes
    1. Créer des canaux pour les équipes
1. **Création de stratégies d’équipes**
    1. Créer des stratégies de message d’équipes
    1. Créer des stratégies de configuration d’application d’équipes
    1. Créer des stratégies d’autorisation d’application d’équipes
1. **Groupes d’utilisateurs et des groupes de sécurité**
    1. Créer des groupes d’utilisateurs et des groupes de sécurité
    1. Attribuer des licences à des utilisateurs au moyen de licences en fonction des groupes
1. **Attribution d’utilisateurs et de stratégies**
    1. Affecter des utilisateurs à des équipes
    1. Affecter des stratégies d’équipes à des utilisateurs
    1. FACULTATIF : convertir le type d’appartenance au groupe
1. **Test et validation**
    1. Se connecter à Teams à l’aide d’un utilisateur test
    1. Rechercher des erreurs
    1. Gestion des erreurs
1. **Lectures supplémentaires**

## <a name="set-up-your-environment"></a>Configuration de votre environnement

Les étapes suivantes vous permettront de configurer votre environnement :

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>Télécharger à partir du référentiel GitHub contenant les exemples de scripts PowerShell et la documentation

Avant de continuer, vous devez télécharger les scripts à [cet emplacement](https://aka.ms/flwteamsscale).

### <a name="configure-the-local-environment"></a>Configurer l’environnement local

La définition des variables d’environnement local permet d’exécuter les scripts référencés ici à l’aide de chemins d’accès relatifs. Le rootPath est la racine de l'emplacement où vous avez cloné ce référentiel, et le tenantName se présente sous la forme **yourTenant.onmicrosoft.com** (https ne doit pas être inclus).

1. Ouvrez une session PowerShell et accédez au dossier scripts à l’intérieur du référentiel Git cloné.
1. Run the script .\SetConfig.ps1 -tenantName [nom de votre client] -rootPath "chemin d’accès complet à la racine du référentiel Git"

Par exemple : .\SetConfig.ps1-tenantName contoso.onmicrosoft.com-rootPath "C:\data\source\FLWTeamsScale"

### <a name="setup-credentials"></a>Configurer les informations d’identification

> [!IMPORTANT]
> La façon dont les informations d’identification sont gérées dans ces scripts peut ne pas être appropriée à votre utilisation, elles sont facilement adaptées à vos besoins. Suivez toujours les normes et pratiques de votre entreprise pour sécuriser les comptes de service et les identités gérées.

Les scripts utilisent les informations d’identification qui sont stockées en tant que fichiers XML dans $ENV:LOCALAPPDATA\keys, autrement dit, le dossier AppData\Local. La fonction d’assistance **Set-Creds** dans le module **BulkAddFunctions. psm1** doit être appelée pour spécifier les informations d’identification utilisées pour exécuter ces scripts. Cette technique permet de supprimer la nécessité d’authentifier tous les points de terminaison de service tout en conservant les informations d’identification dans un magasin local. À partir de chaque script, les informations d’identification appropriées sont lues à l’aide de la fonction d’assistance **Get-Creds**. Ces informations d’identification sont utilisées pour se connecter aux différents services.

Lorsque vous appelez la fonction **Set-Creds**, vous êtes invité à fournir un nom de fichier XML qui sera écrit dans $ENV:LOCALAPPDATA\keys. Il se peut que vous ayez d’autres informations d’identification pour différents services. Par exemple, vous pouvez avoir des informations d’identification différentes pour MicrosoftTeams, AzureAD et MSonline. Dans ce cas, vous pouvez exécuter la fonction **Se-tCred** plusieurs fois, en enregistrant chaque fichier d’informations d’identification avec un nom approprié.

Exemples : Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

Exécutez le script **SetCreds.ps1** pour enregistrer vos informations d’identification. La fenêtre « Exécution de l’opération "Export-Clixml"…» s’affiche et vous devez entrer « O » pour approuver.

> [!NOTE]
> Le compte utilisé pour les informations d’identification ne peut pas nécessiter d’authentification multifacteur (MFA).

Voici un exemple de la façon dont les différents scripts utilisent les informations d’identification enregistrées pour s’authentifier :

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>Configurer les modules PowerShell et les variables d’environnement

Vous devez installer plusieurs modules PowerShell et vous y connecter, y compris Azure AD, MSAL, MSCloudUtils et MicrosoftTeams.

1. Recherchez le script **ConfigurePowerShellModules.ps1** dans le dossier scripts du référentiel.
1. À partir de PowerShell, exécutez le script **ConfigurePowerShellModules.ps1**.

## <a name="create-and-set-up-teams"></a>Créer et configurer des équipes

Pour communiquer et collaborer avec vos employés de terrain, vous devez tout d’abord établir une série d’équipes et ajouter des canaux standard à celles-ci. C’est ce que nous aborderons par la suite.

### <a name="create-teams"></a>Créer des équipes

Les équipes sont un ensemble de personnes, de contenu et d’outils au sein de votre organisation. Pour la plupart des organisations axées sur les employés de terrain, nous vous conseillons d’implanter une équipe dans un emplacement physique. Par exemple, une équipe pour chacun des éléments suivants :

- Magasin
- Centre de distribution
- Usine de fabrication
- Hôpital
- Épicerie

*Discussion sur les meilleures pratiques* : lorsque vous concevez vos équipes, il est important de garder à l’esprit [les spécifications et les limites de Teams](limits-specifications-teams.md). Pour les organisations de plus petite taille, une équipe à l’échelle de l’organisation peut être utilisée pour simplifier la communication et complémenter une structure dans un emplacement physique. Pour d’autres, une convention d’affectation de noms d’équipe dans un emplacement physique structuré facilite les communications d’entreprise, car elle permet d’envoyer des messages croisés à plusieurs équipes simultanément et en toute simplicité. Par exemple, vous pouvez rechercher les équipes dont le nom contient le mot États-Unis et envoyer des messages croisés ciblés aux équipes situées aux États-Unis. Pour plus d’informations sur l’envoi de messages croisés, cliquez [ici](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).

#### <a name="steps-to-create-teams"></a>Étapes de création d’équipes

1. Recherchez le fichier **TeamsInformation.csv** dans le dossier data du référentiel.
1. Mettez à jour les informations contenues dans le fichier **TeamsInformation.csv** avec les informations propres à votre organisation. Gardez à l’esprit nos meilleures pratiques mentionnées ci-dessus.
1. Recherchez le script **CreateTeams.ps1**.
1. À partir de PowerShell, exécutez le script **CreateTeams.ps1**.

### <a name="create-channels-for-teams"></a>Créer des canaux pour les équipes

Les canaux sont des sections dédiées dans une équipe pour organiser les conversations par sujet, projet, discipline spécifique, et plus. Un canal général est automatiquement attribué à chaque équipe, mais vous pouvez personnaliser votre structure en fonction des besoins de votre entreprise. Par exemple, la structure de votre canal supplémentaire peut inclure les éléments suivants :

- **Fabrication** : sécurité, ligne 1, ligne 2, communications d’entreprise, formation
- **Épicerie** : boulangerie, production, viande, communications d’entreprise, formation
- **Soins de santé** : infirmières, docteurs, unité de soins intensifs 1, unité de soins intensifs 2
- **Hôtellerie** : réception, maintenance, maintenance, entretien ménager, voiturier et bagages, communications d’entreprise, formation
- **Commerce** : avant et arrière du magasin, communications d’entreprise, formation

> [!NOTE]
> Les canaux ne devraient pas être considérés comme une frontière de sécurité. Il s’agit d’un moyen d’organiser vos employés à des fins de collaboration.

*Discussion sur les meilleures pratiques* : lorsque vous concevez votre structure de canaux, il est important de simplifier les choses, notamment lorsque vous cherchez à intégrer un grand nombre d’utilisateurs. Résistez à l’envie de créer des canaux pour chaque situation, rôle ou rubrique afin de réduire le besoin de formation. Sélectionnez 3 à 5 canaux au maximum pour commencer. Il est possible de créer facilement des canaux supplémentaires en cas de besoin. En fait, le canal Général est tout à fait suffisant pour l’instant !

#### <a name="steps-to-create-channels-for-teams"></a>Étapes de création de canaux pour les équipes

1. Recherchez le fichier **TeamsChannels.csv** dans le dossier scripts du référentiel.
1. Mettez à jour le fichier **TeamsChannels.csv** avec les informations propres à votre organisation. Gardez à l’esprit nos meilleures pratiques mentionnées ci-dessus.
1. Recherchez le script**CreateTeamsChannels.ps1** dans le dossier scripts du référentiel.
1. À partir de PowerShell, exécutez le script **CreateTeamsChannels.ps1**.

## <a name="create-teams-policies"></a>Créer des stratégies d’équipes

En tant qu’administrateur, vous pouvez utiliser les stratégies d’équipes dans Microsoft Teams pour contrôler ce que les utilisateurs peuvent voir et peuvent faire au sein de votre organisation. Par exemple, vous pouvez contrôler les applications qui sont épinglées dans la partie gauche de votre navigateur de bureau ou de votre navigateur Web, ou dans la barre inférieure sur les appareils mobiles, afin de simplifier l’expérience des utilisateurs finaux lors de l’intégration d’un grand nombre d’utilisateurs. Certaines de ces stratégies peuvent être créées à l’aide de PowerShell, tandis que d’autres doivent être créées manuellement dans la console d’administration de Teams.

*Discussion sur les meilleures pratiques* : pour chacune des stratégies suivantes, nous cherchons à créer deux stratégies : une pour les employés de terrain et une pour les responsables de terrain. Vous pouvez décider d’en créer autant que vous le souhaitez. Pour la plupart des clients, deux stratégies constituent un bon point de départ, même si, au début, vous attribuez les mêmes paramètres à chaque groupe. Au fur et à mesure que vous acquerrez de l’expérience avec Teams, vous pourrez choisir de différencier davantage l’expérience des utilisateurs et le fait d’avoir déjà créé deux stratégies distinctes peut simplifier les choses.

### <a name="create-teams-message-policies"></a>Créer des stratégies de message d’équipes

Les stratégies de messagerie permettent de contrôler la disponibilité des fonctionnalités de conversation et de messagerie de canal pour les utilisateurs de Microsoft Teams.

*Discussion sur les meilleures pratiques* : bien que vous puissiez utiliser la stratégie globale par défaut créée automatiquement, nous avons choisi de créer une stratégie personnalisée à l’aide des étapes ci-dessous pour offrir une expérience plus sécurisée, simple et diversifiée pour les responsables et les employés de terrain.

#### <a name="steps-to-create-teams-message-policies"></a>Étapes de création de stratégies de message d’équipes

1. Recherchez le fichier **TeamsMessagingPolicies.csv** dans le dossier scripts du référentiel.
1. Mettez à jour le fichier **TeamsMessagingPolicies.csv** avec les informations propres à votre organisation. Pour plus d’informations sur les différentes options, cliquez [ici](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).
1. Recherchez le script**CreateTeamsMessagePolicies.ps1** dans le dossier scripts du référentiel.
1. À partir de PowerShell, exécutez le script **CreateTeamsMessagePolicies.ps1**.

### <a name="create-teams-app-setup-policies"></a>Créer des stratégies de configuration d’application d’équipes

En tant qu’administrateur, vous pouvez utiliser les stratégies de configuration d’application pour effectuer les opérations suivantes :

- Personnaliser Teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs. Vous choisissez les applications à épingler et définissez l’ordre dans lequel elles s’affichent. L’épinglage d’applications vous permet de présenter les applications dont les utilisateurs de votre organisation ont besoin, y compris celles créées par des tiers ou par des développeurs de votre organisation.
- Déterminer si les utilisateurs peuvent épingler des applications à Teams.

Les applications sont épinglées à la barre de l’application. Il s’agit de la barre située sur le côté du client de bureau Teams et au bas des clients mobiles Teams (iOS et Android).

|Client de bureau Teams  |         |Client mobile Teams  |
|---------|---------|---------|
|![Capture d’écran du client de bureau Teams avec les applications épinglées à la barre de *l’application*.](media/FLW-Teams-Desktop-Client.png)         |         |![Capture d’écran du client de bureau Teams avec les applications épinglées à la barre *inférieure*.](media/FLW-Teams-Mobile-Client.png) |

*Discussion sur les meilleures pratiques* : vous gérez les stratégies de configuration d’application dans le Centre d’administration Microsoft Teams. Elles ne peuvent pas être créées à l’aide de PowerShell. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer des stratégies personnalisées et les attribuer à des utilisateurs. La stratégie globale sera automatiquement attribuée aux utilisateurs de votre organisation, sauf si vous créez et leur attribuez une stratégie personnalisée. Dans notre cas, nous créons deux nouvelles stratégies pour les employés et les responsables de terrain afin de leur offrir une expérience plus simple et plus uniformisée qui facilite l’intégration simultanée d’un grand nombre d’utilisateurs. Vous pouvez choisir de personnaliser l’expérience en fonction des besoins de votre entreprise.

#### <a name="create-the-firstline-manager-app-setup-policy"></a>Créer la stratégie de configuration de l’application du responsable de terrain

Les paramètres suivants peuvent être personnalisés en fonction des besoins de votre entreprise. Nous avons choisi quelques options recommandées en fonction des meilleures pratiques pour améliorer la facilité d’intégration de nouveaux utilisateurs à grande échelle. Pour plus d’informations, cliquez [ici](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux  **applications Teams** > **Stratégies de configuration**.
2. Cliquez sur  **Ajouter**.  
3. Entrez un nom pour votre stratégie, ainsi qu’une description. Par exemple : **la stratégie de configuration de l’application du responsable de terrain**.
![Image de la stratégie de configuration de l’application du responsable de terrain.](media/FLW-FLM-App-Setup-Policy.png)

4. Désactivez l’option **Charger des applications personnalisées**.
5. Désactivez l’option **Autoriser l’épinglage de l’utilisateur**.
![Image du commutateur Autoriser l’épinglage de l’utilisateur.](media/FLW-Allow-User-Pinning.png)

6. Si ce n’est pas déjà fait, ajoutez l’application **Shifts**. Pour plus d’informations sur **Shifts**, cliquez [ici](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
![Écran Ajouter des applications épinglées affichant l’application Shifts à côté d’un bouton Ajouter.](media/FLW-Add-Pinned-Apps.png)

7. Supprimez la fonctionnalité Appel si celle-ci s’affiche. Remarque : La suppression de cette fonctionnalité ne la désactive pas pour les utilisateurs, mais l’empêche de s’afficher sur la barre de l’application dans le but de simplifier l’expérience des utilisateurs finaux.
8. Disposez les applications dans l’ordre suivant pour déterminer leur ordre dans la barre de l’application Teams, puis cliquez sur  **Enregistrer**.
    1. Activité
    1. Conversation
    1. Équipes
    1. Calendrier
    1. Shifts ![Capture d’écran de la liste des applications du responsable dans l’ordre.](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>Créer la stratégie de configuration de l’application de l’employé de terrain

Les paramètres suivants peuvent être personnalisés en fonction des besoins de votre entreprise. Nous avons choisi quelques options recommandées en fonction des meilleures pratiques pour améliorer la facilité d’intégration de nouveaux utilisateurs à grande échelle. Pour plus d’informations, cliquez [ici](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux  **applications Teams** > **Stratégies de configuration**.
2. Cliquez sur  **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description. Par exemple : **la stratégie de configuration de l’application de l’employé de terrain**.
![Image de la stratégie de configuration de l’application de l’employé de terrain.](media/FLW-FLW-App-Setup-Policy.png)

4. Désactivez l’option **Charger des applications personnalisées**.
5. Désactivez l’option **Autoriser l’épinglage de l’utilisateur**.
![Image du commutateur Autoriser l’épinglage de l’utilisateur.](media/FLW-Allow-User-Pinning.png)

6. Si ce n’est pas déjà fait, ajoutez l’application **Shifts**. Pour plus d’informations sur **Shifts**, cliquez ici.
![Écran Ajouter des applications épinglées affichant l’application Shifts à côté d’un bouton Ajouter.](media/FLW-Add-Pinned-Apps.png)

7. Supprimez les fonctionnalités Réunions et Appel si celles-ci s’affichent. Remarque : La suppression de ces fonctionnalités ne les désactive pas pour les utilisateurs, mais les empêche de s’afficher sur la barre de l’application dans le but de simplifier l’expérience des utilisateurs finaux.
8. Disposez les applications dans l’ordre suivant pour déterminer leur ordre dans la barre de l’application Teams, puis cliquez sur  **Enregistrer**.
    1. Activité
    1. Conversation
    1. Équipes
    1. Shifts ![Capture d’écran de la liste des applications de l’employé dans l’ordre.](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-teams-app-permission-policies"></a>Créer des stratégies d’autorisation d’application d’équipes

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler les applications auxquelles les utilisateurs de Microsoft Teams peuvent accéder au sein de votre organisation. Vous pouvez autoriser ou bloquer toutes les applications ou des applications spécifiques publiées par Microsoft, par des tiers et par votre organisation. Lorsque vous bloquez une application, les utilisateurs qui disposent de la stratégie ne peuvent pas l’installer à partir de la boutique d’applications Teams. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

*Discussion sur les meilleures pratiques* : vous gérez les stratégies de configuration d’application dans le Centre d’administration Microsoft Teams. Elles ne peuvent pas être créées à l’aide de PowerShell. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer des stratégies personnalisées et les attribuer à des utilisateurs. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Dans notre cas, nous créons deux nouvelles stratégies pour les employés et les responsables de terrain afin de leur offrir une expérience sécurisée et plus uniformisée qui facilite l’intégration simultanée d’un grand nombre d’utilisateurs. Bien évidemment, vous pouvez choisir de personnaliser l’expérience en fonction des besoins de votre entreprise.

#### <a name="create-the-firstline-manager-app-permission-policy"></a>Créer la stratégie d’autorisation de l’application du responsable de terrain

Les paramètres suivants peuvent être personnalisés en fonction des besoins de votre entreprise. Voici quelques options recommandées en fonction des meilleures pratiques qui peuvent améliorer la facilité d’intégration de nouveaux utilisateurs à grande échelle. Pour plus d’informations, cliquez [ici](teams-app-permission-policies.md).

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux  **applications Teams** > **Stratégies d’autorisation**.
2. Cliquez sur  **Ajouter**.
![Affiche la page d’ajout de stratégie d’autorisation d’application, avec des sections pour Microsoft, des applications tierces et des applications clientes.](media/FLW-add-app-permission-policy.png)

3. Entrez un nom pour votre stratégie, ainsi qu’une description. Par exemple : la stratégie d’autorisation de l’application du responsable de terrain.
4. Sous les applications Microsoft, sélectionnez **Autoriser toutes les applications**.
5. Sous les applications tierces, sélectionnez **Autoriser toutes les applications**.
6. Sous les applications clientes, sélectionnez **Autoriser toutes les applications**.
7. Cliquez sur  **Enregistrer**.

#### <a name="create-the-firstline-worker-app-permission-policy"></a>Créer la stratégie d’autorisation de l’application de l’employé de terrain

Les paramètres suivants peuvent être personnalisés en fonction des besoins de votre entreprise. Voici quelques options recommandées en fonction des meilleures pratiques qui peuvent améliorer la facilité d’intégration de nouveaux utilisateurs à grande échelle. Pour plus d’informations, cliquez [ici](teams-app-permission-policies.md).

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux  **applications Teams** > **Stratégies d’autorisation**.
2. Cliquez sur  **Ajouter**.
![Affiche la page d’ajout de stratégie d’autorisation d’application, avec des sections pour Microsoft, des applications tierces et des applications clientes.](media/FLW-add-app-permission-policy.png)

3. Entrez un nom pour votre stratégie, ainsi qu’une description. Par exemple : la stratégie d’autorisation de l’application de l’employé de terrain.
4. Sous les applications Microsoft, sélectionnez **Autoriser toutes les applications**.
5. Sous les applications tierces, sélectionnez **Bloquer toutes les applications**.
6. Sous les applications clientes, sélectionnez **Autoriser toutes les applications**.
7. Cliquez sur  **Enregistrer**.

## <a name="users-and-security-groups"></a>Groupes d’utilisateurs et des groupes de sécurité

### <a name="create-users-and-security-groups"></a>Créer des groupes d’utilisateurs et des groupes de sécurité

Pour utiliser un grand nombre d’utilisateurs dans Teams, vous devez d’abord avoir créé les utilisateurs dans Azure AD. Plusieurs méthodes s’offrent à vous pour mettre en service un grand nombre d’utilisateurs, mais nous allons mettre en évidence les éléments suivants :

- Si ces utilisateurs existent déjà dans l’un des systèmes de ressources humaines suivants, utilisez les liens suivants pour configurer la mise en service des utilisateurs :
  - Facteurs de réussite SAP – [Didacticiel : configurer les facteurs de réussite SAP pour l’attribution des utilisateurs dans Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Workday – [Didacticiel : configurer Workday pour attribuer automatiquement des utilisateurs](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Si vos informations utilisateur sont présentes dans d’autres systèmes, procédez comme suit.

Pour gérer ces utilisateurs de façon plus efficace, vous devez créer deux groupes de sécurité pour les employés et les responsables de terrain, et mettre en service ces utilisateurs directement dans les groupes de sécurité en procédant comme suit :

1. Recherchez le fichier **Users.csv** dans le dossier scripts du référentiel.
1. Mettez à jour le fichier **Users.csv** avec les informations propres à votre organisation.
    1. Par défaut, le script fourni permet de créer un utilisateur avec un mot de passe temporaire qui doit être modifié lors de la première connexion. Si vous ne souhaitez pas utiliser le mot de passe par défaut, modifiez le script **CreateUsers.ps1** en fonction de vos besoins.
    1. Assurez-vous de mettre à jour le champ SecurityGroup pour refléter le nom approprié créé précédemment.
1. Recherchez le fichier **SecurityGroups.csv** dans le dossier scripts du référentiel.
1. Mettez à jour le fichier **SecurityGroups.csv** avec les informations de groupe de sécurité propres à votre organisation.
    1. Assurez-vous de mettre à jour les champs **MessagePolicy**, **AppPermissionPolicy** et **AppSetupPolicy** pour mapper les stratégies appropriées que vous avez créées précédemment.
    1. Assurez-vous de mettre à jour le champ **LicensePlan** pour indiquer la licence que vous avez l’intention d’attribuer à chacun de ces utilisateurs. Pour plus d’informations sur les noms de produits et les identificateurs de plan de service, consultez la documentation [ici](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. À partir de PowerShell, exécutez le script **CreateUsers.ps1** à partir des actifs.

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>Attribuer des licences à des utilisateurs au moyen de licences en fonction des groupes

Les services de cloud computing Microsoft payants, comme Microsoft 365, Office 365, Enterprise Mobility + Security, Dynamics 365 et d’autres produits similaires, nécessitent des licences. Ces licences sont attribuées à tous les utilisateurs qui ont besoin d’accéder à ces services. Pour gérer les licences, les administrateurs utilisent l’un des portails de gestion (Office ou Azure) et les applets de commande PowerShell. Azure Active Directory (Azure AD) est l’infrastructure sous-jacente qui prend en charge la gestion des identités pour tous les services de cloud computing Microsoft. Azure AD stocke des informations sur les états d’affectation de licence pour les utilisateurs.

Pour activer la gestion des licences à grande échelle, Azure AD inclut désormais des licences en fonction des groupes. C’est pour cette raison que nous avons créé les groupes de sécurité plus tôt dans cet article. Vous pouvez attribuer une ou plusieurs licences de produit à un groupe. Azure AD garantit que les licences sont attribuées à tous les membres du groupe. Les nouveaux membres qui rejoignent le groupe bénéficient des licences appropriées. Les licences sont supprimées pour les membres qui quittent le groupe. Cette gestion des licences élimine la nécessité d’automatiser la gestion des licences à l’aide de PowerShell dans le but de refléter les modifications au niveau de la structure de l’organisation et du département pour chaque utilisateur.

## <a name="assign-users-and-policies"></a>Attribuer des utilisateurs et des stratégies

### <a name="assign-users-to-teams"></a>Affecter des utilisateurs à des équipes

Maintenant que vous avez créé les utilisateurs et créé les équipes, il est temps de répartir tous les utilisateurs dans les équipes appropriées.

1. Recherchez le fichier **Users.csv** dans le dossier data dans le référentiel et vérifiez que le mappage vers Teams a correctement été effectué dans ce fichier.
1. À partir de PowerShell, exécutez le script **AssignUserstoTeams.ps1** à partir du dossier scripts dans le référentiel.

### <a name="assign-teams-policies-to-users"></a>Affecter des stratégies d’équipes à des utilisateurs

Maintenant que vous avez créé les stratégies et les utilisateurs pour modifier l’expérience de ces derniers dans Teams, il est temps d’attribuer ces stratégies aux utilisateurs appropriés.

1. Recherchez le fichier **SecurityGroups.csv** dans le dossier data du référentiel et vérifiez que le mappage a correctement été effectué des stratégies vers les groupes.
1. À partir de PowerShell, exécutez le script **AssignPoliciestoUsers.ps1** à partir du dossier scripts dans le référentiel.

### <a name="optional-convert-group-membership-type"></a>FACULTATIF : convertir le type d’appartenance au groupe

> [!NOTE]
> Cette étape est destinée aux personnes qui ont Azure AD P1 ou version ultérieure.

Lorsque vous disposez d’une licence Azure AD P1 ou version ultérieure, vous avez la possibilité d’utiliser l’adhésion aux groupes dynamiques au lieu d’utiliser l’appartenance affectée. Les scripts qui ont créé les équipes créent également des groupes Office du type d’appartenance affectés, ce qui signifie que ses membres doivent être ajoutés de manière explicite.

À l’aide de l’appartenance dynamique, les règles sont écrites pour déterminer si une personne est membre de l’équipe ou non.

> [!NOTE]
> Lorsque vous exécutez ce script, l’appartenance actuelle au groupe est supprimée (à l’exception de ses propriétaires), et les nouveaux membres sont ajoutés à l’exécution de la synchronisation de l’appartenance.

1. Recherchez le fichier **migrateGroups.csv** dans le dossier data du référentiel.
1. Mettez à jour le fichier CSV **migrateGroups.csv** avec les groupes qui seront migrés, ainsi que la règle pour l’appartenance dynamique.
1. Recherchez le fichier**ConvertGroupMembershipType.ps1** dans le dossier scripts du référentiel.
1. À partir de PowerShell, exécutez le script **ConvertGroupMembershipType.ps1**

## <a name="test-and-validate"></a>Tester et valider

### <a name="login-to-teams-with-a-test-user"></a>Se connecter à Teams à l’aide d’un utilisateur test

Maintenant que vous avez effectué toutes les étapes, il est temps de vérifier le travail que vous avez accompli.

1. L’utilisateur créé a un mot de passe initial qui se trouve dans le CreateUsers.ps1. Il est nécessaire de le modifier à sa première connexion.
1. Vérifiez que la présentation de Teams correspond à vos attentes. Si ce n’est pas le cas, passez en revue les sections **Créer des stratégies d’équipes** et **Affecter des stratégies d’équipes à des utilisateurs**.
1. Vérifiez que l’utilisateur est dans la bonne équipe. Si ce n’est pas le cas, passez en revue les sections **Création et configuration d’utilisateurs** et **Affecter des utilisateurs à des équipes**.

> [!NOTE]
> Si la mise en service des employés terrain est gérée au sein de votre équipe de gestion des identités et des accès, vous devez suivre leur processus pour leur fournir leurs informations d’identification.

### <a name="check-for-errors"></a>Rechercher des erreurs

Lorsque vous avez exécuté les scripts précédents, des erreurs ou des exceptions ont été écrites dans un fichier .csv situé dans le dossier des journaux de votre copie du référentiel. Ce fichier peut être utilisé pour enquêter sur les problèmes qui ont pu se produire.

Exemple d’exception : si vous essayez de créer une équipe qui existe déjà dans votre client.

1. Recherchez le dossier **Logs** et passez en revue tout fichier .csv qu’il pourrait contenir. S’il n’y a aucune exception, il se peut que vous ne trouviez pas de fichier d’exception ici.

### <a name="error-handling"></a>Gestion des erreurs

Une gestion des erreurs minime a été implémentée dans ces exemples de script. Il existe des blocs try/catch et, s’il est déclenché, nous stockons l’erreur dans une variable dans le bloc catch. Une gestion des erreurs supplémentaire doit être implémentée conformément à vos préférences.

## <a name="further-reading"></a>Lectures supplémentaires

- [Nouveau canal d’équipe (PowerShell)](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps)
- [Stratégie de messagerie de nouvelle équipe (PowerShell)](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [Attribuez des licences et des comptes d’utilisateur avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
