---
title: Interopérabilité de la vidéo cloud de Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Nuage vidéo Interop permet de tiers équipements de salle pour participer à des réunions Teams Microsoft de la réunion.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ea1a81f2418b17d247dafe82d9e94e348d3b4c7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459747"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité de la vidéo cloud de Microsoft Teams

Nuage vidéo Interop (CVI) est une solution tierce Qualified Microsoft qui permet de salles de réunion de tiers (TÉLÉPRÉSENCE) et les périphériques vidéo personnels (VTCs) à participer à des réunions Teams Microsoft.
 
Avec Microsoft Teams, vous obtenez riche collaboration de contenu en ligne dans les réunions qui incluent le partage audio, vidéo et de contenu. Cela revisité via le client web et de bureau, ainsi que par le biais de nombreux périphériques partenaire qui intègrent en mode natif Microsoft Teams. Toutefois, de nombreux clients ont déjà investi dans téléconférence vidéo et les périphériques de communication vidéo personnel, qui peuvent être coûteux en termes de mise à niveau. Nuage vidéo Interop fournit une solution simple, ce qui vous permet de continuer à utiliser vos solutions existantes jusqu'à ce que vous êtes prêt à mettre à niveau.

Avec le nuage vidéo Interop, Teams Microsoft offre une expérience de réunion natif pour tous les participants – dans les salles de réunion ou à l’intérieur clients équipes.

### <a name="is-cloud-video-interop-for-me"></a>Est une interopérabilité vidéo Cloud pour moi ?

Nuage vidéo Interop fournit un service intermédiaire pendant la transition d’une Solution d’équipes Microsoft native complète, à l’aide de points de terminaison équipes. Le service fourni doit faire partie de votre chemin de migration.

Nuage vidéo Interop est destiné aux clients qui répondent aux critères suivants :

- Un grand déploiement de périphériques de la salle de réunion et le déploiement de périphériques vidéo personnels (50 + appareils) qui ne sont pas qualifiés pour l’intégration directe avec Microsoft Teams
- Sont pris en charge par un des partenaires de nuage vidéo Interop
- Pour conserver la valeur de leurs investissements dans leurs en cours de la réunion pendant la migration vers une solution Microsoft Teams native périphériques de salle et vidéo personnels

Nuage vidéo Interop fournit une excellente solution intermédiaire, nous conseillons de nos clients de consulter nos solutions équipes réunion natives, tels que les systèmes de salle d’équipes, à long terme. 

### <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour les équipes Microsoft

Les partenaires suivants ont des solutions d’interopérabilité vidéo pour Microsoft Teams. Votre société peut choisir de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 

