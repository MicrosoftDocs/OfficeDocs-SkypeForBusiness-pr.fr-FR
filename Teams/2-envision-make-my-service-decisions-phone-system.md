---
title: Prendre des décisions pour le service de systèmes téléphoniques avec forfaits d’appels - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Choisissez parmi les offres d’appel et la gestion des licences, configurez des emplacements d’urgence et des fonctionnalités telles que la boîte vocale et l’identification de l’appelant, achetez ou transférez des numéros
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232356"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de service

Pour planifier l’implémentation technique du système téléphonique avec des plans d’appels, vous devez prendre des décisions sur les services à l’avance pour préparer votre organisation à mettre en place une solution qui répond à vos besoins professionnels définis.

## <a name="calling-in-teams"></a>Appel dans teams

Grâce à Microsoft Teams, vos utilisateurs peuvent passer et recevoir des appels téléphoniques à partir du réseau téléphonique public commuté (RTC). Vos utilisateurs peuvent utiliser leur propre numéro de téléphone pour passer et recevoir des appels nationaux et internationaux depuis des applications clientes Teams, grâce à des fonctionnalités avancées qui incluent la boîte vocale.

> [!NOTE]
> La présentation la plus récente d’équipes concernant l’identification du système téléphonique d’équipe avec les fonctionnalités de plan d’appel <https://aka.ms/O365Roadmap>de votre déploiement est disponible à l’adresse.

## <a name="phone-system-in-teams"></a>Système téléphonique dans teams

Pour permettre aux utilisateurs d’équipes de passer et de recevoir des appels RTC, ils doivent être activés pour le système téléphonique, une fonctionnalité d’Office 365.

Pour permettre la connectivité au RTC, votre organisation peut utiliser Microsoft comme fournisseur de services de télécommunication. Pour le moment, vous avez la possibilité de «proposer votre propre fournisseur de services de téléphonie» pour activer la connectivité PSTN pour le système téléphonique.

