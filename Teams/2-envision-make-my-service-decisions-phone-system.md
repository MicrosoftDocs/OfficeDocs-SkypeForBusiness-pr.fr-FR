---
title: Rendre le système téléphonique des décisions service - Microsoft Teams en appelant des Plans
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Choisir parmi les plans d’appel et la gestion des licences, configurer les emplacements d’urgence et des fonctionnalités telles que les ID de la messagerie vocale et de l’appelant, acquérir ou transférer des numéros de téléphone.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1bf0d5514f4202029acabe44268e8e7e7d671f60
ms.sourcegitcommit: f76497a93dc3382c0ff2fc115c8f3e704097ab5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2018
ms.locfileid: "25597845"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de mon service

Pour planifier l’implémentation du système téléphonique technique avec des Plans de l’appel, vous devez apporter une série de décisions de service à l’avance afin de mieux préparer votre organisation pour implémenter une solution qui répond aux besoins de votre entreprise défini.

## <a name="calling-in-teams"></a>Appel dans Teams

Avec Microsoft Teams, vos utilisateurs peuvent passer et recevoir des appels vers ou depuis le réseau téléphonique commuté (RTC). Vos utilisateurs peuvent utiliser leurs propres numéros de téléphone dédié pour l’émission et réception d’appels téléphoniques nationales et internationales des applications clientes équipes, avec des fonctionnalités avancées qui incluent la messagerie vocale.

> [!NOTE]
> La feuille de route équipes le plus récent pour identifier les équipes téléphone système avec l’appel de planifier les fonctionnalités d’étendue pour votre déploiement, voir <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Système téléphonique dans les équipes

Pour les utilisateurs équipes pouvoir émettre et recevoir des appels RTC, ils doivent être activés pour le système téléphonique, une fonctionnalité d’Office 365.

Pour activer la connectivité au réseau RTC, votre organisation peut utiliser Microsoft en tant que son fournisseur de services de télécommunications. Finalement, vous aurez également l’option « apportez votre propre » un fournisseur de services de télécommunications pour activer la connectivité PSTN pour le système téléphonique.