|Partenaire|Solution d’un partenaire|
|----|---|
|![RealConnect de Polycom](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Service RealConnect de Polycom</a> |
|![Infini Pexip](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Infini Pexip pour les équipes Microsoft</a> | 
|![Passerelle blueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Passerelle blueJeans pour les équipes Microsoft</a> |

### <a name="cloud-video-interop-overview"></a>Vue d’ensemble de nuage interopérabilité vidéo

Interopérabilité vidéo cloud est un service de tiers qui est fourni par les partenaires pour assurer l’interopérabilité entre visioconférence existant et les solutions de périphérique vidéo personnel sur site et Microsoft Teams.

Les solutions de partenaires se composent des composants qui peuvent être déployés, entièrement dans le nuage en partiellement/entièrement ou sur site. 
     
Le diagramme suivant illustre l’architecture de haut niveau de nos partenaires de solutions.

![Solution d’un partenaire en nuage vidéo Interop équipes](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Déployer l’interopérabilité vidéo sur le nuage

Lorsque vous déployez une solution de nuage vidéo Interop, il est important de comprendre que vous déployez une solution d’un partenaire. Les étapes générales à suivre pour déployer une interopérabilité vidéo nuage sont répertoriés dans le diagramme suivant.

![Déploiement CVI dans votre organisation](media/deploying-cvi.png)

### <a name="plan"></a>Planifier

Pendant la phase de planification, vous devez identifier les périphériques ne seront pas remplacer par un périphérique équipes natif et de trouver un partenaire de nuage vidéo Interop pouvant prendre en charge ces périphériques.  

Il est également important de comprendre que vous aurez besoin d’une licence pour chaque utilisateur qui planifie dans lequel vous souhaitez qu’un périphérique prenant en charge une interopérabilité vidéo Cloud pour participer à des réunions. Notez qu’exactes critères de licences peuvent être obtenus à partir du partenaire de nuage vidéo Interop. Assurez-vous qu’il s’agit effacer avant de commencer votre déploiement.

### <a name="configure"></a>Configuration

Le partenaire que vous avez choisi pour votre déploiement CVI vous fournira un document de déploiement complet qui se compose de toutes les étapes nécessaires pour déployer avec succès au sein de votre organisation. Cela inclut les ports de pare-feu et les plages d’adresses IP, les modifications de configuration de vos périphériques et d’autres paramètres qui doivent être modifiés.

### <a name="provision"></a>Mise en service  

Pendant la phase de mise en service, vous allez attribuer des licences aux utilisateurs appropriés en fonction du partenaire guide de configuration. Vous devez également suivre le processus de consentement Azure pour fournir l’accès des partenaires à votre environnement d’équipes. Vous trouverez ici des plus d’informations sur le processus de consentement Azure :https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Planification

Après un utilisateur est activé pour l’interopérabilité de vidéo sur le nuage, une réunion planifiée à l’aide soit la réunion équipes complément pour Outlook ou le Client équipes contient les informations supplémentaires appropriées automatiquement ajoutées dans les équipes de réunion ainsi que la vidéo sur le nuage Appareils compatibles Interop peuvent participer à ces réunions.

### <a name="join"></a>Rejoindre

Selon la solution partenaire, il existe plusieurs façons de joindre une réunion prenant en charge une interopérabilité vidéo dans le nuage. Exacte de participation aux réunions scénarios seront fournies par votre partenaire de nuage vidéo Interop. Nous vous proposons ci-dessous quelques exemples ci-dessous :

- IVR (réponse vocale Interactive) 
  - Vous pouvez vous connecter à réponse vocale interactive du partenaire à l’aide de la tenantkey@domain.
  - Lorsque vous êtes dans le partenaire de réponse vocale interactive, vous invitera à entrer le conferenceId VTC, qui se connectera ensuite à la réunion équipes.
- Appel direct 
  - Vous pouvez directement vous connecter à la réunion d’équipes sans interaction avec interactive le partenaire à l’aide de la fonctionnalité d’appel direct, à l’aide de la chaîne complète de tenantkey. VTC ConferenceId@domain.
- Numérotation des touches de raccourci 
  - Si vous disposez d’une salle équipes intégrée, vous pouvez utiliser une touche numérotation fonctionnalités offertes par votre partenaire (sans avoir à taper n’importe quelle chaîne de numérotation).

## <a name="manage-cloud-video-interop"></a>Gérer l’interopérabilité vidéo sur le nuage

Après avoir déployé une interopérabilité vidéo sur le nuage, vous pouvez gérer les périphériques en utilisant les solutions fournies par les partenaires. Chaque partenaire vous fournira une interface d’administration qui inclut la gestion des licences et de périphérique. 

Création de rapports est également disponible directement à partir de l’interface d’administration partenaires. Pour plus d’informations sur les fonctionnalités de création de rapports, contactez le partenaire de votre choix. 

### <a name="troubleshooting-cloud-video-interop"></a>Résolution des problèmes d’interopérabilité vidéo sur le nuage

Nuage vidéo Interop est un service fournis par les partenaires. Si vous rencontrez des problèmes, la première étape consiste à se connecter à un périphérique qui a installé le Client équipes et se connecter à un même segment comme périphérique Cloud vidéo Interop qui pose problème. 

Si les fonctions des équipes correctement sur ce segment et que vous ont suivi également toutes les instructions de mise en réseau et de configuration que du partenaire a fourni, vous devrez contacter le partenaire de dépannage. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell pour l’interopérabilité vidéo sur le nuage

Les applets de commande PowerShell suivantes sont disponibles pour vous (partiellement) automatiser le déploiement de Cloud vidéo Interop.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft propose construit à partir des stratégies pour chacun des partenaires pris en charge qui vous permettent de désigner les partenaires à utiliser pour l’interopérabilité de vidéo sur le nuage.<br>Cette cmdlet vous permet d’identifier les construit à partir des stratégies que vous pouvez utiliser dans votre organisation. Vous pouvez assigner cette stratégie à un ou plusieurs de vos utilisateurs grâce à l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: cette applet de commande permet d’affecter une stratégie construite préalable pour une utilisation dans votre organisation ou la stratégie à des utilisateurs spécifiques.
- **New-CsVideoInteropServiceProvider**: permet de spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser cette applet de commande.
- **Set-CsVideoInteropServiceProvider**: utilisez cette applet de commande pour mettre à jour des informations sur un partenaire CVI pris en charge par votre organisation.
- **Get-CsVideoInteropServiceProvider**: utilisez cette applet de commande pour obtenir tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.
- **Remove-CsVideoInteropServiceProvider**: utilisez cette applet de commande pour supprimer toutes les informations fournisseur sur un fournisseur que votre organisation n’utilise plus.