> [!IMPORTANT]
> La possibilité d’utiliser votre propre fournisseur de services de télécommunication pour le système téléphonique avec le déploiement d’équipes est également disponible avec le routage direct du système téléphonique. Pour en savoir plus sur le routage direct, consultez les instructions relatives au [routage direct](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Système téléphonique avec forfaits d’appels

Pour utiliser Microsoft comme fournisseur de services de télécommunication, vous devez obtenir les licences de plan d’appel et les affecter aux utilisateurs de votre système téléphonique.

Il existe deux types principaux de plans d’appel:

-   Forfait d’appels nationaux

-   Forfait d’appels nationaux et internationaux

Chaque type de plan d’appel attribue un certain nombre de minutes d’appel par mois à chaque utilisateur qui a reçu la licence. Lorsque l’attribution des minutes d’appel est épuisée, l’utilisateur ne pourra pas passer d’appels sortants, à l’exception des appels d’urgence, jusqu’au cycle de facturation du mois suivant. Si vous souhaitez que les utilisateurs puissent continuer à passer des appels sortants même après avoir épuisé leur attribution de minutes d’appel ou pour permettre aux utilisateurs disposant d’un forfait d’appel national d’avoir atteint les appels internationaux, vous pouvez configurer des crédits de communication pour votre organisation.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilité des offres d’appels

Avant de planifier l’implémentation des plans d’appel dans Teams, vérifiez que le service des forfaits d’appels est disponible dans votre région en passant en revue la [disponibilité du pays et de la région pour les offres de conférence et d’appels audio](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison de contraintes juridiques, les offres d’appels doivent être disponibles pour les organisations multinationales, le contrat pour les abonnements Office 365 doit être basé dans un pays ou une région où le service d’appels est disponible, ou dans lequel le service des plans d’appel peut être fournis.

> [!NOTE]
> Si les plans d’appel ne sont pas disponibles dans votre région, vous pouvez utiliser le [routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md) pour permettre aux utilisateurs d’utiliser des équipes dotées des fonctionnalités RTC.

Après confirmation de l’obtention du service de plans d’appel par votre organisation, compilez la liste des emplacements des utilisateurs ou des bureaux où vous allez mettre en œuvre le service des plans d’appel, en fonction de la liste des pays et régions disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements des utilisateurs ou les bureaux dans lesquels vous implémenterez le service des plans d’appels.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements des utilisateurs ou les bureaux à activer pour le service des plans d’appels.</li></ul>|

> [!TIP]
> Vous trouverez ci-dessous un exemple de système téléphonique avec la liste de plans d’activation de site.
> 
> | **Bureau**                     | **Emplacement**   | **Service de système téléphonique** |
> |--------------------------------|----------------|--------------------------|
> | 1 Eppîng Road                | Australie      | Service PSTN hérité |
> | 100 Cyberport Road             | Hong Kong R.A.S.  | Routage direct via le système téléphonique |
> | 1 Marina Boulevard           | Singapour      | Routage direct via le système téléphonique |
> | 32 London Bridge Street        | Royaume-Uni | Système téléphonique avec forfaits d’appels |
> | 39 quai du Président Roosevelt | France         | Système téléphonique avec forfaits d’appels |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les offres d’appels d’Office 365, chaque utilisateur de votre organisation doit disposer d’un numéro de téléphone unique et d’une adresse de secours validée correspondante. Passez en revue la [gestion des numéros de téléphone vocaux Cloud](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) pour planifier l’acquisition du numéro de téléphone de votre implémentation de plans d’appel.

Lorsque vous configurez des numéros de téléphone pour les offres d’appels, vous devez attribuer une adresse d’urgence à chaque numéro de téléphone avant d’affecter le numéro à un utilisateur. Cela est nécessaire pour prendre en charge les appels d’urgence. L’adresse de secours doit être validée pour vérifier qu’elle est dans le bon format à utiliser par les services de réponse d’urgence.

> [!IMPORTANT]
> Les appels vers les services d’urgence fonctionnent différemment dans le service des plans d’appel et dans les services téléphoniques traditionnels. Il est important que vous comprenez ces différences et les communiquez à tous les utilisateurs. Pour plus d’informations, consultez les conditions générales d’utilisation des [appels d’urgence](emergency-calling-terms-and-conditions.md) .

Outre la fourniture d’une adresse de secours validée, vous pouvez définir des emplacements d’urgence et les associer à l’adresse de secours validée afin de fournir un emplacement plus précis au sein d’une adresse. Un emplacement d'urgence correspond généralement à un numéro de bâtiment, un étage, une aile de bâtiment ou un numéro de bureau où se trouve l'utilisateur.

Pour en savoir plus sur les emplacements d’urgence en ce qui concerne les offres d’appels, consultez les articles suivants:

-   [Que sont les emplacements, les adresse et le routage d'appel d'urgence ?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Conditions générales d’utilisation des appels d’urgence](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez la granularité des informations d’emplacement d’urgence à collecter pour les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation de plans d’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez l’adresse de secours et les emplacements d’urgence détaillés pour chaque emplacement utilisateur ou bureau dans le cadre de l’implémentation de plans d’appel.</li></ul>|

> [!TIP]
> Vous pouvez utiliser le modèle suivant pour documenter les détails des numéros de téléphone et les détails de l’emplacement d’urgence.
> 
> |Utilisateur |Emplacement et adresse d’urgence |Numéro de téléphone |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 Londres Bridge Street, Londres, SE1., Royaume-Uni |commande + 44 23 4567 8901 |
> |Lidia Holloway |1065/32 Londres Bridge Street, Londres, SE1., Royaume-Uni |commande + 44 23 4567 89112 |
> |Louis Lahr |1023/32 Londres Bridge Street, Londres, SE1., Royaume-Uni |commande + 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-au-Moulineaux, France | TBA |
> |Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-au-Moulineaux, France | TBA |
> |Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-au-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Messagerie vocale

La messagerie vocale Cloud, optimisée par les services de boîte vocale Azure, prend en charge les dépôts de boîte vocale dans les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de courrier tiers.

Par défaut, la boîte vocale Cloud fonctionne avec Exchange Online. Toutefois, il possède un modèle de version et de déploiement local pris en charge pour permettre la remise de messages vocaux aux boîtes aux lettres des utilisateurs dans le déploiement Exchange local.

La messagerie vocale Cloud inclut la transcription de la boîte vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription de la boîte vocale pour des utilisateurs spécifiques ou pour tout le monde au sein de l’organisation. Si votre organisation a décidé de maintenir la transcription de la boîte vocale activée, vous devez également envisager d’activer ou de désactiver le masquage de la boîte vocale. Pour plus d’informations, reportez-vous à [la rubrique Configuration des stratégies de messagerie vocale pour votre organisation](set-up-phone-system-voicemail.md)

>[!NOTE]
> Un mécanisme de secours a été implémenté de sorte que la boîte vocale Cloud puisse renvoyer les messages à l’aide du protocole SMTP, ce qui signifie que les utilisateurs disposant d’une boîte aux lettres sur un système de courrier tiers recevront leurs messages vocaux. Ce mécanisme n’inclut pas le fonctionnement garanti du service ou d’autres fonctions de messagerie vocale, comme le changement d’accueil de la boîte vocale.

Pour plus d’informations sur la boîte vocale dans l’implémentation d’un système téléphonique, voir [système téléphonique avec forfaits d’appels](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si vous voulez activer la boîte vocale Cloud dans votre implémentation de plans d’appel.</li><li>Si vous utilisez Exchange en local et que votre déploiement actuel ne répond pas à vos exigences de prise en charge de la messagerie vocale dans le Cloud, choisissez l’une des options disponibles (mise à niveau et configuration pour la prise en charge de la messagerie vocale dans le Cloud, migrer vers Exchange Online ou tirer parti de la reprise mécanisme décrit plus haut).</li><li>Décidez si vous activez ou désactivez la transcription de la boîte vocale et le masquage des blasphèmes de transcription de la boîte vocale au sein de l’organisation ou pour des utilisateurs spécifiques.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, documentez les points de décision Exchange pour prendre en charge la messagerie vocale Cloud.</li><li>Si vous activez/désactivez la boîte vocale, la transcription de la boîte vocale et le masquage par inconvenances de transcription de la boîte vocale uniquement pour des utilisateurs spécifiques, documentez la liste des utilisateurs.</li></ul>|

> [!TIP]
> Les détails de la boîte vocale Cloud pour le système téléphonique avec l’implémentation des plans d’appels peuvent être documentés comme suit.
> 
> |Utilisateur |Boîte aux lettres Exchange |Activer la boîte vocale? |Transcription de la boîte vocale |Masquage de l’blasphème de transcription de la boîte vocale |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Oui |Activé |Activé |
> |Lidia Holloway   |Online      |Oui |Activé |Désactivé |
> |Louis Lahr       |Sur site |Oui |Activé |Activé |
> |Marcel Beauchamp |Sur site |Oui |Désactivé |S/O |
> |Rachelle Cormier |Online      |Oui |Désactivé |S/O |
> |Isabell Potvin   |Sur site |Oui |Désactivé |S/O |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Dans certains cas, il existe des exigences d’entreprise légitimes pour masquer l’ID de l’appelant afin de protéger l’identité des appelants à l’aide du numéro de ligne principale d’Office (il s’agit généralement d’un numéro de service desservi par le standard automatique) en tant qu’IDENTIFIant de l’appelant ou pour bloquer l’identification de l’appelant. présentation entièrement.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez s’il est nécessaire de manipuler l’identification de l’appelant pour votre implémentation de plans d’appel.</li><li>Le cas échéant, déterminez les types de manipulation d’ID d’appelant (masque avec numéro de service ou anonymat) à implémenter.</li><li>Le cas échéant, Déterminez quels utilisateurs nécessitent une manipulation d’identification d’appelant et le type de manipulation d’ID d’appelant à attribuer à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les utilisateurs auxquels une manipulation d’ID d’appelant est affectée et le type de manipulation d’ID d’appelant à attribuer.</li></ul>|

> [!TIP]
> Voici un exemple de documentation sur les détails du masquage de l’identification de l’appelant.
> 
> |Utilisateur  |Activer le masquage d’ID d’appelant sortant  |Type de masquage de l’identification de l’appelant  |Autoriser le remplacement de l’utilisateur  | Activer le masquage d’ID d’appelant entrant  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|Non|N/A|Oui|Non|
> |Lidia Holloway|Oui|Numéro de service (OrgAA, + 44 20 7946 0000)|Non|Oui|
> |Louis Lahr|Non|N/A|Oui|Non|
> |Marcel Beauchamp|Oui|Numéro de service (OrgAA TBA)|Non|Oui|
> |Rachelle Cormier|Oui|Anonymat|Oui|Non|
> |Isabell Potvin|Oui|Numéro de service (OrgAA TBA)|Non|Oui|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Gestion des licences pour les fonctionnalités vocales de Cloud

Les fonctionnalités d’audioconférence et de système téléphonique sont des fonctionnalités d’Office 365. Ils peuvent être sous licence séparément en tant que services de modules complémentaires pour les clients existants disposant d’offres d’abonnement à Office 365 E3 ou E1; ils sont déjà inclus dans le cadre du forfait d’abonnement Office 365 E5.

Forfaits d’appels est un module complémentaire de la fonctionnalité de système téléphonique dans Office 365, de sorte que vous devez disposer d’une licence de système téléphonique activée pour pouvoir utiliser des plans d’appels.

Pour la prise en charge des services d’audioconférence et de services d’appels audio supplémentaires (appel sortant de conférence internationale, les appels externes après les allocations de minute de plan d’appel sont épuisés, etc.), vous pouvez configurer les crédits de communication pour votre organisation.

## <a name="licensing-for-calling-plans"></a>Licences pour les offres d’appels

Si votre organisation envisagez d’utiliser Microsoft comme fournisseur de services de téléphonie, vous devez obtenir des modules complémentaires de plan d’appels adaptés aux besoins de vos utilisateurs. En règle générale, vous n’avez pas besoin de passer des appels internationaux à d’autres personnes, de sorte que vous pouvez configurer la plupart des utilisateurs avec des licences de plan d’appel national.

Il existe deux types de licences de plan d’appel:

-   Forfait d'appels nationaux

-   Forfait d'appels nationaux et internationaux

> [!NOTE]
> Ce qui est considéré comme «domestique» pour un utilisateur spécifique est déterminé par l’emplacement d’utilisation d’Office 365 affecté par l’utilisateur.

Chaque type de plan d’appels fournit une attribution de minutes d’appel que les utilisateurs peuvent utiliser par mois, pour passer des appels nationaux ou internationaux. Le forfait d’appels nationaux est inférieur au forfait d’appels nationaux et internationaux.

La flexibilité de l’abonnement et de l’attribution du type de plan d’appel le plus approprié pour les exigences métiers des utilisateurs individuels permet à votre organisation de contrôler les coûts de ses plans d’appel.

Pour chaque client Office 365, le nombre combiné de minutes d’appel est regroupé par pays ou région, et par type de plan d’appel. Lorsque le seuil des minutes d’appel mensuel pour le client est atteint, le service des plans d’appel (sauf pour les appels d’urgence) sera suspendu pendant le reste du mois. Le service forfaits d’appels sera automatiquement relancé le premier jour du mois suivant.

Vous pouvez configurer des crédits de communication pour votre organisation afin que les utilisateurs puissent passer des appels sortants une fois l’attribution des minutes d’appel épuisée sans avoir besoin d’attendre le cycle de facturation du mois suivant. De plus, les crédits de communication permettent aux utilisateurs d’avoir reçu le forfait d’appels nationaux pour passer des appels internationaux, qui sont ensuite facturés par le biais d’un modèle «payant à la minute».

Pour en savoir plus sur le système téléphonique et les offres d’appels, consultez les articles suivants:

-   [Système téléphonique](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Forfaits d’appel](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne dispose pas de la licence de système téléphonique requis, décidez si vous allez acquérir la licence du système téléphonique en accroissant vos abonnements Office 365 existants ou en acquérant le service de complément système téléphonique.</li><li>Déterminez quels utilisateurs nécessitent une licence de plan d’appel national et qui nécessitent une licence de plan d’appels nationaux et internationaux.</li><li>Décidez si vous aurez besoin de crédits de communication pour l’implémentation de vos plans d’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les groupes de divisions, services, bureaux ou utilisateurs vous devez attribuer une licence de système téléphonique à un plan d’appels nationaux ou à une offre d’appels nationaux et internationaux.</li></ul>|

> [!TIP]
> Vous pouvez utiliser l’exemple suivant pour documenter l’attribution de licence pour le système téléphonique avec les utilisateurs de forfaits d’appels.
> 
> |Utilisateur |Bureau |Licence Office 365 |Forfait d’appels |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux et internationaux |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, module complémentaire du système téléphonique |Forfait d'appels nationaux |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Forfait d'appels nationaux et internationaux |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, module complémentaire du système téléphonique |Forfait d'appels nationaux |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Crédits de communication

À l’aide de crédits de communication, vos utilisateurs peuvent se connecter à partir d’une réunion d’audioconférence pour ajouter une autre personne de n’importe où dans le monde (en dehors du pays d’origine de l’organisateur de la réunion). Vous pouvez configurer des crédits de communication pour votre organisation de manière à permettre aux utilisateurs de passer des appels sortants une fois qu’ils ont épuisé leur attribution de minutes d’appel, sans devoir attendre la fin du cycle de facturation du mois suivant. En outre, les crédits de communication permettent aux utilisateurs disposant d’un forfait d’appels nationaux de passer des appels internationaux, qui sont ensuite facturés par le biais d’un modèle «payant à la minute».

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Si votre organisation choisit d’utiliser la recharge automatique, vous déterminez la quantité optimale en mesurant l’utilisation réelle. Surveiller l’utilisation des crédits de communication au fil du temps et régler le montant de votre recharge selon vos besoins.

Pour la mise en œuvre de vos plans d’appel, vous pouvez contrôler l’utilisation des crédits de communication par utilisateur, ce qui vous permet de vous assurer que vous avez attribué ces crédits en fonction de vos besoins professionnels.

Pour en savoir plus sur les crédits de communication, voir [qu’est-ce que les crédits de communication?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si vous avez besoin de crédits de communication pour la mise en œuvre de votre audioconférence ou d’appels audio.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez la Division, le service, les bureaux ou les groupes d’utilisateurs pour lesquels vous souhaitez activer les crédits de communication.</li><li>Documentez vos crédits de communication pour votre implémentation de votre audioconférence ou de vos plans d’appel.</li></ul>|

> [!TIP]
> L’exemple suivant vous permet de documenter la liste d’attributions de crédits de communication pour les utilisateurs d’offres d’appels.
> 
> |Utilisateur |Bureau |Forfait d’appels |Crédits de communication |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Forfait d'appels nationaux et internationaux |Activé |
> |Lidia Holloway |32 London Bridge Street |Forfait d'appels nationaux |Désactivé |
> |Louis Lahr |32 London Bridge Street |Forfait d'appels nationaux |Activé |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |
> |Rachelle Cormier |39 quai du Président Roosevelt |Forfait d'appels nationaux et internationaux |Activé |
> |Isabell Potvin |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |

<br>

> [!TIP]
> Les numéros de téléphone de vos communications peuvent être documentés comme dans l’exemple suivant.
>
> |         |         |
> |---------|---------|
> |Montant initial|1 000 $|
> |Montant déclencheur|400 $|
> |Montant de la recharge automatique|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone vocaux Cloud

Si vous implémentez un système téléphonique en effectuant votre propre fournisseur de services de télécommunication, la gestion des numéros de téléphone restera en tout.

Pour les implémentations de conférences et d’appels audio, vous pouvez choisir d’acheter de nouveaux numéros de téléphone ou de transférer (porter) des numéros de téléphone existants.

Pour permettre aux utilisateurs de composer les numéros de téléphone tels qu’ils sont habitués (par exemple, omettre les indicatifs pour les appels locaux, omettre le code du pays pour les appels nationaux ou utiliser la numérotation à l’aide de numéros abrégés lors de l’exécution d’une conférence rendez-vous ou pour appeler d’autres utilisateurs au sein de l’organisation); vous pouvez configurer un plan de numérotation personnalisé et l’affecter aux utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquisition de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions Microsoft Cloud Voice sont les suivants:

-   Des numéros d’abonnés (utilisateurs), qui peuvent être attribués à des utilisateurs de votre organisation.

-   Les numéros de service, disponibles en tant que numéros de service gratuits ou payants, qui ont une plus grande capacité d’appel simultanée que les numéros d’abonné, peuvent être attribués à des services tels que les conférences audio, les standards automatiques ou les files d’attente d’appels.

Pour plus d’informations sur les types de numéros de téléphone, reportez-vous à [différents types de numéros de téléphone utilisés pour les offres d’appels](different-kinds-of-phone-numbers-used-for-calling-plans.md).

Le nombre total de numéros de téléphone que vous pouvez obtenir dépend du type de numéro de téléphone et du nombre de licences que vous avez achetées et attribuées à vos utilisateurs.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, voir [combien de numéros de téléphone pouvez-vous obtenir?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements ou les bureaux des utilisateurs dans lesquels de nouveaux numéros de téléphone seront achetés auprès de Microsoft.</li><li>Choisissez le type de numéro de téléphone à acquérir auprès de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements ou les bureaux des utilisateurs dans lesquels de nouveaux numéros de téléphone seront achetés auprès de Microsoft.</li><li>Documentez le type de numéro de téléphone à acquérir auprès de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transférer des numéros de téléphone existants

Si votre organisation souhaite transférer (ou porter) des numéros de téléphone existants à Microsoft, vous pouvez le faire en envoyant une demande de transfert à Microsoft.

Vous pouvez transférer tous vos numéros de téléphone existants à la fois (port complet) et, dans certains pays, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existants (port partiel). Un port partiel peut être utile dans les cas où vous souhaitez simplement déplacer progressivement vos utilisateurs vers un système téléphonique avec des plans d’appels.

Une demande de transfert unique peut uniquement transférer les numéros de téléphone vers un même type de numéro de téléphone. Si vous avez besoin de transférer certains de vos numéros de téléphone et d’autres en tant que numéros de service, nous vous recommandons de commencer par procéder au transfert vers Microsoft et de procéder à la conversion dès que les numéros sont dans le contrôle de Microsoft.

En guise d’alternative (si le port partiel est pris en charge), vous pouvez transmettre plusieurs demandes de port, une demande de port à la fois. Toutefois, cette approche peut prolonger votre contrat avec votre fournisseur de services de télécommunication existant.

Le portage des numéros de téléphone est un sujet complexe qui nécessite une planification et une coordination complètes, et la gestion appropriée des attentes des parties prenantes. Pour en savoir plus, consultez les articles suivants:

-   [Transfert de numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md)

-   [Transfert des questions fréquemment posées numéros de téléphone](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements ou les bureaux des utilisateurs dans lesquels les numéros de téléphone existants seront transférés vers Microsoft.</li><li>Choisissez le type de numéro de téléphone à transférer vers Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements ou les bureaux des utilisateurs dans lesquels les numéros de téléphone existants seront transférés vers Microsoft.</li><li>Documentez le type de numéro de téléphone à transférer vers Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un plan de numérotation dans la fonctionnalité système téléphonique d’Office 365 est un ensemble de règles de normalisation qui convertissent les numéros de téléphone numérotés dans un autre format (en général, le format E. 164) pour l’autorisation et le routage des appels. Le service d’audioconférence utilise les mêmes fonctionnalités utilisées par le système téléphonique pour traduire les numéros de téléphone de conférence rendez-vous dans les scénarios de numérotation de conférences (par exemple, invitez des participants via PSTN et Dial-moi).

Dans la fonctionnalité système téléphonique d’Office 365, il existe deux types de plans de numérotation:

-   **Plan de numérotation service:** Il s’agit du plan de numérotation par défaut qui est appliqué aux utilisateurs en fonction de leur emplacement d’utilisation d’Office 365 et ne peut pas être modifié.

-   **Plan de numérotation client:** Il s’agit d’un plan de numérotation personnalisable au sein d’un client, qui est divisée en deux types:

    -   **Client-plan de numérotation global:** Plan de numérotation qui s’applique à tous les utilisateurs du client.

    -   **Plan de numérotation de l’utilisateur:** Plan de numérotation s’appliquant uniquement à des utilisateurs spécifiques.

Le plan de numérotation efficace attribué aux utilisateurs est la combinaison du plan de numérotation service (en fonction de l’emplacement d’utilisation d’Office 365 d’un utilisateur) et du plan de numérotation client (qui peut être un client-plan de numérotation global ou un plan de numérotation de l’utilisateur).

Le ![tableau suivant présente trois combinaisons de plans de services et de numérotation client.] Le (media/audio_conferencing_image8.png "tableau suivant présente trois combinaisons de plans de services et de numérotation client.")

> [!IMPORTANT]
> Chaque plan de numérotation client peut comporter un maximum de 25 règles de normalisation. par conséquent, il est important de ne pas dupliquer les règles de normalisation déjà disponibles dans le cadre du plan de numérotation service.

Pour plus d'informations sur les plans d'appel, voir [Quels sont les plans de numérotation ?](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation nécessite des plans de numérotation personnalisés (exigences d’entreprise, exigences d’adoption, etc.).</li><li>Le cas échéant, déterminez l’étendue du plan de numérotation client (client-global ou utilisateur client) pour prendre en charge vos exigences relatives aux plans de numérotation personnalisés.</li><li>Le cas échéant, déterminez les plans de numérotation client que vous allez créer pour prendre en charge les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation de la voix Cloud.</li><li>Le cas échéant, Déterminez quels utilisateurs nécessitent un plan de numérotation personnalisé et le plan de numérotation client à attribuer pour chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de l’implémentation de la voix Cloud.</li><li>Documentez les utilisateurs auxquels vous voulez attribuer un plan de numérotation personnalisé et le plan de numérotation client à attribuer à chaque utilisateur.</li></ul>|

> [!TIP]
> S’il est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations du plan de numérotation client.
> 
> |Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^ (7-d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000-€ € "x8999) pour OMB Office, Singapour_|^ (8{3}<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^ (1? 800 p{7}) \d * $<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000-€ € "x7999) pour 39 quai du Président Roosevelt Office, Issy-aux-Moulineaux, France_|^ (7-d{3}) $<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0? (80 \n d{7}) \d * $<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1-d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>
> |Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
> |---------|---------|---------|---------|
> |Adele Vance|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Alex Wilber|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Ben Walters|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Christie Cline|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Debra Berger|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Lee Gu|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Louis Lahr|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions relatives au service de documents 

Utilisez les informations des sections précédentes de cet article pour documenter les décisions de votre service. En règle générale, cette documentation contient les sections principales suivantes:

-   Système téléphonique avec une liste de plans d’appel d’activation de site

-   Attribution de licence pour le système téléphonique avec les utilisateurs de forfaits d’appels

-   Numéros de planification de crédits de communication

-   Acquisition de numéro de téléphone, numéros de téléphone et informations de l’emplacement d’urgence

-   Détails de la configuration de la boîte vocale

-   Détails de la configuration du masquage de l’identification de l’appelant

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->