> [!IMPORTANT]
> La possibilité d’utiliser votre propre fournisseur de services de télécommunications pour le système téléphonique avec votre déploiement équipes est également disponible avec le routage d’un système téléphonique Direct. Pour plus d’informations sur le routage Direct, veuillez consulter les [instructions de routage Direct](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Système téléphonique avec forfaits d’appels

Pour utiliser Microsoft comme votre fournisseur de télécommunications, vous devez obtenir des licences de l’appel de planifier et les attribuer aux utilisateurs de votre système téléphonique.

Il existe deux types principaux de plans d’appel :

-   Plan d’appel interne

-   Plan appelant nationale et international

Chaque type de planification de l’appelante alloue un certain nombre de minutes d’appel par mois pour chaque utilisateur qui a été affecté à la licence. Lors de l’allocation de minutes d’appel est atteint, l’utilisateur ne pourra passer des appels sortants, à l’exception des appels d’urgence — jusqu'à ce que le cycle de facturation du mois suivant. Si vous souhaitez que les utilisateurs puissent continuer à émettre des appels sortants une fois qu’ils ont atteint leur affectation de minutes d’appel, ou pour permettre aux utilisateurs qui disposent d’un plan d’appel nationale passer des appels internationaux, vous pouvez configurer les Communications crédits pour votre organisation.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilité des forfaits d'appels

Avant de planifier l’implémentation de l’appel des Plans dans les équipes, vérifiez que le service des Plans de l’appel est disponible dans votre région en examinant le [pays et région disponibilité pour la conférence Audio et des Plans de l’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison des contraintes juridiques, pour appeler des Plans soient disponibles pour les organisations multinationales, le contrat pour les abonnements Office 365 doit être basé dans votre pays ou région où le service des Plans de l’appel est disponible, ou bien où l’appel des Plans de service peut être acheté.

> [!NOTE]
> Si des Plans de l’appel ne sont pas disponibles dans votre région, vous pouvez utiliser le [Routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md) pour autoriser les utilisateurs à l’aide des équipes les fonctionnalités RTC.

Après avoir confirmé que votre organisation peut obtenir le service d’appel de Plans, compiler la liste des emplacements de l’utilisateur ou de bureaux où vous allez être implémentant le service des Plans de l’appel, en fonction de la liste des pays et régions disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements de l’utilisateur ou les bureaux, vous allez implémenter l’appel des Plans de service dans.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux à activer pour le service d’appel de Plans.</li></ul>|

> [!TIP]
> Voici un exemple d’un système téléphonique avec la liste des activation appelant des Plans de site.
> 
> | **Bureau**                     | **Emplacement**   | **Service de système téléphonique** |
> |--------------------------------|----------------|--------------------------|
> | 1 Eppîng Road                | Australie      | Service PSTN hérité |
> | 100 Cyberport Road             | Hong Kong R.A.S.  | Routage d’un système téléphonique Direct |
> | 1 Marina Boulevard           | Singapour      | Routage d’un système téléphonique Direct |
> | 32 London Bridge Street        | Royaume-Uni | Système téléphonique avec forfaits d’appels |
> | 39 quai du Président Roosevelt | France         | Système téléphonique avec forfaits d’appels |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec des Plans de l’appel dans Office 365, tous les utilisateurs de votre organisation doivent avoir un unique vers l’intérieur direct composer le numéro de téléphone (DID) et une adresse d’urgence validée correspondante. Passez en revue les [numéros de téléphone voix gérer dans le nuage](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) pour planifier l’acquisition de numéro de téléphone pour votre mise en œuvre des Plans de l’appel.

Lorsque vous configurez des numéros de téléphone pour appeler des Plans, vous devez affecter une adresse d’urgence pour chaque numéro de téléphone avant d’affecter le nombre à un utilisateur. Cela est obligatoire pour prendre en charge les appels d'urgence. L’adresse d’urgence doit être validée pour vous assurer qu’il se trouve dans le format correct pour être utilisé par les services d’urgence.

> [!IMPORTANT]
> Appel de Services d’urgence fonctionne différemment dans le service d’appel de Plans que dans les services téléphoniques traditionnels. Il est important de comprendre les différences et les communique à tous les utilisateurs. Pour plus d’informations, voir [Conditions et les termes du contrat de l’appel d’urgence](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/emergency-calling-terms-and-conditions) .

En plus de fournir une adresse d’urgence validée, vous pourrez définir des emplacements d’urgence et les associer à l’adresse validée en cas d’urgence pour donner à un emplacement plus précis au sein d’une adresse. Un emplacement d'urgence correspond généralement à un numéro de bâtiment, un étage, une aile de bâtiment ou un numéro de bureau où se trouve l'utilisateur.

Pour en savoir plus sur les emplacements d’urgence par rapport à l’appelant Plans, lisez les articles suivants :

-   [Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [Conditions générales relatives aux appels d'urgence](https://docs.microsoft.com/SkypeForBusiness/legal-and-regulatory/emergency-calling-terms-and-conditions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez la granularité des informations sur l’emplacement d’urgence à collecter pour les emplacements de l’utilisateur ou de bureaux dans la portée de l’implémentation des Plans de l’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les adresses d’urgence détaillées et les emplacements d’urgence pour chaque utilisateur ou office dans la portée de l’implémentation des Plans de l’appel.</li></ul>|

> [!TIP]
> Vous pouvez utiliser le modèle suivant pour documenter les détails des numéros de téléphone et les détails de l’emplacement en cas d’urgence.
> 
> |Utilisateur |Adresse et l’emplacement en cas d’urgence |Numéro de téléphone |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 London Bridge Street, Londres, SE1, Royaume-Uni |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 Londres pont rue, London, SE1, Royaume-Uni |+ 44 23 4567 89112 |
> |Louis Lahr |1023/32 London Bridge Street, Londres, SE1, Royaume-Uni |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
> |Rachelle Cormier |07N15D/39 quai du Président Roosevelt, Issy 92130-les-Moulineaux, France | TBA |
> |Isabell Potvin |07F05E/39 quai du Président Roosevelt, Issy 92130-les-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Messagerie vocale

Messagerie vocale de système téléphonique, grâce aux services de messagerie vocale Azure, prend en charge les dépôts de messagerie vocale pour les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.

Par défaut, la messagerie vocale système téléphonique fonctionne avec Exchange Online ; Toutefois il possède un minimum pris en charge Exchange sur site version et le déploiement modèle pour permettre la remise des messages vocaux pour les boîtes aux lettres dans le déploiement d’Exchange sur site.

La messagerie vocale du système téléphonique inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Besoins de votre entreprise peuvent nécessiter que vous désactivez la transcription de la messagerie vocale pour des utilisateurs spécifiques ou tout le monde dans toute l’organisation. Si votre organisation a décidé de conserver la transcription de la messagerie vocale activée, vous devez également prendre en compte si le masquage de la messagerie vocale transcription gratuites doivent être activés. Pour plus d’informations, voir [définition des stratégies de messagerie vocale dans votre organisation](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) .

>[!NOTE]
> Un mécanisme de secours a été implémenté, qui permet à la messagerie vocale du système téléphonique de renvoyer les messages via SMTP. Ainsi les utilisateurs qui possèdent une boîte aux lettres sur un système tiers recevront les messages vocaux. Ce mécanisme n’inclut pas les temps de fonctionnement de service garanti ou d’autres fonctionnalités de messagerie vocale, telle que la modification du message d’accueil de la messagerie vocale.

Pour plus d’informations sur la messagerie vocale dans une implémentation du système téléphonique, voir [messagerie vocale PBX Azure prend en charge pour Exchange Server](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si vous devez activer la messagerie vocale système téléphonique dans votre implémentation de Plans de l’appel.</li><li>Si l’aide d’Exchange sur site et votre déploiement existant ne répond pas à vos besoins pour prendre en charge le système téléphonique de la messagerie vocale, choisissez parmi les options disponibles (mise à niveau et d’installation pour la prise en charge de système téléphonique de la messagerie vocale, migrer vers Exchange Online ou exploiter les mécanisme de secours décrit plus haut).</li><li>Décider si vous activer ou désactiver la transcription de la messagerie vocale et masquage de gratuites transcription de la messagerie vocale dans toute l’organisation ou des utilisateurs spécifiques.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, les points de décision Exchange pour prendre en charge le système téléphonique de la messagerie vocale du document.</li><li>Si vous devez activer/désactiver le masquage gratuites de transcription de la messagerie vocale uniquement pour des utilisateurs spécifiques, transcription de la messagerie vocale et de la messagerie vocale, cette liste d’utilisateurs du document.</li></ul>|

> [!TIP]
> Détails de la messagerie vocale du système de téléphone pour le système téléphonique avec l’appel des Plans de mise en œuvre peut être documenté comme suit.
> 
> |Utilisateur |Boîte aux lettres Exchange |Activer la messagerie vocale ? |Transcription de la messagerie vocale |Masquage de la messagerie vocale transcription gratuites |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |En ligne      |Oui |Activé |Activé |
> |Lidia Holloway   |En ligne      |Oui |Activé |Désactivé |
> |Louis Lahr       |Local |Oui |Activé |Activé |
> |Marcel Beauchamp |Local |Oui |Désactivé |N/D |
> |Rachelle Cormier |En ligne      |Oui |Désactivé |N/D |
> |Isabell Potvin   |Local |Oui |Désactivé |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identité d'appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu'identité d'appel (ID de l'appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Dans certains cas, il existe des besoins légitimes pour masquer l’ID d’appelant pour protéger l’identité des appelants en utilisant le numéro de ligne principale office — il s’agit généralement d’un numéro de service pris en charge par la configuration du standard automatique — en tant qu’ID d’appelant ou bloquer des ID de l’appelant présentation entièrement.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si manipulation de l’ID de l’appelant est requise pour l’implémentation de Plans de l’appel.</li><li>Le cas échéant, déterminez les types de manipulation de l’ID de l’appelant (masque de numéro de service ou Anonymiser) à mettre en œuvre.</li><li>Le cas échéant, décider quels utilisateurs ont besoin de manipulation de l’ID de l’appelant et le type de manipulation de l’ID de l’appelant à affecter à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les utilisateurs pour disposer de manipulation de l’ID de l’appelant et le type de manipulation de l’ID de l’appelant pour affecter du document.</li></ul>|

> [!TIP]
> Voici un exemple de la documentation plus d’informations de masquage des ID de l’appelant.
> 
> |Utilisateur  |Activer le masquage de l'ID de l'appelant sortant  |Type de masquage de l'ID de l'appelant  |Autoriser le remplacement de l'utilisateur  | Activer le masquage de l'ID de l'appelant entrant  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|Non|N/A|Oui|Non|
> |Lidia Holloway|Oui|Numéro de service (OrgAA, +44 20 7946 0000)|Non|Oui|
> |Louis Lahr|Non|N/A|Oui|Non|
> |Marcel Beauchamp|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|
> |Rachelle Cormier|Oui|Anonymiser|Oui|Non|
> |Isabell Potvin|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Gestion des licences pour les fonctionnalités vocales de nuage

Conférence audio et système téléphonique sont les fonctionnalités d’Office 365. Ils peuvent être une licence séparée en tant que services de module complémentaire pour les clients disposant d’Office 365 E3 ou des plans d’abonnement E1 ; ils sont déjà inclus dans le cadre de la planification d’abonnement Office 365 E5.

Plans d’appel est un module complémentaire à la fonctionnalité de système téléphonique dans Office 365, vous devez disposer d’un système téléphonique sous licence activé à utiliser des Plans de l’appel.

Pour prendre en charge pour audioconférence supplémentaires et appel des Plans de cas (international conférence rendez-vous, externe à l’appel après épuisement des allocations minutes de planifier l’appel, etc.) d’utilisation, vous pouvez configurer les Communications crédits pour votre organisation.

## <a name="licensing-for-calling-plans"></a>Licence de forfaits d'appels

Si votre organisation envisage d’utiliser Microsoft comme fournisseur de services de télécommunications, vous devez obtenir l’appel de planifier les modules complémentaires appropriées aux besoins de vos utilisateurs. En règle générale, pas tout le monde dans une organisation doit passer des appels internationaux, afin que vous pouvez configurer la plupart des utilisateurs avec des licences nationales de planifier l’appel.

Deux types de licences de forfait d'appels sont disponibles :

-   Forfait d'appels nationaux

-   Forfait d'appels nationaux et internationaux

> [!NOTE]
> Le caractère « national » inhérent à un utilisateur spécifique est déterminé par l'emplacement d'utilisation d'Office 365 attribué à cet utilisateur.

Chaque type de forfait d'appels attribue des minutes d'appels nationaux ou internationaux aux utilisateurs sur une base mensuelle. Les coûts de planifier l’appel nationales qu'inférieur par rapport à l’International et nationales appelant planifier.

La flexibilité de l’abonnement et en affectant le type d’appel de planifier plus approprié pour les besoins des utilisateurs individuels permet de contrôler les coûts de son implémentation de l’appel des Plans de votre organisation.

Pour chaque client Office 365, le nombre de minutes d'appels combiné est regroupé par pays ou région et par type de forfait d'appels. Une fois que le client a atteint la limite de minutes d'appels mensuelles, le service de forfaits d'appels (à l'exception des appels d'urgence) est suspendu jusqu'à la fin du mois. Le service d’appel de Plans reprendra automatiquement sur le premier jour du mois suivant.

Vous pouvez définir des crédits Communications pour vos organisations pour permettre aux utilisateurs d’émettre des appels sortants une fois que l’allocation de l’appel de minutes épuisement sans devoir attendre le mois prochain cycle de facturation. En outre, crédits Communications donnent les utilisateurs affectés le Plan d’appel nationales la possibilité d’effectuer des appels internationaux, qui sont appliqués à l’aide d’un modèle « salaire par minute ».

Pour en savoir plus sur le système téléphonique et Plans de l’appel, lisez les articles suivants :

-   [Système téléphonique](https://products.office.com/skype-for-business/phone-system)

-   [Offres d'appels](https://products.office.com/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne possède pas la licence de système téléphonique nécessaire, décidez si vous permet d’acquérir la licence du système téléphonique par le renforcement de vos abonnements Office 365 existants ou à acquérir le service complémentaire système téléphonique.</li><li>Décider quels utilisateurs ont besoin d’une licence nationales appelant planifier et qui nécessitent une licence national et International appelant planifier.</li><li>Décider si vous devez crédits Communications pour votre mise en œuvre des Plans de l’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter la division, département, office ou vous allez attribuer une licence système téléphonique avec nationales appelant planifier ou nationales et International appelant planifier des groupes d’utilisateurs.</li></ul>|

> [!TIP]
> Vous pouvez utiliser l’exemple suivant l’attribution de licence pour le système téléphonique avec des utilisateurs d’appeler des Plans de document.
> 
> |Utilisateur |Bureau |Licence Office 365 |Appel de Plan |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux et internationaux |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, module complémentaire système téléphonique |Forfait d'appels nationaux |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Forfait d'appels nationaux et internationaux |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, module complémentaire système téléphonique |Forfait d'appels nationaux |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Crédits de communication

À l’aide de Communications crédits, vos utilisateurs peuvent composer à partir d’une réunion Conférence Audio pour ajouter quelqu'un à partir de n’importe où dans le monde (à l’extérieur de l’origine pays de l’organisateur de réunion). Vous pouvez définir des crédits Communications pour votre organisation pour permettre aux utilisateurs d’émettre des appels sortants après leur ont atteint leur affectation de l’appel de minutes, sans avoir à attendre la période de facturation du mois prochain. En outre, Communications crédits donner utilisateurs affectés avec le Plan de l’appel nationales la possibilité d’effectuer des appels internationaux, qui sont appliqués à l’aide d’un modèle « salaire par minute ».

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Si votre organisation décide d’utiliser recharge automatique, vous devez déterminer la quantité optimale par mesure de l’utilisation réelle. Surveiller l’utilisation de Communications crédits au fil du temps et ajuster votre recharge selon les besoins.

Pour votre implémentation de Plans de l’appel, vous pouvez contrôler l’utilisation de Communications crédits sur une base par utilisateur, qui vous permet de vérifier que vous avez attribué les crédits d’alignement avec les besoins de votre entreprise.

Pour en savoir plus sur les Communications crédits, passez en revue [Quelles sont les Communications crédits ?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si vous devez crédits Communications pour votre implémentation d’audioconférence ou des Plans de l’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les groupes division, département, office ou utilisateur, pour que vous devez ensuite activer Communications crédits du document.</li><li>Documenter votre planification Communications crédits votre implémentation d’audioconférence ou des Plans de l’appel.</li></ul>|

> [!TIP]
> L’exemple suivant vous permet de documenter la liste des affectations Communications générique pour les utilisateurs de Plans de l’appel.
> 
> |Utilisateur |Bureau |Appel de Plan |Crédits de communication |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Forfait d'appels nationaux et internationaux |Activé |
> |Lidia Holloway |32 London Bridge Street |Forfait d'appels nationaux |Désactivé |
> |Louis Lahr |32 London Bridge Street |Forfait d'appels nationaux |Activé |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |
> |Rachelle Cormier |39 quai du Président Roosevelt |Forfait d'appels nationaux et internationaux |Activé |
> |Isabell Potvin |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |

<br>

> [!TIP]
> Votre planification des numéros des crédits Communications pouvant être documentés comme dans l’exemple suivant.
>
> |         |         |
> |---------|---------|
> |Montant initial|1 000 $|
> |Montant déclencheur|400 $|
> |Montant de la recharge automatique|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone de voix dans le nuage

Si vous implémentez un système téléphonique en apportant votre propre fournisseur de services de télécommunications, gestion de numéros de téléphone reste-est.

Pour les implémentations de conférence Audio et des Plans de l’appel, vous pouvez choisir d’acquérir de nouveaux numéros de téléphone ou transférer des numéros de téléphone existants (port).

Permettent aux utilisateurs de composer des numéros de la façon dont ils êtes habitués à — comme omettant indicatifs pour les appels locaux, en omettant le code du pays pour les appels nationaux ou même à l’aide de numérotation short chiffres lors de la conférence rendez-vous ou l’appel des autres utilisateurs dans l’organisation : Vous pouvez configurer un plan de numérotation personnalisé et attribuez-le aux utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquérir de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions de voix dans le cloud Microsoft sont les suivants :

-   Numéros d’abonné (utilisateur), qui peuvent être affectés aux utilisateurs de votre organisation.

-   Numéros de service, disponibles en tant que numéro payant et numéros gratuits service, qui ont la capacité d’appels simultanés plus élevée que les numéros d’abonné et peuvent être affectés aux services tels que la conférence Audio, les standards automatiques ou files d’attente des appels.

Pour plus d’informations sur les types de numéros de téléphone, voir [différents types de numéros de téléphone utilisés pour les Plans de l’appel](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Le nombre total de numéros de téléphone que vous pouvez obtenir dépendent du type de numéro de téléphone et le nombre de licences que vous avez acheté et affecté à vos utilisateurs.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, voir [combien de numéros de téléphone peut obtenir ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements de l’utilisateur ou les bureaux où nouveaux numéros de téléphone seront acquis à partir de Microsoft.</li><li>Choisir le type de numéros de téléphone à acquérir de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où nouveaux numéros de téléphone seront acquis à partir de Microsoft.</li><li>Le type de numéros de téléphone à acquérir de Microsoft du document.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfert des numéros de téléphone existants

Si votre organisation souhaite transférer (ou le port) existante de numéros de téléphone à Microsoft, vous pouvez le faire en envoyant une demande de commande de port à Microsoft.

Vous pouvez transférer tous les vos numéros de téléphone existants à la fois (port complète), et, dans certains marchés, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existant (port partiel). Un port partiel peut être utile dans les cas où vous souhaitez simplement déplacer progressivement les utilisateurs au système téléphonique avec des Plans de l’appel.

Une commande port unique permettre transférer uniquement les numéros de téléphone à un type de numéro de téléphone unique. Si vous devez transférer certains de vos numéros de téléphone comme numéros d’abonné et d’autres en tant que numéro de service, nous vous recommandons d’abord effectuer le transfert à Microsoft puis effectuez la conversion dès qu’ils sont dans le contrôle de Microsoft.

Comme alternative (si le port partiel est pris en charge), vous pouvez envoyer plusieurs demandes de port, demande un port à la fois. Toutefois, cette méthode alternative sera prolonger votre contrat avec votre fournisseur de services de télécommunications existant.

Portage numéro de téléphone est un sujet complexe et nécessite une planification approfondie, coordination et correctement la gestion des attentes de votre des parties prenantes. Pour plus d’informations, voir les articles suivants :

-   [Transfert des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Questions fréquentes à propos du transfert de numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existant seront transférés vers Microsoft.</li><li>Choisir le type de numéros de téléphone à transférer à Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existant seront transférés vers Microsoft.</li><li>Le type de numéros de téléphone à transférer à Microsoft de document.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un Plan de numérotation dans la fonctionnalité de système téléphonique d’Office 365 est un ensemble de règles de normalisation qui traduisent composé des numéros de téléphone dans un autre format (généralement le format E.164) pour l’autorisation d’appel et le routage des appels. Le service de conférence Audio exploite les mêmes capacités utilisées par le système téléphonique pour traduire des numéros de téléphone composé dans les scénarios d’appel sortant de conférence (par exemple, inviter des participants via PSTN et numérotation, fonctionnalité « m’appeler »).

Dans la fonction système téléphonique d’Office 365, il existe deux types de plans de numérotation :

-   **Plan de numérotation Service :** Il s’agit de la valeur par défaut plan de numérotation est appliquée aux utilisateurs en fonction de leur emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.

-   **Client au plan de numérotation :** Il s’agit d’un plan de numérotation personnalisable au sein d’un client, ce qui est divisé en deux types :

    -   **Client globales plan de numérotation :** Le plan de numérotation qui s’applique à tous les utilisateurs dans le client.

    -   **Plan de numérotation utilisateur client :** Le plan de numérotation qui s’applique uniquement à certains utilisateurs.

Le plan de numérotation effectives attribué aux utilisateurs est la combinaison du plan de numérotation service (basé sur l’emplacement d’utilisation d’un utilisateur Office 365) et client de numérotation de plan (qui peut être un plan de numérotation global-client ou un plan de numérotation utilisateur client).

![Tableau présente trois combinaisons de service et les clients des plans de numérotation.] (media/audio_conferencing_image8.png "Tableau présente trois combinaisons de service et les clients des plans de numérotation.")

> [!IMPORTANT]
> Il peut y avoir un maximum de 25 règles de normalisation dans chaque plan de numérotation client ; Par conséquent, il est important éviter la duplication des règles de normalisation qui sont déjà disponibles dans le cadre du service de plan de numérotation.

Pour plus d’informations sur les plans de numérotation, voir [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation nécessite des plans de numérotation personnalisé (impératifs d’entreprise, configuration requise d’adoption et ainsi de suite).</li><li>Le cas échéant, décider de l’étendue du plan de numérotation client (client globale ou utilisateur client) pour prendre en charge votre configuration requise pour les plans de numérotation personnalisé.</li><li>Le cas échéant, déterminez les plans de numérotation client que vous créerez pour prendre en charge des bureaux ou emplacements de l’utilisateur dans la portée de l’implémentation de la voix dans le nuage.</li><li>Le cas échéant, décider quels utilisateurs ont besoin d’un plan de numérotation personnalisé et le plan de numérotation client pour être attribué à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les plans de numérotation personnalisé et les règles de normalisation associées à configurer dans le cadre de la mise en œuvre de la voix dans le nuage.</li><li>Les utilisateurs à affecter à un plan de numérotation personnalisé et le plan de numérotation client pour être attribué à chaque utilisateur du document.</li></ul>|

> [!TIP]
> Si elle est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations de plan de numérotation client.
> 
> |Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000 â « x 8999) pour office OMB, Singapour_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 d’â « x 7999) pour 39 quai du Président Roosevelt office, les Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

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

## <a name="document-service-decisions"></a>Décisions de service de document 

Utilisez les informations dans les sections précédentes de cet article pour documenter vos décisions de service. En règle générale, cette documentation contient les sections principales suivantes :

-   Liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels

-   Attribution d'une licence aux utilisateurs de système téléphonique avec forfaits d'appels

-   Numéros de planification de crédits de communication

-   Détails relatifs à l'acquisition des numéros de téléphone, aux numéros de téléphones et aux emplacements d'urgence

-   Détails sur la configuration de la messagerie vocale

-   Détails de la configuration du masquage de l'ID de l'appelant

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->