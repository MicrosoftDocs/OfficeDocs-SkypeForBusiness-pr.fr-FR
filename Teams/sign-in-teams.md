---
title: Se connecter à Teams en utilisant l’authentification moderne
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
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8db647d5021aee124dec794e8711662de9f0a1c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121364"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Se connecter à Microsoft Teams en utilisant l’authentification moderne
==========================

Microsoft recommande aux organisations d’utiliser des versions récentes de Windows 10 avec une configuration de jointure Azure AD ou de jointure de domaine hybride. Ceci garantit que les comptes des utilisateurs sont répertoriés dans le gestionnaire de comptes web de Windows, ce qui permet d’activer l’authentification unique pour Teams et les autres applications Microsoft. Cela offre une expérience utilisateur améliorée (connexion silencieuse) et une meilleure position en matière de sécurité.

Microsoft Teams utilise l’authentification moderne pour simplifier et sécuriser l’expérience de connexion. Pour voir comment les utilisateurs se connectent à Teams, consultez [Se connecter à Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Fonctionnement de l’authentification moderne

L’authentification moderne est un processus qui permet à Teams de s’informer que les utilisateurs ont déjà entré leurs informations d’identification (par e-mail et mot de passe professionnels), et ne doivent pas être obligés de les entrer à nouveau pour démarrer l’application. L’expérience peut varier en fonction de plusieurs facteurs, par exemples, si les utilisateurs travaillent dans Windows ou sur un Mac. Il peut également varier selon que votre organisation a activé l’authentification à facteur unique ou l’authentification multi-facteur (l’authentification multi-facteur implique généralement de vérifier les informations d’identification par téléphone, en fournissant un code unique, en entrant un code confidentiel ou présentation d’une empreinte numérique). Voici un récapitulatif de chaque scénario d’authentification moderne.

### <a name="windows-users"></a>Utilisateurs Windows

- Si des utilisateurs ont déjà ouvert une session sur Windows ou d’autres applications Office via leur compte professionnel ou scolaire, ils sont directement dirigés vers l’application lorsqu’ils démarrent Teams. Il ne leur est pas nécessaire d’entrer leurs informations d’identification.

- Microsoft recommande d’utiliser Windows 10 version 1903 ou ultérieure pour optimiser l’expérience d’authentification unique.

- Si les utilisateurs ne sont pas connectés à leur compte professionnel ou scolaire en tout lieu, lorsqu’ils démarrent Teams, ils sont invités à fournir une authentification à un ou plusieurs facteurs (SFA ou MFA), en fonction de ce que votre organisation a décidé de vouloir processus.

- Si les utilisateurs sont connectés à un ordinateur joint à un domaine, lorsqu’ils démarrent Teams, ils peuvent être invités à effectuer une étape d’authentification supplémentaire, selon que votre organisation a choisi d’utiliser l’authentification multi-facteur ou si son ordinateur nécessite déjà l’authentification multi-facteur pour se connecter. Si l’ordinateur requiert déjà l’authentification multi-facteur, lorsqu’il ouvre Teams, l’application démarre automatiquement.

- Sur les PC joints à un domaine, lorsque l’authentification unique est impossible, Teams peut pré-remplir l’écran de connexion à l’aide du nom d’utilisateur principal (UPN). Il peut arriver que vous ne souhaitiez pas utiliser cette option dans certains cas, notamment si votre organisation utilise différents noms d’utilisateur principal localement et dans Azure Active Directory. Dans ce cas, vous pouvez utiliser la clé de Registre Windows suivante pour désactiver le pré-remplissage du nom d’utilisateur principal :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.


### <a name="mac-users"></a>Utilisateurs Mac

Sur MacOS, Teams invite les utilisateurs à entrer leur nom d’utilisateur et informations d’identification, et peut demander l’authentification multifacteur selon les paramètres de votre organisation. Une fois que les utilisateurs ont entré leurs informations d’identification, ils ne sont pas obligés de les redonner. À partir de ce point, Teams démarre automatiquement chaque fois qu’ils travaillent sur le même ordinateur.

## <a name="teams-for-ios-and-android-users"></a>Teams les utilisateurs iOS et Android

Une fois connecté, les utilisateurs mobiles voient une liste de tous les comptes Microsoft 365 qui sont actuellement connectés ou qui ont été précédemment connectés sur leur appareil. Les utilisateurs peuvent appuyer sur l’un des comptes pour se connecter. Il existe deux scénarios de connexion mobile :
    
1. Si le compte sélectionné est actuellement connecté à d’autres applications Office 365 ou Microsoft 365, l’utilisateur est directement dirigé vers Teams. Il n’est pas nécessaire pour l’utilisateur d’entrer ses informations d’identification.
    
2. Si l’utilisateur n’est pas connecté à son compte Microsoft 365 où que ce soit, il est invité à fournir une authentification à facteur unique ou multifacteur (SFA ou MFA), en fonction de ce que votre organisation a configuré pour les stratégies de connexion mobile.

> [!NOTE]
> Pour que les utilisateurs puissent bénéficier de l’expérience de connexion, comme décrit dans cette section, leurs appareils doivent exécuter Teams pour iOS version 2.0.13 (Build 2020061704) ou ultérieure, ou Teams pour Android version 1416/1.0.0.2020061702 ou ultérieure.


### <a name="adding-multiple-accounts-to-teams"></a>Ajout de plusieurs comptes à Teams

Teams pour iOS et Android prend en charge l’ajout de plusieurs comptes d’un seul appareil à Teams. Les images suivantes montrent comment les utilisateurs peuvent ajouter plusieurs comptes dans Teams.
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Ajout de plusieurs comptes dans Teams":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>Utiliser la gestion de la mobilité d’entreprise pour contrôler quels comptes peuvent se connecter à Teams

Teams pour iOS et Android offre aux administrateurs informatiques la possibilité de pousser les configurations des comptes vers les comptes Microsoft 365. Cette fonctionnalité fonctionne avec n’importe quel fournisseur de gestion des appareils mobiles qui utilise le canal  [Configuration de l’application gérée](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) pour iOS ou le canal [Android Enterprise](https://developer.android.com/work/managed-configurations) pour Android.

Pour les utilisateurs inscrits auprès de Microsoft Intune, vous pouvez déployer les paramètres de configuration de compte à l’aide d’Intune dans le portail Azure.

Une fois la configuration du compte effectuée dans le fournisseur de gestion des données de référence, et après que l'utilisateur ait inscrit son appareil, sur le page de connexion, Teams pour iOS et Android affiche uniquement les comptes autorisés sur la page de connexion Teams. L’utilisateur peut appuyer sur l’un des comptes autorisés sur cette page pour se connecter.

Configurez les paramètres de configuration suivants dans le portail Azure Intune pour les appareils gérés.


|Plateforme |Clé  |Valeur  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Activé** : le seul compte autorisé est le compte d’utilisateur géré défini par la clé IntuneMAMUPN.<br> **Désactivé** (ou toute valeur qui n’est pas une correspondance non sensible à la casse à**Activé**) : tout compte est autorisé.        |
|iOS     |   **IntuneMAMUPN**      |   Nom d’utilisateur principal du compte autorisé à se connecter à Teams.<br> Pour les appareils inscrits sur Intune, le jeton {{userPrincipalName}} peut être utilisé pour représenter le compte d’utilisateur inscrit.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Seul le ou les comptes autorisés sont les comptes d’utilisateur gérés définis par cette clé.<br> Un ou plusieurs point-virgule [ ;] - UPN délimités.<br> Pour les appareils inscrits sur Intune, le jeton {{userPrincipalName}} peut être utilisé pour représenter le compte d’utilisateur inscrit.

Une fois la configuration du compte définie, Teams restreint la possibilité de se connecter, de sorte que seuls les comptes autorisés sur les appareils inscrits bénéficient de l'accès.

Pour créer une stratégie de configuration d’application pour les appareils iOS/iPadOS gérés, consultez  [Ajouter des stratégies de configuration d’application pour les appareils iOS/iPadOS gérés](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).

Pour créer une stratégie de configuration d’application pour les appareils Android gérés, consultez  [Ajouter des stratégies de configuration d’application pour les appareils Android gérés](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).


## <a name="switching-accounts-after-completing-modern-authentication"></a>Changer de compte une fois l’authentification moderne terminée

Si les utilisateurs travaillent sur un ordinateur joint au domaine (par exemple, si leur client a activé Kerberos), ils ne peuvent pas changer de compte d’utilisateur une fois l’authentification moderne terminée. Si les utilisateurs ne travaillent pas sur un ordinateur joint à un domaine, ils peuvent changer de compte.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Déconnexion de Teams après l’exécution de l’authentification moderne

Pour se déconnecter de Teams, les utilisateurs peuvent cliquer sur leur image de profil dans la partie supérieure de l’application, puis sélectionner **se déconnecter**. Ils peuvent également cliquer avec le bouton droit sur l’icône de l’application dans la barre des tâches, puis sélectionner **se déconnecter**. Une fois qu’ils se déconnectent de Teams, ils doivent ré-entrer leurs informations d’identification pour lancer l’application.

### <a name="signing-out-of-teams-for-ios-and-android"></a>Déconnexion de Teams pour iOS et Android

Les utilisateurs mobiles peuvent se déconnecter de Teams en accédant au menu, puis en sélectionnant le menu **Plus**, puis en choisissant **Se déconnecter**. Une fois déconnectés, les utilisateurs devront entrer de nouveau leurs informations d’identification lors de la prochaine exécution de l’application.

> [!NOTE]
> Teams pour Android utilise l’authentification unique (SSO) pour simplifier l’expérience de connexion. Les utilisateurs doivent se déconnecter de **toutes** les applications Microsoft, en plus de Teams, afin de se déconnecter complètement de la plateforme Android.

## <a name="urls-and-ip-address-ranges"></a>URL et plages d’adresses IP

Teams a besoin d’une connexion à Internet. Pour comprendre les points de terminaison pouvant être atteints pour les clients qui utilisent Teams dans Office 365 plans, secteur public et autres nuages, consultez [URL et plages d’adresses IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Pour l’instant, Teams a besoin d’accéder (port TCP 443) au service Google ssl.gstatic.com (<https://ssl.gstatic.com)> pour tous les utilisateurs, c’est vrai même si vous n’utilisez pas Gstatic. Teams supprimera cette exigence prochainement (début 2020). nous mettrons à jour cet article en conséquence.

## <a name="troubleshooting-modern-authentication"></a>Résolution des problèmes d’authentification moderne

L’authentification moderne est disponible pour toutes les organisations qui utilisent Teams. par conséquent, si les utilisateurs ne parviennent pas à terminer le processus, il se peut qu’il y ait un problème avec votre domaine ou le compte scolaire ou professionnel de votre organisation.

Pour plus d’informations, voir [Pourquoi est-ce que je rencontre des problèmes pour me connecter à Microsoft Teams ?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)