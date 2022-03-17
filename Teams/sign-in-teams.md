---
title: Se connecter à Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Découvrez comment fonctionne l’authentification moderne, comment changer de compte et comment résoudre les problèmes liés à l’authentification moderne. Inclut comment demander à Teams d'ignorer le pré-remplissage du nom de l'utilisateur (UPN) à l’ouverture de session.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a00561f10e78a18acc146df4ed8a76b103c937c9
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514565"
---
# <a name="sign-in-to-microsoft-teams"></a>Se connecter à Microsoft Teams

## <a name="windows-users"></a>Utilisateurs Windows

Microsoft recommande aux organisations d’utiliser des versions récentes de Windows 10 avec une configuration de jointure Azure AD ou de jointure de domaine hybride. Utiliser des versions récentes permet d’imprimer les comptes des utilisateurs dans le Gestionnaire de Compte Web Windows, ce qui permet d’activer la connexion unique à Teams et d’autres applications M/icrosoft. La connexion unique offre une meilleure expérience d’utilisateur (connexion silencieuse) et une meilleure position en matière de sécurité.

Microsoft Teams utilise l’authentification moderne pour simplifier et sécuriser l’expérience de connexion. Pour voir comment les utilisateurs se connectent à Teams, consultez [Se connecter à Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

### <a name="how-modern-authentication-works"></a>Fonctionnement de l’authentification moderne

L’authentification moderne est un processus qui permet à Teams de s’informer que les utilisateurs ont déjà entré leurs informations d’identification, tels que leur email professionnel et le mot de passe, et ne doivent pas être obligés de les entrer à nouveau pour démarrer l’application. L’expérience varie en fonction de plusieurs facteurs, par exemple, si les utilisateurs travaillent sur Windows ou sur un Mac. Il peut également varier selon que votre organisation a activé l’authentification à facteur unique ou multi-facteur. L’authentification multi-facteur implique généralement de vérifier les informations d’identification par téléphone, en fournissant un code unique, en entrant un code confidentiel ou en présentant une empreinte numérique. Voici un récapitulatif de chaque scénario d’authentification moderne.

L’authentification moderne est disponible pour toutes les organisations qui utilisent Teams. Si les utilisateurs ne parviennent pas à terminer le processus, il est possible qu’il y ait un problème avec la configuration Azure AD de votre organisation. Pour plus d’informations, voir [Pourquoi est-ce que je rencontre des problèmes pour me connecter à Microsoft Teams ?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

- Si des utilisateurs ont déjà ouvert une session sur Windows ou d’autres applications Office via leur compte professionnel ou scolaire, ils sont directement dirigés vers l’application lorsqu’ils démarrent Teams. Il n’est pas nécessaire pour eux d’entrer leurs informations d’identification.

- Microsoft recommande d’utiliser Windows 10 version 1903 ou ultérieure pour optimiser l’expérience d’authentification unique.

- Si les utilisateurs ne sont pas connectés à leur compte Microsoft professionnel ou scolaire ailleurs, lorsqu’ils démarrent Teams, ils sont invités à fournir une authentification à un ou plusieurs facteurs (SFA ou MFA). Ce processus dépend de la décision de la procédure de connexion que votre organisation a jugée nécessaire.

- Si les utilisateurs sont connectés à un ordinateur joint à un domaine, lorsqu’ils démarrent Teams, ils peuvent être invités à effectuer une étape d’authentification supplémentaire, selon que votre organisation a choisi d’utiliser l’authentification multi-facteur ou si son ordinateur nécessite déjà l’authentification multi-facteur pour se connecter. Si l’ordinateur requiert déjà l’authentification multi-facteur, lorsqu’il ouvre Teams, l’application démarre automatiquement.

- Sur les PC joints à un domaine, lorsque l’authentification unique est impossible, Teams peut pré-remplir l’écran de connexion à l’aide du nom d’utilisateur principal (UPN). Il peut arriver que vous ne souhaitiez pas utiliser cette option dans certains cas, notamment si votre organisation utilise différents noms d’utilisateur principal localement et dans Azure Active Directory. Dans ce cas, vous pouvez utiliser la clé de Registre Windows suivante pour désactiver le pré-remplissage du nom d’utilisateur principal :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>Se connecter à un autre compte sur un ordinateur connecté à un domaine

Il se peut que les utilisateurs de l’ordinateur joint au domaine ne puissent pas se connecter à Teams avec un autre compte dans le même domaine Active Directory.

## <a name="macos-users"></a>Utilisateurs MacOS

Sur MacOS, Teams invite les utilisateurs à entrer leur nom d’utilisateur et informations d’identification, et peut demander l’authentification multi-facteur selon les paramètres de votre organisation. Une fois que les utilisateurs ont entré leurs informations d’identification, ils ne sont pas obligés de les redonner. À partir de ce point, Teams démarre automatiquement chaque fois qu’ils travaillent sur le même ordinateur.

## <a name="teams-on-ios-and-android-users"></a>Teams sur les utilisateurs iOS et Android

Une fois connecté, les utilisateurs mobiles voient une liste de tous les comptes Microsoft 365 qui sont actuellement connectés ou qui ont été précédemment connectés sur leur appareil. Les utilisateurs peuvent appuyer sur l’un des comptes pour se connecter. Il existe deux scénarios de connexion mobile :

1. Si le compte sélectionné est actuellement connecté à d’autres applications Office 365 ou Microsoft 365, l’utilisateur est directement dirigé vers Teams. Il n’est pas nécessaire pour l’utilisateur d’entrer ses informations d’identification.

2. Si l’utilisateur n’est pas connecté à son compte Microsoft 365 ailleurs, il est invité à fournir une authentification à facteur unique ou multi-facteur (SFA ou MFA), en fonction de ce que votre organisation a configuré pour les stratégies de connexion mobile.

> [!NOTE]
> Pour que les utilisateurs puissent bénéficier de l’expérience de connexion, comme décrit dans cette section, leurs appareils doivent exécuter Teams pour iOS version 2.0.13 (Build 2020061704) ou ultérieure, ou Teams pour Android version 1416/1.0.0.2020061702 ou ultérieure.

## <a name="using-teams-with-multiple-accounts"></a>Utilisation de Teams avec plusieurs comptes

Teams pour iOS et Android prend en charge l’utilisation de plusieurs comptes professionnels ou scolaires et de plusieurs comptes personnels côte à côte. Les applications de bureau Teams prennent en charge un compte professionnel ou scolaire et un compte personnel côte à côte en décembre 2020, avec une prise en charge de plusieurs comptes professionnels ou scolaires.

Les images suivantes montrent comment les utilisateurs peuvent ajouter plusieurs comptes dans les applications mobile Teams.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Ajout de plusieurs comptes dans Teams.":::

## <a name="restrict-sign-in-to-teams"></a>Restreindre la connexion à Teams

Il se peut que l’organisation souhaite limiter la façon dont les applications approuvées par l’entreprise sont utilisées sur les appareils gérés, par exemple pour restreindre la possibilité pour les étudiants ou les employés d’accéder aux données d’autres organisations ou d’utiliser des applications approuvées par l’entreprise pour des scénarios personnels. Ces restrictions peuvent être appliquées en définissant des stratégies de périphériques reconnues par les applications Teams.

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>Comment restreindre la connexion sur les appareils mobiles

Teams pour iOS et Android offre aux administrateurs informatiques la possibilité de pousser les configurations des comptes vers les comptes Microsoft 365. Cette fonctionnalité fonctionne avec n'importe quel fournisseur Gestion des appareils mobiles (MDM) qui utilise le canal [Configuration d'application gérée](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) pour iOS ou le canal [Android Entreprise](https://developer.android.com/work/managed-configurations) pour Android.

Pour les utilisateurs inscrits auprès de Microsoft Intune, vous pouvez déployer les paramètres de configuration de compte à l’aide d’Intune dans le portail Azure.

Une fois la configuration du compte effectuée dans le fournisseur de Gestion des appareils mobiles (MDM), et après inscription de son appareil par l'utilisateur, sur la page de connexion, Teams pour iOS et Android affiche uniquement le(s) compte(s) autorisé(s) sur la page de connexion Teams. L’utilisateur peut appuyer sur l’un des comptes autorisés de cette page pour se connecter.

Configurez les paramètres de configuration suivants dans le portail Azure Intune pour les appareils gérés.

|Plateforme |Clé  |Valeur  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Activé** : le seul compte autorisé est le compte d’utilisateur géré défini par la clé IntuneMAMUPN.<br> **Désactivé** (ou toute valeur qui n’est pas une correspondance non sensible à la casse à **Activé**) : tout compte est autorisé.        |
|iOS     |   **IntuneMAMUPN**      |   Nom d’utilisateur principal du compte autorisé à se connecter à Teams.<br> Pour les appareils inscrits sur Intune, le jeton {{userprincipalname}} peut être utilisé pour représenter le compte d’utilisateur inscrit.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Seul le ou les comptes autorisés sont les comptes d’utilisateur gérés définis par cette clé.<br> Un ou plusieurs point-virgule ;] - UPN délimités.<br> Pour les appareils inscrits sur Intune, le jeton {{userprincipalname}} peut être utilisé pour représenter le compte d’utilisateur inscrit.

Une fois la configuration du compte définie, Teams restreint la possibilité de se connecter, de sorte que seuls les comptes autorisés sur les appareils inscrits bénéficient de l'accès.

Pour créer une stratégie de configuration d’application pour les appareils iOS/iPadOS gérés, consultez [Ajouter des stratégies de configuration d’application pour les appareils iOS/iPadOS gérés](/mem/intune/apps/app-configuration-policies-use-ios).

Pour créer une stratégie de configuration d’application pour les appareils Android gérés, consultez [Ajouter des stratégies de configuration d’application pour les appareils Android gérés](/mem/intune/apps/app-configuration-policies-use-android).

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>Comment restreindre la connexion sur les appareils de bureau

Les applications Teams sur Windows et MacOS prennent en charge les stratégies d’appareils qui restreignent la connexion à votre organisation. Les stratégies peuvent être définies via les solutions de gestion des appareils usuelles, telles que la gestion des appareils mobiles ou les objets de stratégie de groupe. 

Lorsque cette stratégie est configurée sur un appareil, les utilisateurs peuvent uniquement se connecter à l’aide de comptes hébergés sur un client Azure AD inclus dans la « Liste verte du client » définie dans la stratégie. La stratégie s’applique à tous les signataires, y compris les comptes premiers et supplémentaires. Si votre organisation couvre plusieurs clients Azure AD, vous pouvez inclure plusieurs ID de client dans la liste verte. Les liens permettant d’ajouter un autre compte peuvent continuer à être visibles dans l’application Teams, mais ils ne seront pas opérationnels.

> [!NOTE]
> 
>1. La stratégie restreint uniquement les connexions. Cela ne limite pas la possibilité pour les utilisateurs d'être invités en tant qu'invités dans d'autres clients Azure AD, ou de passer à ces autres clients (où les utilisateurs ont été invités en tant qu'invités).
>2. La stratégie requiert Teams pour Windows version 1.3.00.30866 ou ultérieure, et Teams pour MacOS version 1.3.00.30882 (publiée mi-novembre 2020).

