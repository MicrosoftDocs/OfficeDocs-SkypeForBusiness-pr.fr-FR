---
title: Interopérabilité de la vidéo cloud de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Utilisez Cloud Video Interop comme solution intermédiaire pour autoriser des appareils de salle de réunion tiers à participer Microsoft Teams réunions.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39452a659f1a95d66aeac4a18a4d7801764437ae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618640"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interopérabilité de la vidéo cloud de Microsoft Teams

Cloud Video Interop (CVI) est une solution tierce qualifiée par Microsoft qui permet à des salles de réunion tierces (téléconférence) et des périphériques vidéo personnels (VTCs) de participer à Microsoft Teams réunion.
 
Grâce Microsoft Teams, vous pouvez enrichir la collaboration de contenu en ligne au cours de réunions qui incluent l’audio, la vidéo et le partage de contenu. Cela peut être apprécié via le client de bureau et web, ainsi que par le biais de nombreux appareils partenaires qui s’intègrent en natif avec Microsoft Teams. Toutefois, de nombreux clients ont déjà investi dans la vidéoconférence et les périphériques de communication vidéo personnels, qui peuvent être coûteux à la mise à niveau. Cloud Video Interop fournit une solution simple qui vous permet de continuer à utiliser vos solutions existantes jusqu’à ce que vous soyez prêt à mettre à niveau.

Grâce à Cloud Video Interop, Microsoft Teams permet d’offrir une expérience de réunion native à tous les participants, dans des salles de réunion ou à l’intérieur Teams clients.

### <a name="is-cloud-video-interop-for-me"></a>Est-ce que Cloud Video Interop me s’offre à moi ?

Cloud Video Interop fournit un service intermédiaire pendant la transition vers une solution d’Microsoft Teams native, à l’aide Teams points de terminaison. Le service fourni doit faire partie de votre chemin de migration.

Cloud Video Interop est destiné aux clients qui répondent aux critères suivants :

- Déploiement important d’appareils de salle de réunion et de périphériques vidéo personnels (plus de 50 appareils) qui ne sont pas admissibles à une intégration directe avec Microsoft Teams
- Sont pris en charge par l’un de nos partenaires Cloud Video Interop
- Vous souhaitez conserver la valeur de leur investissement dans les appareils de salle de réunion et les périphériques vidéo personnels pendant la migration vers une solution Microsoft Teams native

Bien que Cloud Video Interop offre une solution intermédiaire, nous encourageons nos clients à se regarder dans nos solutions de réunion Teams natives, telles que Teams Room Systems, à long terme. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 Services publics et tiers des États-Unis

Office 365 permet d’intégrer des applications tierces dans des sites SharePoint Online, des applications Skype Entreprise, Teams et Office incluses dans Applications Microsoft 365 pour les grandes entreprises (telles que Word, Excel, PowerPoint et Outlook) et Outlook Web App. En outre, Office 365 prend en charge l’intégration avec des fournisseurs de services tiers. Ces applications et services tiers peuvent impliquer le stockage, la transmission et le traitement des données client de votre organisation sur des systèmes tiers qui ne sont pas conformes à l’infrastructure Office 365 et ne sont donc pas couverts par les engagements en matière de conformité et de protection des données Office 365. **Il est recommandé de consulter les déclarations de confidentialité et de conformité fournies par des tiers lors de l’évaluation de l’utilisation appropriée de ces services pour votre organisation.**



### <a name="partners-certified-for-microsoft-teams"></a>Partenaires certifiés pour Microsoft Teams

Les partenaires suivants ont des solutions d’interop vidéo pour Microsoft Teams. Votre entreprise peut choisir de travailler avec n’importe quelle combinaison de ces partenaires au sein de votre entreprise. 

