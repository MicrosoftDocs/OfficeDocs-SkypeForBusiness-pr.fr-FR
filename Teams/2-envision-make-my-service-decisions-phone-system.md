---
title: Vérifiez le système téléphonique avec les Plans d’appel de la décision de service - Teams Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Choisissez dans les plans d’appel et les licences, configurer des emplacements d’urgence et les fonctionnalités telles que les ID de messagerie vocale et l’appelant, acquérir ou transférer des numéros de téléphone.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b7b1aaff60d6aa35fa10334c8d55e6a057eccaf
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de mon service

Pour planifier la mise en oeuvre technique de système téléphonique avec appel de PLans, vous devez effectuer une série de décisions de service à l’avance pour mieux préparer votre organisation pour implémenter une solution qui répond à vos besoins métier bien définis.

## <a name="calling-in-teams"></a>Appel dans Teams

Avec Microsoft Teams, vos utilisateurs peuvent émettre et recevoir des appels téléphoniques vers ou depuis le réseau téléphonique public commuté (RTPC). Vos utilisateurs peuvent utiliser leurs propres numéros de téléphone dédiés pour passer et recevoir des appels nationaux et internationaux à partir d’applications clientes équipes, avec des fonctionnalités avancées qui incluent des messages vocaux et appel d’urgence (911 amélioré).

> [!NOTE]
> Le planning actualisé des équipes pour identifier les équipes Phone System avec envisagez d’appeler des fonctions dans la portée de votre déploiement, vous pouvez trouver à <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Système de téléphone dans les équipes

Pour les utilisateurs des équipes pouvoir émettre et recevoir des appels PSTN, ils doivent être activés pour le système téléphonique, une fonctionnalité dans Office 365.

Pour activer la connectivité au RTC, votre organisation peut utiliser Microsoft en tant que son fournisseur de services de télécommunications. Finalement, vous aurez également l’option « apportez votre propre » un fournisseur de services de télécommunications pour activer la connectivité RTPC pour système téléphonique.

