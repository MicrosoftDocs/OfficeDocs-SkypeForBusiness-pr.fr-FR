---
title: Solutions de téléphonie Microsoft
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 'En savoir plus sur les solutions téléphoniques de Microsoft : système téléphonique (Autod exchange de succursale privé - PBX) et options de connectivité PSTN (forfaits d’appels et routage direct).'
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 4fa6b04fba5b9dbea30cfeeb9e347cf542f07d38
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110590"
---
# <a name="microsoft-telephony-solutions"></a>Solutions de téléphonie Microsoft

Microsoft prend en charge plusieurs options lorsque vous commencez votre parcours vers Teams dans le cloud Microsoft. Cet article vous aide à déterminer quelle solution de téléphonie Microsoft (système téléphonique dans le cloud ou Voix Entreprise local) est adaptée aux utilisateurs de votre organisation et comment votre organisation peut se connecter au réseau téléphonique commuté (PSTN).

Vous devez utiliser cet article avec le diagramme technique associé, qui fournit une aide visuelle pour prendre la bonne décision pour votre organisation :

- [Solutions de téléphonie Microsoft - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Solutions de téléphonie Microsoft - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Options pbX (Private Branch Exchange)

### <a name="phone-system-microsoft-365-or-office-365"></a>Système téléphonique (Microsoft 365 ou Office 365)
  
Le système téléphonique est la technologie de Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités PBX (Private Branch Exchange) dans le cloud Microsoft 365 ou Office 365 avec Microsoft Teams et/ou Skype Entreprise Online.

Le système téléphonique fonctionne avec les clients teams ou Skype Entreprise Online et les appareils certifiés. Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement livrées à partir de Microsoft 365 ou Office 365 et étroitement intégrées à l’expérience de productivité cloud de l’entreprise. Pour connecter le système téléphonique au réseau téléphonique commuté (PSTN), vous pouvez choisir le forfait d’appels de Microsoft ou votre propre opérateur téléphonique.

Pour plus d’informations, voir [Qu’est-ce que le système téléphonique dans Microsoft 365 ou Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Voix Entreprise (Skype Entreprise Server)

Voix Entreprise est la technologie de Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités PBX (Private Branch Exchange) dans Skype Entreprise Server local. Cette option Skype Entreprise ne peut être connectée au réseau téléphonique commuté qu’à l’aide de votre propre opérateur téléphonique.

Pour plus d’informations, voir [Plan for Voix Entreprise in Skype for Business Server](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connexion aux options du réseau téléphonique commuté (PSTN)

Vous pouvez choisir de vous connecter au réseau téléphonique commuté (PSTN) en :

- Utilisation du forfait d’appels Microsoft dans Microsoft 365 ou Office 365 
- Connexion de votre propre opérateur téléphonique

### <a name="calling-plan-microsoft-365-or-office-365"></a>Forfait d’appels (Microsoft 365 ou Office 365)

Cette option connecte le système téléphonique Microsoft 365 ou Office 365 au réseau téléphonique commuté (PSTN) pour activer les appels vers les téléphones fixes et mobiles dans le monde entier. Avec forfait d’appels, Microsoft est votre opérateur PSTN.

Pour plus d’informations, [voir Forfaits d’appels pour Microsoft 365 ou Office 365.](/MicrosoftTeams/calling-plans-for-office-365)

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Connecter votre propre opérateur téléphonique (Microsoft 365 ou Office 365 et Skype Entreprise local)

Cette option connecte le système téléphonique dans Microsoft 365 ou Office 365 ou le système Voix Entreprise dans Skype Entreprise local à votre réseau téléphonique. Cette option nécessite un contrôleur SBC (Session Border Controller) pris en charge. Dans certains cas, cette option peut nécessiter des logiciels Microsoft supplémentaires déployés en local.

## <a name="which-solution-is-right-for-your-organization"></a>Quelle solution est adaptée à votre organisation ?

Vous pouvez choisir une solution tout-dans-le-cloud, une solution connect-your-own-carrier ou un mélange entre les opérateurs tout-dans-le-cloud et les opérateurs tiers :

- Système téléphonique avec forfait d’appels (dans le cloud)

- Système téléphonique avec son propre opérateur via le routage direct

- Système téléphonique avec son propre opérateur via Skype Entreprise Server OU Cloud Connector Edition

- Voix Entreprise skype entreprise server avec son propre opérateur

La solution que vous choisissez dépend de vos besoins actuels et futurs, tels que :

- Que vous vouliez ou soient requis pour conserver les fonctionnalités fournies par votre déploiement local.
- Le client que vous souhaitez déployer pour vos utilisateurs.
- Votre plan consiste à déplacer des personnes vers le cloud.
- Si vous devez interopérer avec des PBX tiers et d’autres équipements téléphoniques.

Prenez en compte les questions suivantes pour déterminer la meilleure solution pour votre organisation :

- Avez-vous un déploiement Skype Entreprise Server existant ?
- Vos utilisateurs sont-ils homed in Skype for Business on premises, in the cloud on Skype for Business Online, or both? 
- Voulez-vous déplacer des utilisateurs locaux vers le cloud ?
- Le plan d’appel PSTN de Microsoft est-il disponible dans votre région ?
- Voulez-vous ou devez-vous conserver votre opérateur téléphonique actuel ?  Par exemple, devez-vous conserver votre opérateur actuel en raison d’un contrat existant ?
- Avez-vous un PBX hérité local existant que vous souhaitez ou devez conserver ?
- Votre PBX hérité actuel offre-t-il des fonctionnalités uniques qui sont essentielles à votre entreprise ?
- L’un ou l’ensemble de vos utilisateurs nécessitent-ils des fonctionnalités qui ne sont pas actuellement proposées dans le système téléphonique ?

Veuillez prendre en compte les éléments suivants:

- Les quatre options peuvent co-exister les unes avec les autres si vous avez besoin de concevoir une solution pour un environnement complexe ou de gérer la migration en plusieurs étapes.
- Le système téléphonique avec son propre opérateur via Skype Entreprise Server ou Cloud Connector Edition ne peut être déployé qu’avec Skype Entreprise Server ou Cloud Connector. La coexistence de Skype Entreprise Server et cloud Connector n’est pas prise en charge dans une seule entreprise.

## <a name="phone-system-with-calling-plan"></a>Système téléphonique avec forfaits d’appels


Le système téléphonique avec forfait d’appels est une option tout-dans-le-cloud pour les utilisateurs de Teams ou Skype Entreprise Online, comme illustré dans le diagramme suivant :

![Système téléphonique avec forfaits d’appels](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Système téléphonique Microsoft avec des forfaits d’appels nationaux ou internationaux ajoutés qui permettent d’appeler des téléphones dans le monde entier (selon le niveau de service sous licence). 
- Étant donné que le plan d’appel PSTN fonctionne en dehors de Microsoft 365 ou d’Office 365, cette option ne nécessite pas de déploiement ou de maintenance de déploiement local.
- Les clients peuvent connecter un SBC pris en charge via le routage direct pour l’interopérabilité avec des PBX tiers, des périphériques analogiques et d’autres équipements téléphoniques tiers pris en charge par le SBC.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion ininterrompue à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier*                            | Non  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (Session Border Controller) pris en charge | Non |
| Nécessite un contrat avec un opérateur tiers      | Non   |
| Nécessite le déploiement et la maintenance de Skype Entreprise Server ou cloud Connector Edition | Non |

\*Pour plus d’informations sur les pays où forfait d’appels est disponible, voir Disponibilité des forfaits d’appels et de l’audioconférence dans les pays et [régions.](/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)


Si vous répondez oui aux questions suivantes, il s’agit de la solution appropriée pour vous :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous souhaitez utiliser l’accès géré par Microsoft au réseau téléphonique commuté (PSTN).
- Vous ne souhaitez pas gérer vous-même les contrôleurs de frontière de session.
- Teams et/ou Skype Entreprise Online disposent de toutes les fonctionnalités dont votre organisation a besoin.

Pour plus d’informations, voir What [is Phone System in Microsoft 365 and Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) and Calling Plans for Microsoft [365 or Office 365](/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Système téléphonique avec son propre opérateur via le routage direct

Cette option fournit au système téléphonique Microsoft dans le cloud pratiquement n’importe quel opérateur téléphonique pour les utilisateurs de Teams.

![Système téléphonique avec votre opérateur via le routage direct](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connectez directement votre propre SBC pris en charge au système téléphonique Microsoft sans avoir besoin de logiciels locaux supplémentaires.  
- Utiliser pratiquement n’importe quel opérateur téléphonique avec Microsoft Phone System.
- Peut être configuré et géré par des clients ou par votre opérateur ou partenaire (demandez si votre opérateur ou partenaire propose cette option).
- Configurez l’interopérabilité entre votre équipement téléphonique, tel qu’un PBX tiers et des périphériques analogiques, et Microsoft Phone System.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion ininterrompue à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (Session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers*      | Oui   |
| Nécessite le déploiement et la maintenance de Skype Entreprise Server ou cloud Connector Edition | Non |

\* Sauf s’il est déployé en tant qu’option pour fournir une connexion à des PBX tiers, des périphériques analogiques ou d’autres équipements téléphoniques pour les utilisateurs qui utilisent un système téléphonique avec forfaits d’appels.

Si vous répondez oui aux questions suivantes, il s’agit de la solution appropriée pour vous :

- Vous voulez utiliser Teams avec le système téléphonique.
- Vous devez conserver votre opérateur PSTN actuel.
- Vous souhaitez combiner le routage, certains appels via les forfaits d’appels, d’autres via votre opérateur
- Vous devez interopérer avec des PBX tiers et/ou des équipements tels que des pageurs de surcharge, des périphériques analogiques
- Teams dispose de toutes les fonctionnalités dont votre organisation a besoin.

Pour plus d’informations, voir Qu’est-ce que le système téléphonique dans [Microsoft 365 et Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365) et [planifier le routage direct](/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Système téléphonique avec son propre opérateur via Skype Entreprise Server OU Cloud Connector Edition

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams à l’aide [du routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Cette option fournit au système téléphonique Microsoft dans le cloud la connectivité à un réseau téléphonique local pour les utilisateurs de Skype Entreprise Online.

![Système téléphonique avec votre opérateur via Skype Entreprise Server OU Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connectez votre propre SBC pris en charge au système téléphonique Microsoft via Skype Entreprise Server ou Skype Entreprise, version Cloud Connector déployée en local. 
- Utiliser pratiquement n’importe quel opérateur téléphonique avec Microsoft Phone System. 
- Si vous avez déjà Skype Entreprise Server en local, vous pouvez l’utiliser ;  Si ce n’est pas le cas, vous pouvez déployer une version plus légère : Cloud Connector Edition.


| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion ininterrompue à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (Session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers      | Oui   |
| Nécessite le déploiement et la maintenance de Skype Entreprise Server ou cloud Connector Edition | Oui |



Si vous répondez oui aux questions suivantes, il s’agit de la solution appropriée pour vous :

- Vous souhaitez utiliser Skype Entreprise Online pour vos utilisateurs.
- Le plan d’appel PSTN n’est pas disponible dans votre région.
- Vous devez conserver votre opérateur PSTN actuel.

Pour plus d’informations, voir What [is Phone System in Microsoft 365 and Office 365](/MicrosoftTeams/what-is-phone-system-in-office-365), Skype for Business Server [2019](../../SfBServer2019/skype-for-business-server-2019.yml), and [Plan for Skype for Business Cloud Connector Edition](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).

Recommandation : lorsque les conditions professionnelles changent(par exemple, vous n’avez plus besoin de conserver votre opérateur PSTN), envisagez de passer à Microsoft Teams à l’aide des options 1 ou 2 vers :
- Réduire les coûts de maintenance
- Accéder aux dernières fonctionnalités publiées par Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Voix Entreprise skype entreprise server avec son propre opérateur

Cette option fournit Voix Entreprise la connectivité à un réseau téléphonique local pour les utilisateurs locaux de Skype Entreprise.

![Voix Entreprise skype entreprise server avec son propre opérateur](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connectez votre propre SBC pris en charge Voix Entreprise système local dans Skype Entreprise.
- À utiliser si vous avez besoin d’une survivabilité locale.
- Utiliser pratiquement n’importe quel opérateur téléphonique avec Microsoft Phone System. 
- Option la plus complexe pour le déploiement et la maintenance.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion ininterrompue à Microsoft 365 ou Office 365 | Non |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (Session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers      | Oui   |
| Nécessite le déploiement et la maintenance de Skype Entreprise Server | Oui |

Pour plus d’informations, voir [Plan for Voix Entreprise in Skype for Business Server](../../SfbServer/plan-your-deployment/enterprise-voice-solution/enterprise-voice.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).

Recommandation : lorsque les conditions professionnelles changent(par exemple, vous n’avez plus besoin de conserver votre opérateur PSTN), envisagez de passer à Microsoft Teams à l’aide des options 1 ou 2 vers :
- Réduire les coûts de maintenance
- Accéder aux dernières fonctionnalités publiées par Microsoft