|Partenaire|Solution partenaire|
|----|---|
|![Logo représentant Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![Logo représentant Pexip Infini](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infini pour Microsoft Teams</a> | 
|![Logo représentant la passerelle BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Passerelle BlueJeans pour Microsoft Teams</a> |
|![Logo représentant Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Intégration de Cisco Webex Video pour Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Vue d’ensemble d’Interop Cloud Video

Cloud Video Interop est un service tiers proposé par nos partenaires pour fournir une interopérabilité entre les solutions de vidéoconférence existantes et de périphériques vidéo personnels en local, et Microsoft Teams.

Les solutions proposées par nos partenaires se composent de composants qui peuvent être déployés entièrement sur le cloud ou partiellement/entièrement en local. 
     
Le diagramme suivant illustre l’architecture de haut niveau de nos solutions partenaires.

![Diagramme décrivant une solution partenaire Teams Cloud Video Interop](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Déployer Cloud Video Interop

Lors du déploiement d’une solution Cloud Video Interop, il est important de comprendre que vous déployez une solution partenaire. Les étapes générales à suivre pour déployer Cloud Video Interop sont répertoriées dans le diagramme suivant.

![Diagramme décrivant le déploiement de CVI dans votre organisation](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Au cours de la phase de plan, vous devez identifier les appareils que vous ne remplacerez pas par un appareil Teams natif et trouver un partenaire Cloud Video Interop qui peut prendre en charge ces appareils.  

Il est également important de comprendre que vous aurez besoin d’une licence pour chaque utilisateur qui planifiera des réunions pour lesquelles vous souhaitez qu’un appareil activé pour Cloud Video Interop participe. Notez que les conditions de licence exactes peuvent être obtenues auprès du partenaire Cloud Video Interop. Assurez-vous que ce message est clair avant de commencer votre déploiement.

### <a name="configure"></a>Configuration

Le partenaire que vous avez choisi pour votre déploiement DVI vous fournira un document de déploiement complet constitué de toutes les étapes nécessaires au déploiement au sein de votre organisation. Cela comprend les ports et les plages d’adresses IP du pare-feu, les modifications de configuration de vos appareils et d’autres paramètres à modifier.

### <a name="provision"></a>Approvisionnement  

Au cours de la phase de configuration, vous attribuerez des licences aux utilisateurs appropriés, conformément au guide de configuration du partenaire. Vous devrez également passer par le processus de consentement Azure pour fournir au partenaire l’accès à votre Teams professionnel. Pour [plus d’informations sur](/azure/active-directory/develop/v2-permissions-and-consent) le processus de consentement Azure, voir Autorisations et consentement dans Plateforme d’identités Microsoft point de terminaison.

### <a name="schedule"></a>Planifier

Une fois qu’un utilisateur est activé pour Cloud Video Interop, toute réunion programmée à l’aide du complément Réunion Teams pour Outlook ou du client Teams se chargera automatiquement d’ajouter les informations supplémentaires appropriées à la réunion Teams afin que les périphériques compatibles avec Cloud Video Interop puisse participer à ces réunions.

### <a name="join"></a>Rejoindre

Selon la solution partenaire, plusieurs méthodes s’offrent à vous pour participer à une réunion cloud avec Interop Video. Des scénarios exacts de participer à une réunion seront fournis par votre partenaire Cloud Video Interop. Nous avons répertorié quelques exemples ci-dessous :

- IVR (réponse vocale interactive) 
  - Vous pouvez appeler les IVR du partenaire à l’aide de la tenantkey@domain.
  - Lorsque vous êtes dans l’IVR partenaire, vous êtes invité à entrer le VTC conferenceId, qui vous connecte ensuite à la Teams partenaire.
- Numérotation directe 
  - Vous pouvez appeler directement la réunion Teams sans interagir avec les IVR du partenaire à l’aide de la fonctionnalité de numérotation directe, en utilisant la chaîne complète de touches client. VTC ConferenceId@domain.
- Numérotation à une pression 
  - Si vous avez une salle de numérotation Teams intégrée, vous pouvez utiliser les fonctionnalités de numérotation à une pression offertes par votre partenaire (sans avoir à taper de chaîne de numérotation).

## <a name="manage-cloud-video-interop"></a>Gérer Cloud Video Interop

Une fois Cloud Video Interop déployé, vous pouvez gérer les appareils à l’aide des solutions fournies par nos partenaires. Chaque partenaire vous fournira une interface administrative qui inclut à la fois la gestion des licences et des appareils. 

Les rapports sont également disponibles directement à partir de l’interface administrative du partenaire. Pour plus d’informations sur les fonctionnalités de rapport, contactez le partenaire de votre choix. 

### <a name="troubleshooting-cloud-video-interop"></a>Résolution des problèmes d’Interop cloud Video

Cloud Video Interop est un service fourni par un partenaire. Si vous rencontrez des problèmes, la première étape consiste à connecter un appareil sur qui le client Teams est installé et à le connecter au même segment que l’appareil Cloud Video Interop qui cause des problèmes. 

Si Teams fonctionne correctement sur ce segment et que vous avez également suivi toutes les instructions relatives à la mise en réseau et à la configuration fournies par le partenaire, vous devrez contacter ce partenaire pour obtenir une résolution des problèmes supplémentaire. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell pour Cloud Video Interop

Les cmdlets PowerShell suivantes sont disponibles pour automatiser (partiellement) le déploiement Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft fournit des stratégies pré-construite pour chacun de nos partenaires pris en charge qui vous permettent de désigner le ou les partenaires à utiliser pour Cloud Video Interop.<br>Cette cmdlet vous permet d’identifier les stratégies pré-construite que vous pouvez utiliser dans votre organisation. Vous pouvez affecter cette stratégie à un ou plusieurs de vos utilisateurs en tirant parti de l'Grant-CsTeamsVideoInteropServicePolicy cmdlet.
- **Grant-CsTeamsVideoInteropServicePolicy :** cette cmdlet vous permet d’attribuer une stratégie préécontante à utiliser dans votre organisation ou d’affecter la stratégie à des utilisateurs spécifiques.
- **New-CsVideoInteropServiceProvider**: utilisez cette cmdlet pour spécifier les informations sur un partenaire CVI pris en charge que votre organisation souhaite utiliser.
- **Set-CsVideoInteropServiceProvider**: utilisez cette cmdlet pour mettre à jour les informations sur un partenaire CVI pris en charge que votre organisation utilise.
- **Get-CsVideoInteropServiceProvider**: utilisez cette cmdlet pour obtenir tous les fournisseurs configurés pour une utilisation au sein de l’organisation.
- **Remove-CsVideoInteropServiceProvider**: cette cmdlet permet de supprimer toutes les informations de fournisseur concernant un fournisseur que votre organisation n’utilise plus.