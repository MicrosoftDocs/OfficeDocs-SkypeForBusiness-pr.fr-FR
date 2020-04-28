---
title: Interopérabilité de la vidéo cloud de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Utiliser le Cloud Video Interop comme solution intermédiaire pour permettre à des appareils de salle de réunion tiers de participer à des réunions Microsoft Teams.
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c7cb1888856ff8dba910e4f4735516876a8ade2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905876"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité de la vidéo cloud de Microsoft Teams

Le Cloud Video Interop (CVI) est une solution tierce qualifiée par Microsoft qui permet d’accéder à des salles de réunion ou des appareils vidéo personnels (VTCs) tiers pour participer à des réunions dans Microsoft Teams.
 
Grâce à Microsoft Teams, vous bénéficiez d’une collaboration sur le contenu en ligne riche dans les réunions qui incluent l’audio, la vidéo et le partage de contenu. Cela peut être apprécié par le biais du client de bureau et Web, ainsi que par le biais de nombreux appareils partenaires qui s’intègrent en mode natif avec Microsoft Teams. En revanche, de nombreux clients ont déjà investi dans des périphériques de communication vidéo et de visioconférence personnels, ce qui peut être coûteux à mettre à niveau. La technologie Cloud Video Interop fournit une solution simple, qui vous permet de continuer à utiliser vos solutions actuelles tant que vous n’êtes pas prêt à effectuer la mise à niveau.

Avec la fonction d’interopérabilité de la vidéo Cloud, Microsoft teams permet à tous les participants de bénéficier d’une interface de réunion native pour tous les participants :

### <a name="is-cloud-video-interop-for-me"></a>Est-ce que Cloud Video Interop pour moi ?

La technologie Cloud Video Interop fournit un service intermédiaire lors d’une transition vers une solution Microsoft teams native complète, utilisant des points de terminaison Teams. Le service fourni doit faire partie de votre chemin de migration.

L’interopérabilité de la vidéo Cloud est destiné aux clients qui remplissent les critères suivants :

- Déploiement de systèmes de salle de réunion et de déploiement de périphériques vidéo personnels (50 périphériques) qui ne sont pas qualifiés pour une intégration directe avec Microsoft teams
- Sont prises en charge par l’un de nos partenaires d’interopérabilité Cloud Video
- Vous souhaitez conserver la valeur de leur investissement dans ses appareils de salle de réunion actuels et périphériques vidéo personnels lors de la migration vers une solution Microsoft teams Native

Même si la technologie Cloud Video Interop fournit une solution de grande qualité, nous encourageons nos clients à consulter les solutions de réunion natives de nos équipes, telles que les systèmes de salle de réunion, pour le long terme. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 secteur public et services tiers

Office 365 offre la possibilité d’intégrer des applications tierces dans les sites SharePoint Online, Skype entreprise, équipes et applications Office incluses dans les applications Microsoft 365 pour les entreprises (par exemple, Word, Excel, PowerPoint et Outlook) et Outlook Web App. Par ailleurs, Office 365 prend en charge l’intégration avec des fournisseurs de services tiers. Ces services et applications tiers peuvent impliquer le stockage, la transmission et le traitement des données client de votre organisation sur des systèmes tiers situés en dehors de l’infrastructure 365 d’Office et ne sont donc pas soumis aux engagements en matière de conformité et de protection des données d’Office 365. **Nous vous recommandons de consulter les déclarations de confidentialité et de conformité fournies par les tiers lors de l’évaluation de l’utilisation appropriée de ces services pour votre organisation.**



### <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour Microsoft teams

Les partenaires suivants disposent de solutions d’interopérabilité vidéo pour Microsoft Teams. Votre entreprise est susceptible de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 

