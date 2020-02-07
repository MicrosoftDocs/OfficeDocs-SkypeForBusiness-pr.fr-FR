---
title: Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Cet article décrit la planification et la configuration de l’interopérabilité Cloud Video pour les utilisateurs de votre organisation.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e937e7825000d02156c1f5ede2671711006cbdd
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825102"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Mise en place de l’interopérabilité de la vidéo cloud de Microsoft Teams

Une fois que vous avez [choisi votre ou vos partenaires d’interopérabilité Cloud Video](cloud-video-interop.md), vous devez planifier votre déploiement, se familiariser avec les détails de mise en service et la clé de client partenaire et consent à l’application d’interopérabilité vidéo au sein de votre organisation. Le schéma suivant décrit le processus. 

![Déploiement d’CVI au sein de votre organisation](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Pour plus d’informations sur l’identification d’un partenaire ou partenaire à utiliser au sein de votre organisation, voir [interopérabilité Cloud pour Microsoft teams](cloud-video-interop.md) . 

Pour planifier l’activation basée sur le niveau d’utilisation/le site, procédez comme suit : 

- Sélectionner un modèle de déploiement/un modèle hébergé pour votre utilisation
- Sélectionnez le plan de licence idéal pour votre organisation. 
- Vous pouvez planifier la capacité des VM pour votre infrastructure vidéo.

## <a name="configure"></a>Configuration 

Pour configurer le Cloud Video Interop, procédez comme suit. 

1. Obtenez les informations de configuration des partenaires/partenaires que vous avez choisis (clé de client, AppID...). Vous pouvez utiliser un ou plusieurs partenaires d’interopérabilité vidéo au sein de votre organisation. 

2. Assurez-vous que votre réseau est configuré correctement. Configurez votre pare-feu vidéo standard pour la prise en charge du réseau de périmètre. Par exemple : 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurez les salles intégrées avec Exchange et OTD. Dans la plupart des cas, il est nécessaire de configurer et de configurer un relais supplémentaire dans votre environnement.


## <a name="provision"></a>Octroi
 
La clé de locataire sera le numéro de connexion au service partenaire. Dans l’exemple suivant, 813878896@t.plcm.vc est la clé de client. 

![Exemple de clé de client](media/tenant-key-example.png) 

Vous devez exécuter les applets de commande suivantes pour mettre en service la clé de client et permettre à certains utilisateurs ou à votre organisation de créer des réunions avec des coordonnées d’interopérabilité vidéo.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft fournit des stratégies préconçues pour chacun de nos partenaires pris en charge, qui vous permettent de désigner le ou les partenaires à utiliser pour l’interopérabilité de la vidéo Cloud.

    Cette applet de connexion vous permet d’identifier les politiques prédéfinies que vous pouvez utiliser au sein de votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de passe Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** L’applet de connexion Grant-CsTeamsVideoInteropServicePolicy vous permet d’affecter une stratégie prédéfinie à utiliser au sein de votre organisation ou de l’affecter à des utilisateurs spécifiques.
 
- ** [Nouveau-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Utilisez le nouveau-CsVideoInteropServiceProvider pour spécifier les informations relatives à un partenaire CVI pris en charge que votre organisation souhaite utiliser.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Utilisez la CsVideoInteropServiceProvider pour mettre à jour les informations relatives à un partenaire CVI pris en charge que votre organisation utilise.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenir tous les fournisseurs configurés pour une utilisation au sein de l’organisation.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Utilisez Remove-CsVideoInteropServiceProvider pour supprimer toutes les informations de fournisseur relatives à un fournisseur que votre organisation n’utilise plus.  
 
## <a name="consent"></a>Consentement

Vous devez fournir le consentement d’autorisation pour les appareils de visioconférence vidéo (VTCs) pour rejoindre les réunions de votre organisation via le service partenaire. Ce lien de consentement sera également fourni par votre partenaire.  
 
Une fois ces étapes terminées, les utilisateurs qui sont activés individuellement par le biais de l’applet de contrôle Grant ci-dessus, ou tous les utilisateurs de l’organisation si le client est activé, auront des coordonnées VTC dans toutes les réunions teams qu’ils emploient. Tout VTC peut rejoindre ces réunions par le biais de ces coordonnées.


|Nom|Brève description de l’autorisation d’application| Description|
|--|--|---|
|Appels. JoinGroupCall. All|Joindre des appels de groupe et des réunions en tant qu’application (Preview)|Autorise l’application à rejoindre les appels de groupe et les réunions planifiées au sein de votre organisation, sans utilisateur connecté.  L’application sera associée aux privilèges d’un utilisateur d’annuaire pour les réunions de votre client.|
|Appels. JoinGroupCallasGuest. All|Joindre des appels de groupe et des réunions en tant qu’utilisateur invité (Preview)|Permet à l’application de joindre anonymement des appels de groupe et des réunions planifiées au sein de votre organisation, sans utilisateur connecté.  L’application sera associée en tant qu’invité à des réunions de votre client.|
|Appels. AccessMedia. All|Accéder aux flux multimédias dans un appel en tant qu’application (Preview)|Autorise l’application à accéder directement aux flux multimédias pendant un appel, sans utilisateur connecté.|
|OnlineMeetings. Read. All|Lire les détails d’une réunion en ligne (Preview)|Permet à l’application de lire les détails d’une réunion en ligne au sein de votre organisation, sans utilisateur connecté.|

## <a name="schedule"></a>Horaire

Ensuite, planifiez une réunion en équipe avec des coordonnées d’interopérabilité vidéo. L’utilisateur activé peut planifier des réunions d’équipes par le biais de :
- [Complément réunion teams pour Outlook](teams-add-in-for-outlook.md)
- Bureau et appareil mobile teams


## <a name="join"></a>Rejoindre

Vous pouvez participer à des réunions d’équipes à l’aide de vos appareils VTC comme suit :
 
- IVR (réponse vocale interactive)
    - Vous pouvez vous connecter à l’IVR du partenaire à l’aide du tenantkey@domain. 
    - Une fois que vous avez été dans le partenaire IVR, vous êtes invité à entrer le conferenceId VTC, qui vous connecte ensuite à la réunion Teams.
- Numérotation directe
    - Vous pouvez accéder directement à la réunion teams sans interagir avec le son de votre partenaire à l’aide de la fonction de numérotation directe qui utilise la chaîne complète de tenantkey. VTC ConferenceId@domain.
- Numérotation en un clic
    - Si vous avez une salle d’équipe intégrée, vous pouvez utiliser les fonctionnalités de numérotation à l’aide de votre partenaire (sans avoir à taper une chaîne de numérotation).

Enfin, vous collaborez avec les utilisateurs de teams dans vos réunions à l’aide du son, de la vidéo et du partage de contenu. 
