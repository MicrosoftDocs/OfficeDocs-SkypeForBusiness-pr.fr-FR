---
title: Configurer une interopérabilité vidéo dans le nuage pour Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Cet article explique comment planifier et configurer une interopérabilité vidéo Cloud pour les utilisateurs dans votre organisation.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2090036aa5e1a05e46581d365d9b6b4aeb94b32
ms.sourcegitcommit: fbef2bfa4e5eb27799aa25f0e890cfb18013cf72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25040779"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurer une interopérabilité vidéo dans le nuage pour Microsoft Teams

Une fois que vous avez [choisi sur vos partenaires interopérabilité vidéo sur le nuage](cloud-video-interop.md), vous devrez planifier votre déploiement, get configurer avec des détails de mise en service et la clé client partenaire et consentement de l’utilisateur à l’application d’interopérabilité vidéo dans votre organisation. Le diagramme suivant présente le processus. 

![Déploiement CVI dans votre organisation](media/deploying-cvi.png)

## <a name="plan"></a>Planifier

Pour plus d’informations sur l’identification d’un partenaire ou des partenaires à utiliser dans votre organisation, voir [Interopérabilité vidéo de Cloud pour les équipes Microsoft](cloud-video-interop.md) . 

Planification de la prise en charge à l’échelle utilisateur/simultanés/site sur : 

- Choisir un modèle hébergé/modèle de déploiement pour l’utilisation
- Sélectionnez le plan de licence idéale pour votre organisation. 
- Planifier la capacité des ordinateurs virtuels est de que vous hébergez votre infrastructure vidéo.

## <a name="configure"></a>Configuration 

Pour configurer une interopérabilité vidéo sur le nuage, procédez comme suit. 

1. Obtenir des informations de configuration des partenaires/partenaires que vous avez choisi (clé client, AppID...). Vous pouvez utiliser un ou plusieurs partenaires interopérabilités vidéo dans votre organisation 

2. Assurez-vous que votre réseau est configuré correctement. Configurez votre pare-feu vidéo basée sur les normes de traversée du réseau de périmètre prendre en charge. Par exemple : 
    - Cisco VCS-e                  
    - RPAD de Polycom

3. Configuration des salles intégrées avec exchange et OTD. Dans la plupart des cas, relais supplémentaires devra être configurée et configurées dans votre environnement.


## <a name="provision"></a>Mise en service
 
La clé client seront les appels sortants vers le service partenaire. Dans l’exemple suivant, 813878896@t.plcm.vc est la clé de client. 

![Exemple de clé de client](media/tenant-key-example.png) 

Vous devrez exécuter les applets de commande suivantes pour configurer la clé client et permettent également aux utilisateurs de sélectionner ou toute l’organisation créer des réunions avec des coordonnées interopérabilitées vidéo.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft propose construit à partir des stratégies pour chacun des partenaires pris en charge qui vous permettent de désigner les partenaires qui à utiliser pour l’interopérabilité vidéo dans le nuage.

    Cette cmdlet vous permet d’identifier les construit à partir des stratégies que vous pouvez utiliser dans votre organisation. Vous pouvez assigner cette stratégie à un ou plusieurs de vos utilisateurs de tirer parti de l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** L’applet de commande Grant-CsTeamsVideoInteropServicePolicy permet d’affecter une stratégie construite préalable pour une utilisation dans votre organisation ou la stratégie à des utilisateurs spécifiques.
 
- ** [Nouveau CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Le nouveau-CsVideoInteropServiceProvider permet de spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Utiliser la Set-CsVideoInteropServiceProvider pour mettre à jour des informations sur un partenaire CVI pris en charge que votre organisation utilise.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenir tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Remove-CsVideoInteropServiceProvider permet de supprimer toutes les informations fournisseur sur un fournisseur que votre organisation n’utilise plus.  
 
## <a name="consent"></a>Consentement de l’utilisateur

Vous devrez fournir le consentement de l’autorisation pour les périphériques de téléconférence vidéo (VTCs) à participer à des réunions de votre organisation via le service partenaire. Ce lien consentement est fourni par votre partenaire.  
 
Une fois ces étapes terminées, les utilisateurs qui sont activés de façon individuelle par le biais de l’applet de commande Grant au-dessus ou tous les utilisateurs dans l’organisation si le client est activé, a VTC coordonnées dans toutes les réunions d’équipes qu’ils planifient. N’importe quel VTC peut participer à ces réunions via ces coordonnées.


|Nom|Courte Description d’autorisation d’application| Description|
|--|--|---|
|Calls.JoinGroupCall.All|Rejoindre des réunions et appels de groupe en tant qu’une application (preview)|Permet à l’application participer à des réunions planifiées et les appels de groupe dans votre organisation, sans qu’un utilisateur connecté.  L’application s’être joint avec les privilèges d’un utilisateur de l’annuaire à des réunions dans votre client.|
|Calls.JoinGroupCallasGuest.All|Participer à des réunions et appels de groupe en tant qu’invité (preview)|Permet à l’application à se joindre à des réunions planifiées et les appels de groupe dans votre organisation, sans qu’un utilisateur connecté.  L’application sera joint en tant qu’invité à des réunions dans votre client.|
|Calls.AccessMedia.All|Flux de données Access dans un appel en tant qu’une application (preview)|Permet à l’application d’accéder directement à des flux de données dans un appel, sans qu’un utilisateur connecté.|
|OnlineMeetings.Read.All|Détails d’une réunion en ligne en lecture (preview)|Permet à l’application afficher les détails de réunion en ligne dans votre organisation, sans qu’un utilisateur connecté.|

## <a name="schedule"></a>Planification

Ensuite, planifier les équipes réunion avec vidéo coordonnées PIA. L’utilisateur activé peut planifier des équipes réunions via :
- [Des équipes de complément de conférence pour Outlook](teams-add-in-for-outlook.md)
- Client équipes mobile et de bureau


## <a name="join"></a>Rejoindre

Vous pouvez joindre des réunions d’équipes avec vos périphériques VTC comme suit :
 
- IVR (réponse vocale Interactive)
    - Vous pouvez vous connecter à réponse vocale interactive du partenaire à l’aide de la tenantkey@domain. 
    - Une fois que vous êtes dans le partenaire de réponse vocale interactive, vous serez invité à entrer le conferenceId VTC, qui se connectera ensuite à la réunion équipes.
- Appel direct
    - Vous pouvez directement joindre la réunion équipes sans interaction avec interactive le partenaire à l’aide de la fonctionnalité de numérotation directe à l’aide de la chaîne complète de tenantkey. VTC ConferenceId@domain.
- Numérotation des touches de raccourci
    - Si vous disposez d’une salle équipes intégrée, vous pouvez utiliser une touche numérotation fonctionnalités offertes par votre partenaire (sans avoir à taper n’importe quelle chaîne de numérotation).

Enfin, vous collaborez avec les utilisateurs des équipes dans vos réunions en utilisant le partage audio, vidéo et de contenu. 