|Partenaire|Solution de partenariat|
|----|---|
|![Logo représentant Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Service RealConnect Polycom</a> |
|![Logo représentant l’infini de PEXIP](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">PEXIP Infinity pour Microsoft teams</a> | 
|![Logo représentant la passerelle BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Passerelle BlueJeans pour Microsoft teams</a> |

### <a name="cloud-video-interop-overview"></a>Vue d’ensemble de l’interopérabilité Cloud Video

L’interopérabilité de la vidéo Cloud est un service tiers offert par nos partenaires pour assurer l’interopérabilité entre les solutions de conférence vidéo existantes et les solutions de périphériques vidéo personnels en local et Microsoft Teams.

Les solutions proposées par nos partenaires sont composées de composants qui peuvent être déployés entièrement sur le Cloud ou partiellement ou entièrement sur site. 
     
Le diagramme suivant illustre l’architecture de haut niveau de nos solutions de partenariat.

![Diagramme décrivant une solution de partenariat Cloud Video Interop](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Déploiement de l’interopérabilité Cloud Video

Lors du déploiement d’une solution d’interopérabilité Cloud Video, il est important de comprendre que vous déployez une solution de partenariat. Le diagramme suivant décrit les étapes générales nécessaires pour déployer la technologie Cloud.

![Diagramme décrivant le déploiement d’CVI au sein de votre organisation](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Pendant la phase du plan, vous devez identifier les appareils que vous ne devez pas remplacer par un appareil teams natif et Rechercher un partenaire d’interopérabilité Cloud qui peut prendre en charge ces appareils.  

Il est également important de savoir que vous aurez besoin d’une licence pour chaque utilisateur qui planifie les réunions dans lesquelles vous voulez qu’un périphérique compatible avec la vidéo Cloud puisse y accéder. Notez qu’il est possible d’obtenir exactement les exigences de licence du partenaire Cloud Video Interop. Assurez-vous qu’il est clair avant de commencer votre déploiement.

### <a name="configure"></a>Configuration

Le partenaire que vous avez choisi pour votre déploiement CVI vous fournira un document de déploiement complet composé de toutes les étapes nécessaires au déploiement réussi au sein de votre organisation. Cela inclut les ports de pare-feu et les plages d’adresses IP, les modifications de configuration pour vos appareils et d’autres paramètres qui doivent changer.

### <a name="provision"></a>Octroi  

Pendant la phase de mise en service, vous attribuerez des licences aux utilisateurs appropriés conformément au Guide de configuration du partenaire. Vous devrez également suivre le processus de consentement d’Azure pour proposer au partenaire l’accès à votre environnement d’équipes. Pour plus d’informations sur le processus de consentement d’Azure, voir [autorisations et consentement dans le point de terminaison de la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) .

### <a name="schedule"></a>Horaire

Lorsqu’un utilisateur est activé pour l’interopérabilité de la vidéo Cloud, toute réunion planifiée à l’aide du complément réunion teams pour Outlook ou du client teams disposera des informations supplémentaires appropriées automatiquement ajoutées à la réunion Teams, afin que les appareils compatibles avec la vidéo Cloud puissent participer à ces réunions.

### <a name="join"></a>Rejoindre

En fonction de la solution de partenariat, il existe plusieurs façons de participer à une réunion Cloud Video Interop. Les scénarios exacts de participation à une réunion seront fournis par votre partenaire Cloud Video Interop. Nous avons classé quelques exemples ci-dessous :

- IVR (réponse vocale interactive) 
  - Vous pouvez vous connecter à l’IVR du partenaire à l’aide du tenantkey@domain.
  - Lorsque vous vous trouvez dans l’IVR du partenaire, vous êtes invité à entrer le conferenceId VTC, qui vous connecte ensuite à la réunion Teams.
- Numérotation directe 
  - Vous pouvez directement composer le numéro de la réunion teams sans interagir avec l’IVR du partenaire à l’aide de la fonction de numérotation directe, en utilisant la chaîne complète de tenantkey. VTC ConferenceId@domain.
- Numérotation en un clic 
  - Si vous avez une salle d’équipe intégrée, vous pouvez utiliser les fonctionnalités de numérotation à l’aide de votre partenaire (sans avoir à taper une chaîne de numérotation).

## <a name="manage-cloud-video-interop"></a>Gérer l’interopérabilité Cloud Video

Après le déploiement de l’interopérabilité de la vidéo Cloud, vous pouvez gérer les appareils à l’aide des solutions fournies par nos partenaires. Chaque partenaire vous fournira une interface d’administration qui inclura la gestion des licences et des appareils. 

La création de rapports est également disponible directement à partir de l’interface d’administration du partenaire. Pour en savoir plus sur les fonctionnalités de création de rapports, contactez le partenaire de votre choix. 

### <a name="troubleshooting-cloud-video-interop"></a>Résolution des problèmes liés à l’interopérabilité Cloud Video

La technologie Cloud Video Interop est un service fourni par les partenaires. Si vous rencontrez des problèmes, la première étape consiste à connecter un appareil sur lequel le client teams a été installé et à le connecter au même segment que le périphérique Cloud Video Interop qui cause des problèmes. 

Si teams fonctionne correctement sur ce segment et que vous avez également suivi toutes les instructions de mise en réseau et de configuration fournies par le partenaire, vous devez contacter ce dernier pour résoudre les problèmes. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell pour l’interopérabilité vidéo Cloud

Les applets de commande PowerShell suivantes sont disponibles pour vous pour (partiellement) automatiser le déploiement d’interopérabilité de la vidéo Cloud.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft fournit des stratégies préconçues pour chacun de nos partenaires pris en charge, qui vous permettent de désigner le ou les partenaires à utiliser pour l’interopérabilité de la vidéo Cloud.<br>Cette applet de connexion vous permet d’identifier les politiques prédéfinies que vous pouvez utiliser au sein de votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de passe Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: cette applet de connexion vous permet d’assigner une stratégie préconçue pour une utilisation au sein de votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.
- **New-CsVideoInteropServiceProvider**: cette applet de cmdlet permet de spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
- **Set-CsVideoInteropServiceProvider**: utilisez cette applet de cmdlet pour mettre à jour des informations sur un partenaire CVI pris en charge utilisé par votre organisation.
- **Get-CsVideoInteropServiceProvider**: utilisez cette applet de cmdlet pour obtenir tous les fournisseurs configurés pour une utilisation au sein de l’organisation.
- **Remove-CsVideoInteropServiceProvider**: cette applet de passe permet de supprimer toutes les informations de fournisseur relatives à un fournisseur que votre organisation n’utilise plus.
