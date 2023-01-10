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
ms.openlocfilehash: 37201c788618da1544d4f00b743907dc22ff6366
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749010"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité de la vidéo cloud de Microsoft Teams

Cloud Video Interop (CVI) est une solution tierce qualifiée par Microsoft qui permet aux salles de réunion tierces (téléprésence) et aux appareils vidéo personnels (VTC) de participer à des réunions Microsoft Teams.
 
Avec Microsoft Teams, vous bénéficiez d’une collaboration riche en contenu en ligne dans les réunions qui incluent l’audio, la vidéo et le partage de contenu. Cela peut être apprécié via le bureau et le client web, ainsi que par le biais de nombreux appareils partenaires qui s’intègrent en mode natif à Microsoft Teams. Toutefois, de nombreux clients ont déjà investi dans des téléconférences vidéo et des appareils de communication vidéo personnels, qui peuvent être coûteux à mettre à niveau. Cloud Video Interop fournit une solution simple, qui vous permet de continuer à utiliser vos solutions existantes jusqu’à ce que vous soyez prêt à effectuer une mise à niveau.

Avec Cloud Video Interop, Microsoft Teams offre une expérience de réunion native à tous les participants, dans les salles de réunion ou à l’intérieur des clients Teams.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop est-il fait pour moi ?

Cloud Video Interop fournit un service intermédiaire pendant la transition vers une solution Microsoft Teams native complète, à l’aide de points de terminaison Teams. Le service fourni doit faire partie de votre chemin de migration.

Cloud Video Interop est destiné aux clients qui répondent aux critères suivants :

- Disposer d’un déploiement important d’appareils de salle de réunion et d’appareils vidéo personnels (plus de 50 appareils) qui ne sont pas qualifiés pour l’intégration directe avec Microsoft Teams
- Sont pris en charge par l’un de nos partenaires Cloud Video Interop
- Souhaitez conserver la valeur de leur investissement dans leurs appareils de salle de réunion actuels et leurs appareils vidéo personnels pendant la migration vers une solution Microsoft Teams native

Bien que Cloud Video Interop offre une excellente solution intermédiaire, nous encourageons nos clients à examiner nos solutions de réunion Teams natives, telles que Les systèmes de salle Teams, à long terme. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 gouvernement des États-Unis et des services tiers

Office 365 permet d’intégrer des applications tierces dans des sites SharePoint Online, des Skype Entreprise, Teams, des applications Office incluses dans Applications Microsoft 365 pour les grandes entreprises (telles que Word, Excel, PowerPoint et Outlook) et Outlook Web App. En outre, Office 365 prend en charge l’intégration avec des fournisseurs de services tiers. Ces applications et services tiers peuvent impliquer le stockage, la transmission et le traitement des données client de votre organisation sur des systèmes tiers qui se trouvent en dehors de l’infrastructure Office 365 et ne sont donc pas couverts par les engagements de conformité et de protection des données Office 365. **Il est recommandé de consulter les déclarations de confidentialité et de conformité fournies par les tiers lors de l’évaluation de l’utilisation appropriée de ces services pour votre organisation.**

> [!NOTE]
> Le connecteur Pexip Teams doit être hébergé dans les régions Azure Arizona ou Texas pour GCC High. La région Azure Virginie ne prend pas en charge l’hébergement du connecteur Pexip Teams pour GCC High.

### <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour Microsoft Teams

Les partenaires suivants disposent de solutions d’interopérabilité vidéo pour Microsoft Teams. Votre entreprise peut choisir de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 

