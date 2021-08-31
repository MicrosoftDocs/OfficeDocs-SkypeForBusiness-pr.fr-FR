---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 0fe0ac66b8d1ff9afe43d4d57783e803f426c23c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732953"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams

Une fois que vous avez choisi votre ou vos partenaires [Cloud Video Interop,](cloud-video-interop.md)vous devez planifier votre déploiement, configurer avec les détails de mise en service et la clé de client partenaire, et donner votre consentement à l’application d’interop vidéo dans votre organisation. Le diagramme suivant décrit le processus. 

![Déploiement de CVI dans votre organisation.](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Pour [plus d’informations sur l’Microsoft Teams](cloud-video-interop.md) d’un partenaire ou d’un partenaire à utiliser dans votre organisation, voir Cloud Video Interop. 

Pour planifier l’enablement à l’échelle de l’utilisateur, du concurrent/du site : 

- Sélectionner un modèle de déploiement/hébergé pour votre utilisation
- Sélectionnez le plan de licences idéal pour votre organisation. 
- La capacité des VMs est que vous hébergez votre infrastructure vidéo.

## <a name="configure"></a>Configuration 

Pour configurer Cloud Video Interop, suivez ces étapes. 

1. Obtenez des informations de configuration auprès du partenaire/partenaire que vous avez choisi (clé client, appIds, etc.). Vous pouvez utiliser un ou plusieurs partenaires d’interop vidéo dans votre organisation 

2. Assurez-vous que votre réseau est correctement configuré. Configurez votre pare-feu vidéo basé sur les normes pour le travers de réseau de périmètre à prendre en charge. Par exemple : 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurez des salles intégrées avec Exchange et OTD. Dans la plupart des cas, un relais supplémentaire doit être configuré dans votre environnement.


## <a name="provision"></a>Approvisionnement
 
La clé client sera l’appel sortant vers le service partenaire. Dans l’exemple suivant, 813878896@t.plcm.vc est la clé client. 

![Exemple de clé client.](media/tenant-key-example.png) 

Vous devrez exécuter les cmdlets suivantes pour mettre en service la clé client et permettre également à certains utilisateurs ou à l’ensemble de votre organisation de créer des réunions avec des coordonnées d’interop vidéo.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fournit des stratégies prédécoupées pour chacun de nos partenaires pris en charge qui vous permettent de désigner le ou les partenaires à utiliser pour interop vidéo cloud.

    Cette cmdlet vous permet d’identifier les stratégies pré-construite que vous pouvez utiliser dans votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l'Grant-CsTeamsVideoInteropServicePolicy cmdlet.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** LGrant-CsTeamsVideoInteropServicePolicy cmdlet vous permet d’affecter une stratégie précont enfantin à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Utilisez le New-CsVideoInteropServiceProvider pour spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Utilisez le Set-CsVideoInteropServiceProvider pour mettre à jour les informations sur un partenaire CVI pris en charge par votre organisation.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenez tous les fournisseurs configurés pour une utilisation au sein de l’organisation.
 
- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Utilisez Remove-CsVideoInteropServiceProvider pour supprimer toutes les informations de fournisseur concernant un fournisseur que votre organisation n’utilise plus.  
 
## <a name="consent"></a>Consentement

Vous devrez fournir l’autorisation d’autoriser les périphériques de téléconférence vidéo (VCS) à rejoindre les réunions de votre organisation via le service partenaire. Ce lien d’accord sera également fourni par votre partenaire.  
 
Une fois ces étapes terminées, les utilisateurs qui sont activés individuellement via l’cmdlet Grant ci-dessus, ou tous les utilisateurs de l’organisation si le client est activé, auront des coordonnées VTC dans toutes les réunions Teams qu’ils ont prévues. N’importe quel VTC peut participer à ces réunions via ces coordonnées.


|Nom|Courte description des autorisations d’application| Description|
|--|--|---|
|Calls.JoinGroupCall.All|Rejoindre des appels de groupe et des réunions en tant qu’application (aperçu)|Permet à l’application de participer à des appels de groupe et à des réunions programmées dans votre organisation, sans qu’un utilisateur ne soit inscrit.  L’application sera jointe avec les privilèges d’un utilisateur de l’annuaire pour les réunions dans votre client.|
|Calls.JoinGroupCallasGuest.All|Rejoindre des appels de groupe et des réunions en tant qu’utilisateur invité (prévisualisation)|Permet à l’application de participer de manière anonyme à des appels de groupe et à des réunions programmées dans votre organisation, sans qu’un utilisateur ne soit inscrit.  L’application sera jointe en tant qu’invité aux réunions dans votre client.|
|Calls.AccessMedia.All|Accéder aux flux multimédias dans un appel en tant qu’application (aperçu)|Permet à l’application d’accéder directement aux flux multimédias dans un appel, sans utilisateur inscrit.|
|OnlineMeetings.Read.All|Lire les détails de la réunion en ligne (aperçu)|Permet à l’application de lire les détails de la réunion en ligne dans votre organisation, sans utilisateur inscrit.|

## <a name="schedule"></a>Planifier

Ensuite, planifier Teams réunion avec les coordonnées d’interopation vidéo. L’utilisateur activé peut planifier des réunions d’équipe via :
- [Teams Le add-in de réunion pour Outlook](teams-add-in-for-outlook.md)
- Teams bureau et mobile client


## <a name="join"></a>Rejoindre

Vous pouvez participer Teams réunions avec vos appareils VTC des façons suivantes :
 
- IVR (Réponse vocale interactive)
    - Vous pouvez appeler les IVR du partenaire à l’aide de la tenantkey@domain. 
    - Une fois que vous êtes dans l’IVR partenaire, vous êtes invité à entrer le VTC conferenceId, qui vous connecte ensuite à la Teams partenaire.
- Numérotation directe
    - Vous pouvez appeler directement la réunion Teams sans interagir avec les IVR du partenaire à l’aide de la fonctionnalité de numérotation directe utilisant la chaîne complète de clés client. VTC ConferenceId@domain.
- Numérotation à une pression
    - Si vous avez une salle de numérotation Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation à une pression offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).

Enfin, engagez-vous Teams vos réunions en utilisant l’audio, la vidéo et le partage de contenu.