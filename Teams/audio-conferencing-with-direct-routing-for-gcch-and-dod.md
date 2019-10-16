---
title: Audioconférence avec routage direct pour GCCH et DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Découvrez comment utiliser les fonctionnalités d’audioconférence avec le routage direct dans les environnements GCCH et DoD.
ms.openlocfilehash: 67c8a8b3ec16f36a93eb4561473facacdbd85464
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516734"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconférence avec routage direct pour GCC High et DoD

Les conférences audio avec le routage direct de GCC High et DoD permettent aux participants de participer à des réunions d’équipes au sein de votre organisation de la société ou de la DoD, à l’aide d’un appareil téléphonique. Les participants à la réunion peuvent préférer utiliser un appareil téléphonique pour participer à des réunions d’équipes dans des scénarios tels que la connectivité Internet est limitée ou lorsque les utilisateurs sont en déplacement et ne peuvent pas accéder à Teams. Les participants peuvent rejoindre une réunion en composant un numéro de téléphone à composer pour votre organisation ou en faisant appel à la réunion par téléphone.

Dans le cadre de l’audioconférence avec le routage direct de GCC High et DoD, votre organisation utilise ses propres numéros en tant que numéros de téléphone rendez-vous et tous les appels sortants vers les appareils mobiles sont routés via le routage direct. Pour activer le service, les organisations doivent configurer le routage direct et configurer des numéros de téléphone qui peuvent être utilisés en tant que numéros de téléphone à composer. La configuration requise pour l’utilisation du routage direct est différente de celle proposée par le service de conférence rendez-vous par Microsoft, qui n’est pas un service de conférence téléphonique.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Déploiement de l’audioconférence avec le routage direct pour les services d’audioconférence et de DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Étape 1 : obtenir des services d’audioconférence avec le routage direct pour les licences GCC High ou DoD 

Pour utiliser l’audioconférence dans GCC High ou DoD, votre organisation et les utilisateurs de votre organisation doivent disposer d’une conférence audio avec une licence de routage directe attribuée. Vous trouverez ci-dessous les licences dont vous avez besoin pour activer l’audioconférence avec le routage direct pour la fonction DoD High ou DoD.

- GCC High : une audioconférence pour les conférences audio : une licence pour les clients de votre organisation et de l’audioconférence : des licences plus élevées pour vos utilisateurs.

- DoD : licence de client de services d’audioconférence pour les licences de votre organisation et audioconférence-DoD pour vos utilisateurs.

Une licence client et au moins une licence utilisateur sont requises pour activer le service. Vous ne pouvez pas activer le service avec uniquement la licence client ou uniquement pour les licences utilisateur. Pour obtenir des licences de service pour votre client et les utilisateurs de votre organisation, contactez l’équipe de votre compte.

> [!IMPORTANT]
> Les utilisateurs ne peuvent pas être activés pour les conférences audio avec le routage direct tant que les numéros de téléphone de connexion n’ont pas été configurés. Nous vous conseillons de ne pas affecter les conférences audio avec le routage direct pour les licences pour les utilisateurs de la fonction DoD (High ou DoD) aux utilisateurs tant que vous n’avez pas configuré les numéros de téléphone à composer comme décrit dans cet article.

### <a name="step-2-set-up-direct-routing"></a>Étape 2 : configurer le routage direct

Pour configurer le routage direct, voir les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)

- [Configurer le routage direct](direct-routing-configure.md)

> [!NOTE]
> Lorsque vous configurez le routage direct, n’oubliez pas d’utiliser les noms de domaine complets et les ports de FQDN

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Étape 3 : configurer les numéros de téléphone à composer

Les numéros de téléphone à composer sont les numéros de téléphone associés à votre pont de conférence audio. Ces numéros permettent aux participants de participer à des réunions planifiées par des utilisateurs au sein de votre organisation. Ces numéros sont également inclus dans les invitations aux réunions des utilisateurs qui planifient des réunions au sein de votre organisation et sur la page « Rechercher un numéro local ».

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Définir des numéros de téléphone de service dans votre client

Vous pouvez utiliser l’applet de demande PowerShell New-csHybridTelephoneNumber pour définir des numéros de téléphone de service dans votre client, qui peuvent être utilisés pour acheminer les appels vers le service de visioconférence via le routage direct. 

  ```
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Par exemple :
  ```
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Affecter les numéros de téléphone de service au pont de conférence audio de votre organisation

Vous pouvez affecter des numéros de service à votre pont de conférence audio de votre organisation à l’aide de l’applet de méthode PowerShell Register-Csonlinedialinconferencingservicenumberhttp.

  ```
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Vous pouvez voir l’ID de votre pont de conférence audio à l’aide de Get-CsOnlineDialInConferencingBridge. Par exemple :

  ```
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Étape 4 : attribuer des conférences audio avec le routage direct pour les licences GCC High ou DoD à vos utilisateurs

Pour attribuer des conférences audio avec le routage direct pour les licences GCC High ou DoD aux utilisateurs, voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Étape 5 : (facultatif) afficher une liste des numéros de conférence audio dans teams

Pour afficher la liste des numéros de conférence audio de votre organisation, consultez la [liste des numéros de conférence audio dans Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md) .

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Étape 6 : (facultatif) définir les langues du standard automatique pour les numéros d’accès pour les conférences audio de votre organisation

Pour modifier la langue des numéros d’accès pour les conférences audio de votre organisation, voir [définir les langues du standard automatique pour les conférences audio dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Étape 7 : (facultatif) modifier les paramètres du pont de conférence audio de votre organisation

Pour modifier les paramètres du pont de conférence audio de votre organisation, voir [modifier les paramètres d’un pont de conférence audio](change-the-settings-for-an-audio-conferencing-bridge.md) .

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Étape 8 : (facultatif) définir les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation

Pour modifier l’ensemble des numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation, voir [définir les numéros de téléphone inclus dans les invitations dans Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Les fonctionnalités d’audioconférence ne sont pas prises en charge dans les conférences audio avec le routage direct de GCC High et DoD

Voici les fonctionnalités de l’audioconférence qui ne sont pas prises en charge dans les conférences audio avec le routage direct pour les services de préversion de GCC et de DoD :

- Notifications d’entrée et de sortie utilisant l’enregistrement de nom. Pour les conférences audio avec le routage direct, les notifications d’entrée et de sortie sont lues dans la réunion en tant que tonalités.

- Stratégies de restriction des appels sortants pour les conférences audio. Les contrôles de niveau utilisateur permettant de limiter les appels sortants ne sont pas applicables aux appels sortants de réunion routés via le routage direct.

- Désactivez l’utilisation des numéros sans frais pour l’organisateur de la réunion. Les contrôles de niveau utilisateur permettant de limiter l’utilisation des numéros gratuits pour participer aux réunions de votre organisation ne sont pas applicables aux appels routés via le routage direct.

- Envoyer des notifications par courrier électronique aux utilisateurs en cas de modification de leurs paramètres. Les messages électroniques de notification de l’audioconférence ne sont pas pris en charge pour les conférences audio avec le routage direct pour les services de messagerie générale de GCC.
