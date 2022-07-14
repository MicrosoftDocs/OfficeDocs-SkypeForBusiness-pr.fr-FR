---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Cet article explique comment planifier et configurer Cloud Video Interop pour les utilisateurs de votre organisation.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ae7d59a97989d7f0677bf56b46c0a3d51f3e49
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789329"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams

Une fois que vous avez [choisi votre ou vos partenaires Cloud Video Interop](cloud-video-interop.md), vous devez planifier votre déploiement, vous familiariser avec les détails d’approvisionnement et la clé de locataire du partenaire, et donner votre consentement à l’application d’interopérabilité vidéo dans votre organisation. Le diagramme suivant décrit le processus.

![Déploiement de l’interface CVI dans votre organisation.](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Pour plus d’informations sur l’identification d’un partenaire ou d’un partenaire à utiliser dans votre organisation, consultez [Cloud Video Interop pour Microsoft Teams](cloud-video-interop.md) .

Pour planifier l’activation à l’échelle utilisateur/simultanée/à l’échelle du site :

- Choisir un modèle de déploiement/modèle hébergé pour votre utilisation
- Sélectionnez le plan de licence idéal pour votre organisation.
- Vous pouvez planifier la capacité des machines virtuelles en hébergeant votre infrastructure vidéo.

## <a name="configure"></a>Configuration

Pour configurer Cloud Video Interop, procédez comme suit.

1. Obtenez les informations de configuration auprès du partenaire/des partenaires que vous avez choisis (clé de locataire, appIds...). Vous pouvez utiliser un ou plusieurs partenaires d’interopérabilité vidéo dans votre organisation

2. Vérifiez que votre réseau est correctement configuré. Configurez votre pare-feu vidéo basé sur des normes pour la traversée réseau de périmètre à prendre en charge. Par exemple :
    - Cisco VCS-e
    - Polycom RPAD

3. Configurez des salles intégrées avec Exchange et OTD. Dans la plupart des cas, un relais supplémentaire doit être configuré et configuré dans votre environnement.

## <a name="provision"></a>Disposition

La clé de locataire est l’appel sortant vers le service partenaire. Dans l’exemple suivant, 813878896@t.plcm.vc est la clé de locataire.

![Exemple de clé de locataire.](media/tenant-key-example.png)

Vous devez exécuter les applets de commande suivantes pour provisionner la clé de locataire, et également autoriser certains utilisateurs ou toute votre organisation à créer des réunions avec des coordonnées d’interopérabilité vidéo.

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy) :** Microsoft fournit des stratégies prédéfines pour chacun de nos partenaires pris en charge qui vous permettent de désigner les partenaires à utiliser pour l’interopérabilité vidéo cloud.

    Cette applet de commande vous permet d’identifier les stratégies pré-construites que vous pouvez utiliser dans votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy) :** L’applet de commande Grant-CsTeamsVideoInteropServicePolicy vous permet d’affecter une stratégie prédéfini à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider) :** Utilisez le New-CsVideoInteropServiceProvider pour spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider) :** Utilisez le Set-CsVideoInteropServiceProvider pour mettre à jour les informations relatives à un partenaire CVI pris en charge que votre organisation utilise.

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider) :** Obtenez tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider) :** Utilisez Remove-CsVideoInteropServiceProvider pour supprimer toutes les informations du fournisseur sur un fournisseur que votre organisation n’utilise plus.

## <a name="consent"></a>Consentement

Vous devez fournir un consentement d’autorisation pour que les appareils de téléconférence vidéo (VTC) rejoignent les réunions de votre organisation via le service partenaire. Ce lien de consentement sera également fourni par votre partenaire.

Une fois ces étapes terminées, les utilisateurs qui sont activés individuellement via l’applet de commande Grant ci-dessus, ou tous les utilisateurs de l’organisation si le locataire est activé, auront des coordonnées VTC dans toutes les réunions Teams qu’ils planifient. N’importe quel VTC peut participer à ces réunions via ces coordonnées.

|Nom|Description abrégée de l’autorisation d’application| Description|
|---|---|---|
|Calls.JoinGroupCall.All|Participer à des appels de groupe et à des réunions en tant qu’application (préversion)|Permet à l’application de rejoindre des appels de groupe et des réunions planifiées dans votre organisation, sans utilisateur connecté.  L’application sera jointe avec les privilèges d’un utilisateur d’annuaire aux réunions dans votre locataire.|
|Calls.JoinGroupCallasGuest.All|Participer à des appels de groupe et à des réunions en tant qu’utilisateur invité (préversion)|Permet à l’application de rejoindre anonymement des appels de groupe et des réunions planifiées dans votre organisation, sans utilisateur connecté.  L’application sera jointe en tant qu’invité aux réunions de votre locataire.|
|Calls.AccessMedia.All|Accéder aux flux multimédias dans un appel en tant qu’application (préversion)|Permet à l’application d’accéder directement aux flux multimédias dans un appel, sans utilisateur connecté.|
|OnlineMeetings.Read.All|Lire les détails de la réunion en ligne (préversion)|Permet à l’application de lire les détails de la réunion en ligne dans votre organisation, sans utilisateur connecté.|

## <a name="schedule"></a>Horaire

Ensuite, planifiez la réunion Teams avec des coordonnées d’interopérabilité vidéo. L’utilisateur activé peut planifier des réunions Teams via :

- [Complément réunion Teams pour Outlook](teams-add-in-for-outlook.md)
- Bureau client et mobile Teams

## <a name="join"></a>Rejoindre

Vous pouvez participer aux réunions Teams avec vos appareils VTC des manières suivantes :

- IVR (Réponse vocale interactive)
  - Vous pouvez vous connecter à l’IVR du partenaire à l’aide de la tenantkey@domain.
  - Une fois que vous êtes dans l’IVR partenaire, vous êtes invité à entrer l’ID de conférence VTC, qui vous connectera ensuite à la réunion Teams.
- Direct
  - Vous pouvez directement accéder à la réunion Teams sans interagir avec l’IVR du partenaire à l’aide de la fonctionnalité de numérotation directe à l’aide de la chaîne complète de clé de locataire. ConferenceId@domain VTC.
- Numérotation à une seule touche
  - Si vous disposez d’une salle Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation tactile offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).

Enfin, contactez les utilisateurs teams dans vos réunions à l’aide du partage audio, vidéo et de contenu.
