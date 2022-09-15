---
title: Interopérabilité de la vidéo cloud de Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Utilisez Cloud Video Interop comme solution intermédiaire pour permettre aux appareils de salle de réunion tiers de participer à des réunions Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c732cc01a525a4895fafe45c954c965fe960853
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706451"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité de la vidéo cloud de Microsoft Teams

Cloud Video Interop (CVI) est une solution tierce qualifiée Microsoft qui permet aux salles de réunion tierces (téléprésence) et aux périphériques vidéo personnels (VTC) de participer à des réunions Microsoft Teams.
 
Avec Microsoft Teams, vous bénéficiez d’une collaboration riche en contenu en ligne dans les réunions qui incluent le partage audio, vidéo et de contenu. Cela peut être apprécié via le client de bureau et web, ainsi que par le biais de nombreux appareils partenaires qui s’intègrent en mode natif à Microsoft Teams. Toutefois, de nombreux clients ont déjà investi dans la téléconférence vidéo et les appareils de communication vidéo personnels, ce qui peut être coûteux à mettre à niveau. Cloud Video Interop fournit une solution simple, qui vous permet de continuer à utiliser vos solutions existantes jusqu’à ce que vous soyez prêt à effectuer la mise à niveau.

Avec Cloud Video Interop, Microsoft Teams offre une expérience de réunion native pour tous les participants , dans les salles de réunion ou à l’intérieur des clients Teams.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop est-il pour moi ?

Cloud Video Interop fournit un service intermédiaire pendant la transition vers une solution Microsoft Teams native complète, à l’aide de points de terminaison Teams. Le service fourni doit faire partie de votre chemin de migration.

Cloud Video Interop est destiné aux clients qui répondent aux critères suivants :

- Disposer d’un déploiement important d’appareils de salle de réunion et d’appareils vidéo personnels (plus de 50 appareils) qui ne sont pas qualifiés pour une intégration directe avec Microsoft Teams
- Sont pris en charge par l’un de nos partenaires Cloud Video Interop
- Vous souhaitez conserver la valeur de leur investissement dans leurs appareils de salle de réunion actuels et leurs périphériques vidéo personnels pendant la migration vers une solution Microsoft Teams native

Bien que Cloud Video Interop offre une excellente solution intermédiaire, nous encourageons nos clients à examiner nos solutions de réunion Teams natives, telles que les systèmes de salle Teams, à long terme. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 services du gouvernement des États-Unis et de tiers

Office 365 permet d’intégrer des applications tierces dans des sites SharePoint Online, Skype Entreprise, Teams, des applications Office incluses dans Applications Microsoft 365 pour les grandes entreprises (telles que Word, Excel, PowerPoint et Outlook) et Outlook Web App. En outre, Office 365 prend en charge l’intégration avec des fournisseurs de services tiers. Ces applications et services tiers peuvent impliquer le stockage, la transmission et le traitement des données client de votre organisation sur des systèmes tiers qui ne font pas partie de l’infrastructure Office 365 et ne sont donc pas couverts par les engagements de conformité et de protection des données Office 365. **Il est recommandé d’examiner les déclarations de confidentialité et de conformité fournies par les tiers lors de l’évaluation de l’utilisation appropriée de ces services pour votre organisation.**



### <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour Microsoft Teams

Les partenaires suivants disposent de solutions d’interopérabilité vidéo pour Microsoft Teams. Votre entreprise peut choisir de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 

