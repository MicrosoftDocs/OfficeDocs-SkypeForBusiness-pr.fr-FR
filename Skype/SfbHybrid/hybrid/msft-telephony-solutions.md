---
title: Détails sur les solutions téléphoniques Microsoft Telephony
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
description: Décrit les solutions de téléphonie Microsoft.
ms.openlocfilehash: 4d83ea2251175de65db6e642f89bca730af9e0be
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359100"
---
# <a name="microsoft-telephony-solutions"></a>Détails sur les solutions téléphoniques Microsoft Telephony

Microsoft prend en charge plusieurs options lorsque vous commencez votre transition vers teams dans le Cloud de Microsoft. Cet article vous aide à décider quelle solution de téléphonie Microsoft (système téléphonique dans le Cloud ou voix entreprise en local) est appropriée pour les utilisateurs de votre organisation, et comment votre organisation peut se connecter au réseau téléphonique commuté (PSTN). 

Vous devez utiliser cet article avec le diagramme technique associé, qui fournit une aide visuelle pour prendre la bonne décision pour votre organisation :

- [Solutions de téléphonie Microsoft-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Solutions de téléphonie Microsoft-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Options de PBX (Private Branch Exchange)

### <a name="phone-system-microsoft-365-or-office-365"></a>Système téléphonique (Microsoft 365 ou Office 365)
  
Le système téléphonique est la technologie de Microsoft qui permet d’activer les fonctionnalités de contrôle d’appel et de PBX (Private Branch Exchange) dans le nuage Microsoft 365 ou Office 365 avec Microsoft teams et/ou Skype entreprise online. 

Le système téléphonique fonctionne avec les clients teams ou Skype entreprise Online et les appareils certifiés. Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités livré directement par Microsoft 365 ou Office 365 et intégré étroitement à l’expérience de productivité dans le Cloud de l’entreprise. Pour connecter un système téléphonique au réseau téléphonique commuté (RTC), vous pouvez choisir Microsoft Call plan ou votre propre opérateur téléphonique.

Pour plus d’informations, consultez la rubrique [qu’est-ce que le système téléphonique dans Microsoft 365 ou Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Voix entreprise (Skype entreprise Server)

Voix entreprise est la technologie de Microsoft qui permet d’activer le contrôle d’appel et les fonctionnalités PBX (Private Branch Exchange) sur le serveur Skype entreprise local. Cette option ne peut être connectée au réseau téléphonique commuté public qu’à l’aide de votre propre opérateur de téléphonie. 

Pour plus d’informations, reportez-vous à la rubrique [plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Connexion aux options RTC (réseau téléphonique commuté)

Vous pouvez choisir de vous connecter au réseau téléphonique commuté (PSTN) en procédant comme suit :

- Utilisation de Microsoft Call plan dans Microsoft 365 ou Office 365 
- Connexion de votre propre opérateur de téléphonie

### <a name="calling-plan-microsoft-365-or-office-365"></a>Plan d’appel (Microsoft 365 ou Office 365)

Cette option connecte le système téléphonique Microsoft 365 ou Office 365 au réseau téléphonique commuté (PSTN) pour permettre les appels vers les téléphones fixes et mobiles dans le monde entier. Avec le forfait d’appels, Microsoft est votre opérateur RTC.

Pour plus d’informations, consultez la rubrique [forfaits d’appels pour Microsoft 365 ou Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Connexion de votre propre opérateur de téléphonie (Microsoft 365 ou Office 365 et Skype entreprise en local)

Cette option connecte le système téléphonique de Microsoft 365 ou Office 365 ou Enterprise Voice dans Skype entreprise en local à votre réseau téléphonique. Cette option nécessite un contrôleur SBC (session Border Controller) pris en charge. Dans certains cas, cette option peut nécessiter des logiciels Microsoft supplémentaires déployés sur site.

## <a name="which-solution-is-right-for-your-organization"></a>Quelle solution convient à votre organisation ?

Vous pouvez choisir une solution « tout-en-un-Cloud », une solution de connexion à votre propre opérateur ou une combinaison entre les opérateurs de tout-le-nuage et tiers :

- Système téléphonique avec forfait d’appels (tout dans le Cloud)

- Système téléphonique avec propre opérateur via le routage direct

- Système téléphonique avec propre opérateur via Skype entreprise Server ou Cloud Connector Edition

- Voix entreprise dans Skype entreprise Server avec votre propre opérateur

La solution que vous choisissez dépend de vos besoins actuels et à venir, par exemple :

- Si vous le souhaitez,-ou si nécessaire,-pour conserver les fonctionnalités fournies par votre déploiement sur site.
- Le client que vous souhaitez déployer pour vos utilisateurs.
- Votre forfait pour le transfert des personnes vers le Cloud.
- Si vous devez interagir avec des PBX tiers et d’autres équipements de téléphonie.

Posez-vous les questions suivantes pour déterminer la meilleure solution pour votre organisation :

- Disposez-vous d’un déploiement Skype entreprise Server existant ?
- Vos utilisateurs sont-ils hébergés dans Skype entreprise en local, dans le nuage sur Skype entreprise Online ou dans les deux ? 
- Voulez-vous déplacer les utilisateurs locaux vers le Cloud ?
- Le plan d’appel RTC de Microsoft est-il disponible dans votre région ?
- Souhaitez-vous conserver votre opérateur de téléphonie actuel ?  Par exemple, avez-vous besoin de conserver votre opérateur actuel en raison d’un contrat existant ?
- Avez-vous besoin d’un système PBX hérité sur site existant ou que vous souhaitez conserver ?
- Votre système PBX actuel offre-t-il des fonctionnalités uniques essentielles à votre entreprise ?
- Certains ou l’ensemble de vos utilisateurs nécessitent-ils des fonctionnalités qui ne sont actuellement pas proposées dans le système téléphonique ?

Veuillez prendre en compte les éléments suivants:

- Les quatre options peuvent coexister les unes avec les autres au cas où vous devriez concevoir une solution pour un environnement complexe ou la gestion de la migration en plusieurs étapes.
- Le système téléphonique avec propre opérateur via Skype entreprise Server ou Cloud Connector Edition ne peut être déployé qu’avec Skype entreprise Server ou Cloud Connector. La coexistence de Skype entreprise Server et de Cloud Connector n’est pas prise en charge dans une seule société.

## <a name="phone-system-with-calling-plan"></a>Système téléphonique avec forfait d’appels


Le système téléphonique avec forfait d’appels est une option tout en nuage pour les équipes ou les utilisateurs de Skype entreprise Online, comme illustré dans le diagramme suivant :

![Système téléphonique avec forfait d’appels](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Système Microsoft Phone avec des forfaits d’appels nationaux ou internationaux permettant d’appeler des téléphones dans le monde entier (en fonction du niveau de service sous licence). 
- Étant donné que le plan d’appel RTC fonctionne à partir de Microsoft 365 ou Office 365, cette option ne nécessite pas de déploiement ou de maintenance de tout déploiement local.
- Les clients peuvent connecter un contrôleur SBC pris en charge via le routage direct pour l’interopérabilité avec un PBX tiers, des appareils analogiques et d’autres équipements de téléphonie tiers pris en charge par l’SBC.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion sans interruption à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier *                            | Non  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (session Border Controller) pris en charge | Non |
| Nécessite un contrat avec un opérateur tiers      | Non   |
| Nécessite le déploiement et la maintenance de Skype entreprise Server ou de Cloud Connector Edition | Non |

\* Pour plus d’informations sur les pays où le plan d’appels est disponible, consultez la rubrique [disponibilité du pays et de la région pour l’audioconférence et les forfaits d’appels](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Si vous répondez oui aux questions suivantes, il s’agit de la solution la plus adaptée :

- Le plan d’appel est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur RTC actuel.
- Vous souhaitez utiliser un accès géré par Microsoft au réseau téléphonique commuté (RTC).
- Vous ne souhaitez pas gérer les contrôleurs de frontière de session.
- Teams et/ou Skype entreprise Online offre toutes les fonctionnalités requises par votre organisation.

Pour plus d’informations, consultez [qu’est-ce que le système téléphonique dans microsoft 365 et office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) et les [forfaits d’appels pour Microsoft 365 ou Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Système téléphonique avec propre opérateur via le routage direct

Cette option fournit un système Microsoft Phone dans le Cloud avec pratiquement n’importe quel opérateur de téléphonie pour les utilisateurs de teams.

![Système téléphonique avec votre opérateur via le routage direct](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Connectez directement votre propre SBC au système Microsoft Phone sans avoir besoin de logiciels supplémentaires sur site.  
- Utilisez pratiquement n’importe quel opérateur de téléphonie avec Microsoft Phone System.
- Peuvent être configurés et gérés par les clients ou par votre opérateur ou votre partenaire (demandez si votre opérateur ou partenaire fournit cette option).
- Configurez l’interopérabilité entre votre équipement de téléphonie, tel qu’un système PBX tiers et des périphériques analogiques, et Microsoft Phone System.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion sans interruption à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers *      | Oui   |
| Nécessite le déploiement et la maintenance de Skype entreprise Server ou de Cloud Connector Edition | Non |

\* Sauf si elle est déployée en tant qu’option pour fournir une connexion à un PBX tiers, des appareils analogiques ou d’autres équipements de téléphonie pour les utilisateurs qui se trouvent sur un système téléphonique avec forfaits d’appels.

Si vous répondez oui aux questions suivantes, il s’agit de la solution la plus adaptée :

- Vous souhaitez utiliser teams avec le système téléphonique.
- Vous devez conserver votre opérateur RTC actuel.
- Vous souhaitez mélanger le routage, certains appels passent via des forfaits d’appels, certains via votre opérateur
- Vous devez interopérer avec des PBX tiers et/ou des appareils de communication, des appareils analogiques.
- Teams dispose de toutes les fonctionnalités requises par votre organisation.

Pour plus d’informations, consultez [qu’est-ce que le système téléphonique dans Microsoft 365 et Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) et [planifiez le routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Système téléphonique avec propre opérateur via Skype entreprise Server ou Cloud Connector Edition

> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.  De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Cette option permet au système Microsoft Phone dans le Cloud de se connecter à un réseau téléphonique local pour les utilisateurs de Skype entreprise online.

![Système téléphonique avec votre opérateur via Skype entreprise Server ou Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Connectez votre propre SBC au système Microsoft Phone via Skype entreprise Server ou Skype entreprise, version Cloud Connector déployée en local. 
- Utilisez pratiquement n’importe quel opérateur de téléphonie avec Microsoft Phone System. 
- Si vous possédez déjà Skype entreprise Server en local, vous pouvez l’utiliser ;  Si vous ne le faites pas, vous pouvez déployer une version plus légère – Cloud Connector Edition.


| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion sans interruption à Microsoft 365 ou Office 365 | Oui |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers      | Oui   |
| Nécessite le déploiement et la maintenance de Skype entreprise Server ou de Cloud Connector Edition | Oui |



Si vous répondez oui aux questions suivantes, il s’agit de la solution la plus adaptée :

- Vous souhaitez utiliser Skype entreprise Online pour vos utilisateurs.
- Le plan d’appel RTC n’est pas disponible dans votre région.
- Vous devez conserver votre opérateur RTC actuel.

Pour plus d’informations, consultez la rubrique [What is Phone System in Microsoft 365 and Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)et [plan for Skype for Business Cloud Connector Edition](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Recommandation : lorsque les conditions de l’entreprise changent (par exemple, vous n’avez plus besoin de conserver votre opérateur RTC), envisagez de passer à Microsoft teams à l’aide des options 1 ou 2 pour :
- Réduire les coûts de maintenance
- Avoir accès aux dernières fonctionnalités publiées par Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Voix entreprise dans Skype entreprise Server avec votre propre opérateur

Cette option fournit une voix entreprise sur site avec la connectivité à un réseau téléphonique local pour les utilisateurs locaux de Skype entreprise.

![Voix entreprise dans Skype entreprise Server avec votre propre opérateur](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Connectez votre propre contrôleur SBC au système voix entreprise dans Skype entreprise sur site.
- À utiliser si vous avez besoin d’une survivabilité locale.
- Utilisez pratiquement n’importe quel opérateur de téléphonie avec Microsoft Phone System. 
- Option la plus complexe à déployer et à gérer.

| Conditions requises en matière d’infrastructure                   | Obligatoire ?|
| :----------------------------------------------------| ---------:|
| Nécessite une connexion sans interruption à Microsoft 365 ou Office 365 | Non |
| Disponible dans le monde entier                            | Oui  |
| Nécessite le déploiement et la maintenance d’un contrôleur SBC (session Border Controller) pris en charge | Oui |
| Nécessite un contrat avec un opérateur tiers      | Oui   |
| Nécessite le déploiement et la maintenance de Skype entreprise Server | Oui |

Pour plus d’informations, reportez-vous à la rubrique [plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Recommandation : lorsque les conditions de l’entreprise changent (par exemple, vous n’avez plus besoin de conserver votre opérateur RTC), envisagez de passer à Microsoft teams à l’aide des options 1 ou 2 pour :
- Réduire les coûts de maintenance
- Avoir accès aux dernières fonctionnalités publiées par Microsoft