|Partenaire|Solution de partenaire|
|----|---|
|![Logo représentant Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![Logo représentant Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity pour Microsoft Teams</a> | 
|![Logo représentant BlueJeans Gateway.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway pour Microsoft Teams</a> |
|![Logo représentant Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Vue d’ensemble de l’interopérabilité vidéo cloud

Cloud Video Interop est un service tiers proposé par nos partenaires pour assurer l’interopérabilité entre les solutions de visioconférence existantes et d’appareils vidéo personnels en local et Microsoft Teams.

Les solutions proposées par nos partenaires se composent de composants qui peuvent être déployés entièrement dans le cloud ou partiellement/entièrement localement. 
     
Le diagramme suivant montre l’architecture générale de nos solutions partenaires.

![Diagramme décrivant une solution partenaire Teams Cloud Video Interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Déployer l’interopérabilité vidéo cloud

Lors du déploiement d’une solution Cloud Video Interop, il est important de comprendre que vous déployez une solution partenaire. Les étapes générales à suivre pour déployer Cloud Video Interop sont répertoriées dans le diagramme suivant.

![Diagramme décrivant le déploiement de CVI dans votre organisation.](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Pendant la phase de plan, vous devez identifier les appareils que vous ne remplacerez pas par un appareil Teams natif et trouver un partenaire Cloud Video Interop qui peut prendre en charge ces appareils.  

Il est également important de comprendre que vous aurez besoin d’une licence pour chaque utilisateur qui planifiera des réunions auxquelles vous souhaitez qu’un appareil compatible Cloud Video Interop rejoigne. Notez que les exigences de licence exactes peuvent être obtenues auprès du partenaire Cloud Video Interop. Assurez-vous que cela est clair avant de commencer votre déploiement.

### <a name="configure"></a>Configuration

Le partenaire que vous avez choisi pour votre déploiement CVI vous fournira un document de déploiement complet qui comprend toutes les étapes nécessaires pour déployer correctement au sein de votre organisation. Cela inclut les ports de pare-feu et les plages d’adresses IP, les modifications de configuration de vos appareils et d’autres paramètres qui doivent être modifiés.

### <a name="provision"></a>Disposition  

Pendant la phase de provisionnement, vous allez attribuer des licences aux utilisateurs appropriés conformément au guide de configuration du partenaire. Vous devez également suivre le processus de consentement Azure pour fournir au partenaire l’accès à votre environnement Teams. Pour plus d’informations sur le processus de consentement Azure[, consultez Autorisations et consentement dans le point de terminaison Plateforme d'identités Microsoft](/azure/active-directory/develop/v2-permissions-and-consent).

### <a name="schedule"></a>Horaire

Une fois qu’un utilisateur est activé pour l’interopérabilité vidéo cloud, toute réunion planifiée à l’aide du complément de réunion Teams pour Outlook ou du client Teams aura les informations supplémentaires appropriées automatiquement ajoutées à la réunion Teams afin que les appareils compatibles avec l’interopérabilité vidéo cloud puissent participer à ces réunions.

### <a name="join"></a>Rejoindre

Selon la solution partenaire, il existe plusieurs façons de participer à une réunion compatible avec l’interopérabilité vidéo dans le cloud. Les scénarios exacts de participation aux réunions seront fournis par votre partenaire Cloud Video Interop. Nous avons répertorié quelques exemples ci-dessous :

- IVR (Interactive Voice Response) 
  - Vous pouvez vous connecter à la RVI du partenaire à l’aide de la tenantkey@domain.
  - Lorsque vous êtes dans la RVI partenaire, vous êtes invité à entrer le VTC conferenceId, qui vous connectera ensuite à la réunion Teams.
- Direct 
  - Vous pouvez vous connecter directement à la réunion Teams sans interagir avec la RVI du partenaire à l’aide de la fonctionnalité de numérotation directe, à l’aide de la chaîne complète de tenantkey. VTC ConferenceId@domain.
- Numérotation à une seule touche 
  - Si vous disposez d’une salle Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation à une seule touche offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).

## <a name="manage-cloud-video-interop"></a>Gérer l’interopérabilité vidéo cloud

Une fois Cloud Video Interop déployé, vous pouvez gérer les appareils à l’aide des solutions fournies par nos partenaires. Chaque partenaire vous fournira une interface d’administration qui inclura à la fois la gestion des licences et des appareils. 

Les rapports sont également disponibles directement à partir de l’interface d’administration du partenaire. Pour plus d’informations sur les fonctionnalités de création de rapports, contactez le partenaire de votre choix. 

### <a name="troubleshooting-cloud-video-interop"></a>Résolution des problèmes d’interopérabilité vidéo cloud

Cloud Video Interop est un service fourni par un partenaire. Si vous rencontrez des problèmes, la première étape consiste à connecter un appareil sur lequel le client Teams est installé et à le connecter au même segment que l’appareil Cloud Video Interop à l’origine des problèmes. 

Si Teams fonctionne correctement sur ce segment et que vous avez également suivi toutes les instructions de mise en réseau et de configuration fournies par le partenaire, vous devez contacter le partenaire pour une résolution des problèmes supplémentaires. 

## <a name="powershell-for-cloud-video-interop"></a>Interopérabilité vidéo PowerShell pour le cloud

Les applets de commande PowerShell suivantes vous permettent d’automatiser (partiellement) le déploiement cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy** : Microsoft fournit des stratégies prédéfinies pour chacun de nos partenaires pris en charge qui vous permettent de désigner le ou les partenaires à utiliser pour l’interopérabilité vidéo cloud.<br>Cette applet de commande vous permet d’identifier les stratégies prédéfinies que vous pouvez utiliser dans votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l’applet de commande Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy** : cette applet de commande vous permet d’affecter une stratégie prédéfinie à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.
- **New-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour spécifier des informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
- **Set-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour mettre à jour les informations sur un partenaire CVI pris en charge que votre organisation utilise.
- **Get-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour obtenir tous les fournisseurs qui ont été configurés pour une utilisation au sein de l’organisation.
- **Remove-CsVideoInteropServiceProvider** : utilisez cette applet de commande pour supprimer toutes les informations de fournisseur sur un fournisseur que votre organisation n’utilise plus.