> [!IMPORTANT]
> La possibilité de choisir votre propre fournisseur de services de télécommunications pour système téléphonique seront disponible à l’avenir. Pour en savoir plus sur la barre de planning prévisionnel, veuillez consulter le [Skype pour entreprises à l’introduction de fonctionnalités équipes de Microsoft](https://aka.ms/skype2teamsroadmap).

## <a name="phone-system-with-calling-plans"></a>Système téléphonique avec forfaits d’appels

Pour utiliser Microsoft comme votre fournisseur de télécommunications, vous devez obtenir des licences de l’appel de planifier et de les affecter à des utilisateurs de votre système téléphonique.

Il existe deux principaux types de plans d’appel :

-   Plan d’appel interne

-   Plan d’appel nationaux et internationaux

Chaque type de plan d’appel alloue un certain nombre de minutes d’appel par mois pour chaque utilisateur qui a été attribué à la licence. Lors de l’allocation de minutes d’appel est épuisée, l’utilisateur ne sera pas en mesure d’effectuer des appels sortants, à l’exception des appels d’urgence, jusqu'à ce que le cycle de facturation du mois suivant. Si vous souhaitez que les utilisateurs puissent continuer à placer l’appel sortant même après leur avoir épuisé leur allocation de minutes de l’appel, ou pour permettre aux utilisateurs qui ont un plan d’appel interne à passer des appels internationaux, vous pouvez configurer les crédits de Communications pour votre organisation.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilité des forfaits d'appels

Avant de planifier la mise en oeuvre des Plans d’appel dans des équipes, vérifiez que le service d’appel de Plans est disponible dans votre région en passant en revue la [disponibilité de pays et de région pour les conférences Audio et les Plans d’appel](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> En raison des contraintes juridiques, pour appeler des Plans soient disponibles pour les organisations multinationales, le contrat pour les abonnements Office 365 doit être basé dans un pays ou une région où le service d’appel de Plans est disponible, ou dans le cas où le service d’appel de Plans peut être acheté.

Après avoir confirmé que votre organisation peut obtenir le service appel de Plans, établissez la liste des emplacements de l’utilisateur ou des bureaux où vous allez implémenter le service d’appel de Plans, basé sur la liste des pays et régions disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir les emplacements de l’utilisateur ou les bureaux, vous mettez en œuvre les Plans d’appel dans le service.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux à activer pour le service d’appel de Plans.</li></ul>|

> [!TIP]
> Voici un exemple d’un système de téléphone avec les Plans d’appel de liste prise en charge des sites.
>|Bureau   |Emplacement |Service du système téléphonique  |
>|---------|---------|---------|
>|1 Eppîng Road|Australie|Service PSTN hérité|
>|100 Cyberport Road|Hong Kong R.A.S.|Service PSTN hérité|
>|1 Marina Boulevard|Singapour|Service PSTN hérité|
>|32 London Bridge Street|Royaume-Uni|Système téléphonique avec forfaits d’appels|
>|39 quai du Président Roosevelt|France|Système téléphonique avec forfaits d’appels|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec l’appel de Plans dans Office 365, tous les utilisateurs de votre organisation doivent avoir un unique vers l’intérieur directe (DID) numéro de téléphone et une adresse de secours validée correspondante de numérotation. Vérifier les [numéros de téléphone vocal gérer cloud](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) pour planifier l’acquisition de numéro de téléphone pour votre mise en oeuvre de Plans d’appel.

Lorsque vous configurez des numéros de téléphone pour les Plans d’appel, vous devez affecter une adresse d’urgence pour chaque numéro de téléphone avant de vous attribuez le numéro à un utilisateur. Cela est obligatoire pour prendre en charge les appels d'urgence. L’adresse d’urgence doit être validé pour s’assurer qu’il est dans le format correct pour être utilisé par les services d’intervention d’urgence.

> [!IMPORTANT]
> Appel de Services d’urgence fonctionne différemment dans le service d’appel de Plans que dans les services téléphoniques traditionnels. Il est important que vous compreniez ces différences et les communique à tous les utilisateurs. Pour plus d’informations, reportez-vous à la section [Conditions et termes d’appel d’urgence](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions) .

En plus de fournir une adresse de secours validée, vous pouvez définir des emplacements d’urgence et les associer à l’adresse validée en cas d’urgence pour donner à un emplacement plus précis dans une adresse. Un emplacement d'urgence correspond généralement à un numéro de bâtiment, un étage, une aile de bâtiment ou un numéro de bureau où se trouve l'utilisateur.

Pour en savoir plus sur les emplacements d’urgence en ce qui concerne les Plans d’appel, consultez les articles suivants :

-   [Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [Conditions générales relatives aux appels d'urgence](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir la granularité d’urgence d’informations d’emplacement à percevoir pour les emplacements de l’utilisateur ou de bureaux dans la portée de la mise en oeuvre des Plans d’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>L’adresse de secours détaillée et emplacements d’urgence pour chaque utilisateur ou office dans la portée de la mise en oeuvre des Plans d’appel de document.</li></ul>|

> [!TIP]
> Vous pouvez utiliser le modèle suivant pour documenter les détails de numéros de téléphone et les détails de l’emplacement de secours.
>|Utilisateur |Adresse et l’emplacement de secours |Numéro de téléphone |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, Londres, SE1, Royaume-Uni |+ 44 23 4567 8901 |
>|Lidia Holloway |Pont de Londres 1065/32 rue, London, SE1, Royaume-Uni |+ 44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, Londres, SE1, Royaume-Uni |+ 44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Messagerie vocale

Messagerie vocale de système téléphonique, alimenté par les services de messagerie vocale d’Azure, prend en charge de la messagerie vocale des dépôts pour les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.

Par défaut, la messagerie vocale du système téléphonique fonctionne avec Exchange Online ; Toutefois a un minimum pris en charge Exchange sur site version modèle de déploiement et pour permettre l’envoi de messages de messagerie vocale aux boîtes aux lettres de l’utilisateur dans le déploiement de Exchange sur site.

La messagerie vocale du système téléphonique inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Besoins de votre entreprise peuvent vous demander de désactiver transcription de messagerie vocale pour des utilisateurs ou tout le monde au sein de l’organisation. Si votre organisation a décidé de conserver la transcription des messages vocaux activée, vous devez également envisager si masquage de grossièretés de transcription de messagerie vocale doivent être activés. Pour plus d’informations, consultez [définition des stratégies de messagerie vocale dans votre organisation](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) .

>[!NOTE]
> Un mécanisme de secours a été implémenté, qui permet à la messagerie vocale du système téléphonique de renvoyer les messages via SMTP. Ainsi les utilisateurs qui possèdent une boîte aux lettres sur un système tiers recevront les messages vocaux. Disponibilité du service de garantie ou autres fonctionnalités de messagerie vocale, telles que la modification des vœux de messagerie vocale ne comprend pas ce mécanisme.

Pour plus d’informations sur la messagerie vocale dans une mise en œuvre du système téléphonique, reportez-vous à la section [messagerie vocale du PBX d’Azure prend en charge pour Exchange Server](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si vous allez activer messagerie vocale du système téléphonique dans votre implémentation de Plans d’appel.</li><li>Si à l’aide d’Exchange en local et votre déploiement existant ne répond pas à vos exigences en matière de messagerie vocale du système téléphonique, choisissez parmi les options disponibles (mise à niveau et le programme d’installation de la prise en charge de la messagerie vocale système téléphonique, effectuer une migration vers Exchange en ligne ou exploitez la mécanisme de secours décrit plus haut).</li><li>Décidez si vous allez l’activer ou la désactiver transcription des messages vocaux et masquage de grossièretés transcription messagerie vocale dans toute l’entreprise ou pour des utilisateurs spécifiques.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, documenter les points de décision de Exchange pour prendre en charge de la messagerie vocale du système téléphonique.</li><li>Si vous allez activer/désactiver la messagerie vocale, transcription des messages vocaux et masquage de grossièretés de transcription de messagerie vocale uniquement pour des utilisateurs spécifiques, document de cette liste d’utilisateurs.</li></ul>|

> [!TIP]
> Détails de messagerie vocale de système téléphonique pour le système de téléphone avec la mise en oeuvre des Plans d’appel peuvent être décrite comme suit.
>|Utilisateur |Boîte aux lettres Exchange |Activer la messagerie vocale ? |Transcription de la messagerie vocale |Masquage des grossièretés de transcription de messagerie vocale |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |En ligne      |Oui |Activé |Activé |
>|Lidia Holloway   |En ligne      |Oui |Activé |Désactivé |
>|Louis Lahr       |Local |Oui |Activé |Activé |
>|Marcel Beauchamp |Local |Oui |Désactivé |N/D |
>|Rachelle Cormier |En ligne      |Oui |Désactivé |N/D |
>|Isabell Potvin   |Local |Oui |Désactivé |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identité d'appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu'identité d'appel (ID de l'appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Dans certains cas, il existe des besoins légitimes pour masquer l’ID de l’appelant pour protéger l’identité des appelants en utilisant le numéro de la ligne principale office — il s’agit généralement d’un numéro de service pris en charge par la configuration de Standard automatique : en tant qu’ID de l’appelant ou bloquer l’ID de l’appelant présentation complètement.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si la manipulation de l’ID de l’appelant est requise pour votre mise en oeuvre de Plans d’appel de.</li><li>Le cas échéant, déterminez les types de manipulation de l’ID de l’appelant (masque de numéro de service ou Anonymiser) à mettre en oeuvre.</li><li>Le cas échéant, décider quels utilisateurs ont besoin de manipulation de l’ID de l’appelant et le type de manipulation d’ID de l’appelant à être affecté à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les utilisateurs pour être affecté de manipulation de l’ID de l’appelant et le type de manipulation d’ID de l’appelant à affecter.</li></ul>|

> [!TIP]
> Voici un exemple de masquage de documentation de détails des ID de l’appelant.
>|Utilisateur  |Activer le masquage de l'ID de l'appelant sortant  |Type de masquage de l'ID de l'appelant  |Autoriser le remplacement de l'utilisateur  | Activer le masquage de l'ID de l'appelant entrant  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|Non|N/A|Oui|Non|
>|Lidia Holloway|Oui|Numéro de service (OrgAA, +44 20 7946 0000)|Non|Oui|
>|Louis Lahr|Non|N/A|Oui|Non|
>|Marcel Beauchamp|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|
>|Rachelle Cormier|Oui|Anonymiser|Oui|Non|
>|Isabell Potvin|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licences pour les fonctionnalités vocales de nuage

Audio conférence et système téléphonique sont des fonctionnalités dans Office 365. Ils peuvent être sous licence séparément en tant que services de module complémentaire pour les clients disposant d’Office 365 E3 ou programmes d’abonnement E1 ; ils sont déjà inclus dans le cadre de l’abonnement Office 365 E5.

Plans d’appel est un module complémentaire à la fonctionnalité du système téléphonique dans Office 365, vous devez disposer d’un système téléphonique sous licence activé pour utiliser des Plans d’appel.

Pour prendre en charge des conférences Audio supplémentaires et les Plans d’appel d’utilisent (conférence internationale des appels sortants, externe appelant après que l’appel de planifier les allocations minutes sont épuisées, etc.), vous pouvez définir des crédits de Communications pour votre organisation.

## <a name="licensing-for-calling-plans"></a>Licence de forfaits d'appels

Si votre organisation envisage d’utiliser Microsoft comme fournisseur de services de télécommunications, vous devez obtenir l’appel de planifier les modules complémentaires appropriées aux besoins de vos utilisateurs. En règle générale, pas tout le monde dans une organisation a besoin de placer des appels internationaux, afin que vous pouvez configurer la plupart des utilisateurs avec des licences d’appel Plan nationales.

Il existe deux types de licences de l’appel de Plan :

-   Forfait d'appels nationaux

-   Forfait d'appels nationaux et internationaux

> [!NOTE]
> Le caractère « national » inhérent à un utilisateur spécifique est déterminé par l'emplacement d'utilisation d'Office 365 attribué à cet utilisateur.

Chaque type de forfait d'appels attribue des minutes d'appels nationaux ou internationaux aux utilisateurs sur une base mensuelle. Les coûts nationaux appelant Plan qu'inférieur par rapport à l’International et domestiques Plan d’appel.

La souplesse d’abonnement et d’assigner le type de l’appel de planifier plus approprié pour les besoins des utilisateurs individuels aide votre entreprise à contrôler les coûts de sa mise en oeuvre des Plans d’appel.

Pour chaque client Office 365, le nombre de minutes d'appels combiné est regroupé par pays ou région et par type de forfait d'appels. Une fois que le client a atteint la limite de minutes d'appels mensuelles, le service de forfaits d'appels (à l'exception des appels d'urgence) est suspendu jusqu'à la fin du mois. Le service appel de Plans reprendra automatiquement le premier jour du mois civil suivant.

Vous pouvez configurer les crédits de Communications pour vos organisations pour permettre aux utilisateurs d’effectuer des appels sortants après épuisée de la répartition de l’appel de minutes sans avoir à attendre le mois prochain cycle de facturation. En outre, les crédits de Communications donnent les utilisateurs affectés le Plan d’appel interne la possibilité d’effectuer des appels internationaux, qui sont appliqués à l’aide d’un modèle de « paiement par minute ».

Pour plus d’informations sur le système téléphonique et les Plans d’appel, consultez les articles suivants :

-   [Système de téléphone](https://products.office.com/skype-for-business/phone-system)

-   [Plans d’appel](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne possède pas la licence requise de système téléphonique, décidez si vous pourrez d’acquérir la licence du système téléphonique par le renforcement de vos abonnements Office 365 existants ou en acquérant le service complémentaire de système téléphonique.</li><li>Décider quels utilisateurs ont besoin d’une licence nationale appelant Plan et qui nécessitent une licence domestiques et envisagez d’appel International.</li><li>Décider si vous devez les crédits de Communications pour votre mise en oeuvre de Plans d’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>La division, service, office ou groupes d’utilisateurs vous lui attribuez une licence de système téléphonique avec le Plan national appelant ou domestiques et d’International appelant Plan du document.</li></ul>|

> [!TIP]
> Vous pouvez utiliser l’exemple suivant pour l’attribution de licence pour système téléphonique avec les utilisateurs de Plans d’appel de document.
>|Utilisateur |Bureau |Licence Office 365 |Plan d’appel |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux et internationaux |
>|Lidia Holloway |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
>|Louis Lahr |32 London Bridge Street |Office 365 E5 |Forfait d'appels nationaux |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, module complémentaire du système téléphonique |Forfait d'appels nationaux |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Forfait d'appels nationaux et internationaux |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, module complémentaire du système téléphonique |Forfait d'appels nationaux |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Crédits de communication

À l’aide de crédits de Communications, vos utilisateurs peuvent composer à partir d’une réunion de l’audioconférence pour ajouter quelqu'un à partir de n’importe où dans le monde (en dehors du pays d’origine de l’organisateur de la réunion). Vous pouvez configurer les crédits de Communications de votre entreprise pour permettre aux utilisateurs d’effectuer des appels sortants après leur avoir épuisé leur allocation de l’appel de minutes, sans avoir à attendre que le cycle de facturation au mois suivant. En outre, les crédits de Communications donner les utilisateurs affectés par le Plan d’appel nationaux la possibilité d’effectuer des appels internationaux, qui sont appliqués à l’aide d’un modèle de « paiement par minute ».

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Si votre organisation choisit d’utiliser recharge automatique, vous devez déterminer la quantité optimale en mesurant l’activité réelle. Surveiller l’utilisation des crédits de Communications au fil du temps et ajuster le montant de votre recharge selon les besoins.

Pour votre mise en oeuvre des Plans d’appel, vous pouvez contrôler l’utilisation des crédits de Communications sur une base par utilisateur, ce qui vous permet de vous assurer que vous avez affecté ces crédits d’alignement avec les besoins de votre entreprise.

Pour en savoir plus sur les crédits des Communications, consultez [que sont les crédits de Communications ?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si vous devez crédits de Communications pour votre implémentation d’audioconférence ou des Plans d’appel.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les groupes de division, service, office ou utilisateur que vous allez activer des crédits de Communications pour des documents.</li><li>Votre plan de crédits de Communications pour votre implémentation d’audioconférence ou des Plans d’appel de document.</li></ul>|

> [!TIP]
> L’exemple suivant vous permet de documenter la liste d’affectation de crédits de Communications pour les utilisateurs de Plans d’appel.
>|Utilisateur |Bureau |Plan d’appel |Crédits de communication |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Forfait d'appels nationaux et internationaux |Activé |
>|Lidia Holloway |32 London Bridge Street |Forfait d'appels nationaux |Désactivé |
>|Louis Lahr |32 London Bridge Street |Forfait d'appels nationaux |Activé |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |
>|Rachelle Cormier |39 quai du Président Roosevelt |Forfait d'appels nationaux et internationaux |Activé |
>|Isabell Potvin |39 quai du Président Roosevelt |Forfait d'appels nationaux |Désactivé |

<br>
> [!TIP]
> Votre planification de numéros des crédits de Communications pouvant être documentés dans l’exemple suivant.
>|         |         |
>|---------|---------|
>|Montant initial|1 000 $|
>|Montant déclencheur|400 $|
>|Montant de la recharge automatique|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gérer les numéros de téléphone vocal de nuage

Si vous implémentez un système téléphonique en mettant votre propre fournisseur de services de télécommunications, gestion de numéro de téléphone reste-est.

Pour les implémentations d’audioconférence et Plans d’appel, vous pouvez choisir d’acquérir des nouveaux numéros de téléphone ou de transfert des numéros de téléphone existants (port).

Permettre aux utilisateurs de composer des numéros de la façon dont ils sont habitués à — en omettant les codes de zone pour les appels locaux, en omettant le code de pays pour les appels nationaux ou même à l’aide de courtes-chiffres lors de la conférence des appels sortants ou appeler d’autres utilisateurs de l’organisation : Vous pouvez configurer un plan de numérotation personnalisé et attribuez-le aux utilisateurs.

## <a name="acquire-new-telephone-numbers"></a>Acquérir de nouveaux numéros de téléphone

Les deux types de numéros de téléphone dans les solutions de voix de nuage de Microsoft sont les suivantes :

-   Numéros d’abonné (utilisateur), qui peuvent être assignés aux utilisateurs de votre organisation.

-   Numéros de service disponibles en tant que numéro payant et les numéros de service gratuit, qui ont la capacité d’appel simultané plus élevée que les chiffres de l’abonné et peuvent être affectés aux services d’audioconférence, des surveillances automatiques ou des files d’attente de l’appel.

Pour plus d’informations sur les types de numéros de téléphone, voir [différents types de numéros de téléphone utilisés pour les Plans d’appel](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Le nombre total de numéros de téléphone que vous pouvez obtenir dépendent du type de numéro de téléphone et le nombre de licences que vous avez achetés et affectées à vos utilisateurs.

Pour plus d’informations sur le nombre total de numéros de téléphone que vous pouvez obtenir, consultez [le nombre de numéros de téléphone vous obtiendrez ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir les emplacements de l’utilisateur ou les bureaux où les nouveaux numéros de téléphone seront sont acquis à partir de Microsoft.</li><li>Choisir le type de numéros de téléphone à acquérir auprès de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les nouveaux numéros de téléphone seront sont acquis à partir de Microsoft.</li><li>Le type de numéros de téléphone à acquérir de Microsoft de document.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfert des numéros de téléphone existant

Si votre organisation souhaite de transfert (ou port) existant à Microsoft, les numéros de téléphone, vous pouvez le faire en envoyant une demande de commande de port à Microsoft.

Vous pouvez transférer tous vos existant téléphone numéros à la fois (port complet), et, sur certains marchés, vous pouvez transférer un sous-ensemble de vos numéros de téléphone existant (port partielle). Un port partiel peut être utile dans les cas où vous souhaitez que vos utilisateurs se déplacent progressivement au système téléphonique avec des Plans d’appel.

Une commande port unique peut uniquement transférer les numéros de téléphone à un type de numéro de téléphone unique. Si vous devez transférer certaines de vos numéros de téléphone sous forme de numéros de l’abonné, ainsi que sous forme de numéros de service, nous vous recommandons que vous tout d’abord complétez le transfert à Microsoft et que vous effectuez la conversion dès qu’ils sont dans le contrôle de Microsoft.

Comme alternative (si le port partielle est pris en charge), vous pouvez soumettre plusieurs demandes du port, demande un port à la fois. Toutefois, cette approche alternative de se prolonger votre contrat avec votre fournisseur de services de télécommunications existants.

Portage numéro de téléphone est un sujet complexe et requiert une planification minutieuse, de coordination et suffisamment gestion des attentes de vos parties prenantes. Pour plus d’informations, consultez les articles suivants :

-   [Transfert des numéros de téléphone à Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Questions fréquentes à propos du transfert de numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisir les emplacements utilisateur ou les bureaux où les numéros de téléphone existants seront transférés à Microsoft.</li><li>Choisir le type de numéros de téléphone pour être transférés à Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux où les numéros de téléphone existants seront transférés à Microsoft.</li><li>Le type de numéros de téléphone pour être transférés à Microsoft de document.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Plan de numérotation

Un Plan de numérotation dans la fonction système téléphonique d’Office 365 est un ensemble de règles de normalisation qui traduisent composé des numéros de téléphone dans un autre format (en général le format E.164) pour le routage des appels et l’autorisation d’appel. Le service d’audioconférence exploite les mêmes fonctionnalités que celui utilisées par le système téléphonique pour convertir les numéros de téléphone composés dans les scénarios d’appel sortant de conférence (par exemple, inviter des participants via RTPC et accès à distance, fonction de « call me »).

Dans la fonction système téléphonique d’Office 365, il existe deux types de plans de numérotation :

-   **Plan d’appel de Service :** Il s’agit de la valeur par défaut plan de numérotation qui est appliquée aux utilisateurs en fonction de leur emplacement de l’utilisation d’Office 365, et il ne peut pas être modifié.

-   **Plan d’appel de clients :** Il s’agit d’un plan d’appel personnalisables dans un client, ce qui est divisé en deux types :

    -   **Plan de numérotation de clients globale :** Le plan de numérotation qui s’applique à tous les utilisateurs dans le locataire.

    -   **Plan de numérotation de client-utilisateur :** Le plan de numérotation qui s’applique uniquement à certains utilisateurs.

Plan de numérotation effectives attribué aux utilisateurs est la combinaison du service à distance plan (basé sur l’emplacement d’utilisation d’un utilisateur Office 365) et plan (qui peut être un plan de numérotation globale locataire ou un plan de numérotation de client-utilisateur) d’appel des clients.

![Tableau montre trois combinaisons de service et les clients des plans de numérotation.] (media/audio_conferencing_image8.png "Tableau montre trois combinaisons de service et les clients des plans de numérotation.")

> [!IMPORTANT]
> Il peut y avoir un maximum de 25 règles de normalisation dans chaque plan de numérotation de clients ; Par conséquent, il est important d’éviter de dupliquer les règles de normalisation qui sont déjà disponibles dans le cadre du service de plan de numérotation.

Pour plus d’informations sur les plans de numérotation, consultez [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si votre organisation requiert que les plans de numérotation personnalisé (besoins, exigences en matière d’adoption et ainsi de suite).</li><li>Le cas échéant, décider de la portée du plan d’accès clients (clients-global ou locataire utilisateur) pour prendre en charge vos besoins en matière de plans de numérotation personnalisé.</li><li>Le cas échéant, décider de plans de numérotation de clients que vous allez créer pour prendre en charge des bureaux ou des emplacements de l’utilisateur dans la portée de la mise en oeuvre des voix de nuage.</li><li>Le cas échéant, décider que les utilisateurs qui nécessitent un plan de numérotation personnalisé et le plan de numérotation de clients à affecter pour chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les plans de numérotation personnalisé et les règles de normalisation associé à configurer dans le cadre de la mise en oeuvre des voix de nuage.</li><li>Documenter les utilisateurs pour être affecté à un plan de numérotation personnalisé et le plan de numérotation de clients à affecter pour chaque utilisateur.</li></ul>|

> [!TIP]
> S’il est applicable à votre projet, vous pouvez utiliser le modèle suivant pour documenter les configurations de plan d’accès clients.
>|Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000 â « x 8999) pour office OMB, Singapour_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 â €« x 7999) pour 39 quai du Président Roosevelt office Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>|Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
>|---------|---------|---------|---------|
>|Adele Vance|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Alex Wilber|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Ben Walters|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
>|Christie Cline|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Debra Berger|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Lee Gu|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Louis Lahr|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions de service de document 

Utilisez les informations dans les sections précédentes de cet article pour documenter vos décisions de service. En général, cette documentation contient les sections suivantes :

-   Liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels

-   Attribution d'une licence aux utilisateurs de système téléphonique avec forfaits d'appels

-   Numéros de planification de crédits de communication

-   Détails relatifs à l'acquisition des numéros de téléphone, aux numéros de téléphones et aux emplacements d'urgence

-   Détails sur la configuration de la messagerie vocale

-   Affectations de paramètres de pont de téléconférence

-   Détails de la configuration du masquage de l'ID de l'appelant

-   Plans de numérotation de client

-   Affectations du plan de numérotation

<!--ENDOFSECTION-->