|Partenaire|Solution partenaire|
|----|---|
|![Logo représentant Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![Logo représentant Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity pour Microsoft Teams</a> | 
|![Logo représentant la passerelle BlueJeans.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Passerelle BlueJeans pour Microsoft Teams</a> |
|![Logo représentant Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration pour Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Vue d’ensemble de Cloud Video Interop

Cloud Video Interop est un service tiers proposé par nos partenaires pour fournir une interopérabilité entre les solutions de vidéoconférence existantes et les solutions d’appareils vidéo personnels en local et Microsoft Teams.

Les solutions offertes par nos partenaires se composent de composants qui peuvent être déployés entièrement dans le cloud ou partiellement/entièrement en local. 
     
Le diagramme suivant illustre l’architecture générale de nos solutions partenaires.

![Diagramme décrivant une solution de partenaire Teams Cloud Video Interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Déployer Cloud Video Interop

Lors du déploiement d’une solution Cloud Video Interop, il est important de comprendre que vous déployez une solution partenaire. Les étapes générales à suivre pour déployer Cloud Video Interop sont répertoriées dans le diagramme suivant.

![Diagramme décrivant le déploiement de l’interface CVI dans votre organisation.](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Pendant la phase de plan, vous devez identifier les appareils que vous ne remplacerez pas par un appareil Teams natif et rechercher un partenaire Cloud Video Interop capable de prendre en charge ces appareils.  

Il est également important de comprendre que vous aurez besoin d’une licence pour chaque utilisateur qui planifiera des réunions auxquelles vous souhaitez qu’un appareil compatible Cloud Video Interop soit joint. Notez que les exigences de licence exactes peuvent être obtenues auprès du partenaire Cloud Video Interop. Assurez-vous que cela est clair avant de commencer votre déploiement.

### <a name="configure"></a>Configuration

Le partenaire que vous avez choisi pour votre déploiement CVI vous fournira un document de déploiement complet qui comprend toutes les étapes nécessaires pour déployer correctement au sein de votre organisation. Cela inclut les ports de pare-feu et les plages d’adresses IP, les modifications de configuration de vos appareils et d’autres paramètres qui doivent être modifiés.

### <a name="provision"></a>Disposition  

Pendant la phase de provisionnement, vous allez attribuer des licences aux utilisateurs appropriés conformément au guide de configuration du partenaire. Vous devez également passer par le processus de consentement Azure pour fournir au partenaire l’accès à votre environnement Teams. Pour plus d’informations sur le processus de consentement Azure, consultez [Autorisations et consentement dans le point](/azure/active-directory/develop/v2-permissions-and-consent) de terminaison Plateforme d'identités Microsoft.

### <a name="schedule"></a>Horaire

Une fois qu’un utilisateur est activé pour Cloud Video Interop, toute réunion planifiée à l’aide du complément de réunion Teams pour Outlook ou du client Teams dispose des informations supplémentaires appropriées automatiquement ajoutées à la réunion Teams afin que les appareils compatibles avec Cloud Video Interop puissent participer à ces réunions.

### <a name="join"></a>Rejoindre

Selon la solution partenaire, il existe plusieurs façons de participer à une réunion compatible Avec Cloud Video Interop. Les scénarios exacts de participation à une réunion seront fournis par votre partenaire Cloud Video Interop. Nous avons répertorié quelques exemples ci-dessous :

- IVR (Interactive Voice Response) 
  - Vous pouvez vous connecter à l’IVR du partenaire à l’aide de la tenantkey@domain.
  - Lorsque vous êtes dans l’IVR partenaire, vous êtes invité à entrer l’ID de conférence VTC, qui vous connectera ensuite à la réunion Teams.
- Direct 
  - Vous pouvez vous connecter directement à la réunion Teams sans interagir avec l’IVR du partenaire à l’aide de la fonctionnalité de numérotation directe, à l’aide de la chaîne complète de clé de locataire. ConferenceId@domain VTC.
- Numérotation à une seule touche 
  - Si vous disposez d’une salle Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation tactile offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).

## <a name="manage-cloud-video-interop"></a>Gérer Cloud Video Interop

Une fois Cloud Video Interop déployé, vous pouvez gérer les appareils à l’aide des solutions fournies par nos partenaires. Chaque partenaire vous fournira une interface d’administration qui inclura à la fois la gestion des licences et des appareils. 

Les rapports sont également disponibles directement à partir de l’interface d’administration du partenaire. Pour plus d’informations sur les fonctionnalités de création de rapports, contactez le partenaire de votre choix. 

### <a name="troubleshooting-cloud-video-interop"></a>Résolution des problèmes liés à Cloud Video Interop

Cloud Video Interop est un service fourni par un partenaire. Si vous rencontrez des problèmes, la première étape consiste à connecter un appareil sur lequel le client Teams est installé et à le connecter au même segment que l’appareil Cloud Video Interop qui provoque des problèmes. 

Si Teams fonctionne correctement sur ce segment et que vous avez également suivi toutes les instructions de mise en réseau et de configuration fournies par le partenaire, vous devez contacter le partenaire pour une résolution des problèmes supplémentaire. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell pour Cloud Video Interop

Les applets de commande PowerShell suivantes sont disponibles pour vous permettre d’automatiser (partiellement) le déploiement Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy** : Microsoft fournit des stratégies pré-construites pour chacun de nos partenaires pris en charge qui vous permettent de désigner les partenaires à utiliser pour Cloud Video Interop.<br>Cette applet de commande vous permet d’identifier les stratégies pré-construites que vous pouvez utiliser dans votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy** : cette applet de commande vous permet d’attribuer une stratégie prédéfini à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.
- **New-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
- **Set-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour mettre à jour les informations sur un partenaire CVI pris en charge que votre organisation utilise.
- **Get-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour obtenir tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.
- **Remove-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour supprimer toutes les informations du fournisseur sur un fournisseur que votre organisation n’utilise plus.