**stratégies pour les fichiers de modèles d’administration Windows** (ADMX/ADML) sont disponibles à partir du [centre de téléchargement](https://www.microsoft.com/download/details.aspx?id=49030) (le nom descriptif du paramètre de stratégie dans le fichier de modèle d’administration est « Restreindre la connexion à Teams aux comptes dans des locataires spécifiques »). En outre, vous pouvez définir manuellement des clés dans le Registre Windows :

- Nom de la valeur : RestrictTeamsSignInToAccountsFromTenantList
- Type de valeur : chaîne
- Données de valeur : ID de client ou liste d’ID client séparés par des virgules
- Chemin d’accès : utilisez l’une des options suivantes :

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

Exemple : OFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID ou SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = ID client 1, ID client 2, ID client 3

**Stratégies pour MacOS** Pour les appareils gérés par MacOS, utilisez .plist pour déployer les restrictions de connexion. Le profil de configuration est un fichier .plist, composé d’entrées identifiées par une clé (qui indique le nom de la préférence), suivie d’une valeur qui dépend de la nature de la préférence. Les valeurs peuvent être simples (par exemple, une valeur numérique) ou complexes, comme une liste imbriquée de préférences.

- Domaine : com.microsoft.teams
- Clé : RestrictTeamsSignInToAccountsFromTenantList
- Type de données : chaîne
- Commentaires : entrez une liste séparée par des virgules pour les ID client Azure AD

### <a name="global-sign-in"></a>Connexion globales

L’application Android Teams prend désormais en charge la connexion et la déconnexion globales pour offrir une expérience de connexion et de déconnexion aisée pour employés de première ligne. Les employés peuvent choisir un appareil dans le pool de périphériques partagé et effectuer une connexion unique personnelle afin de l’utiliser pour la durée de leur équipe. À la fin de leur équipe, ils doivent pouvoir effectuer une déconnexion globale de l’appareil. Pour en savoir plus, consultez [Se déconnecter de Teams](sign-out-of-teams.md) . Cette opération permet de supprimer toutes les informations personnelles et professionnelles de l’appareil afin de pouvoir rétablir l’appareil sur le pool d’appareils. Pour obtenir cette fonctionnalité, l’appareil doit être en mode partagé. Veillez à mettre fin à une réunion ou à un appel actif sur l’appareil avant de vous déconnecter. Pour découvrir comment configurer un appareil partagé, voir [Comment utiliser un mode d’appareil partagé dans Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

L’expérience de connexion est similaire à l’expérience de signature Teams standard.

## <a name="urls-and-ip-address-ranges"></a>URL et plages d’adresses IP

Microsoft Teams requiert un accès à internet pour comprendre les points de terminaison pouvant être atteints pour les clients qui utilisent Teams dans les plans Office 365, Secteur Public et autres cloud, consultez [URLs et plages d’adresses IP d’Office 365](/office365/enterprise/urls-and-ip-address-ranges).


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
