---
title: La configuration système téléphonique de votre organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Guide pas à pas détaillant la configuration du système téléphonique Teams pour votre organisation dans Microsoft 365.
ms.openlocfilehash: 7f5a29bc5d57d59cf8d63dbe1f61db18a906e110
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156899"
---
# <a name="set-up-phone-system-in-your-organization"></a>La configuration système téléphonique de votre organisation

Cet article fournit une feuille de route pour le contenu de la configuration du système téléphonique : la technologie de Microsoft pour activer le contrôle des appels et les fonctionnalités PBX (Private Branch Exchange) dans le cloud Microsoft 365. Des liens vers des informations plus détaillées sont disponibles à la fin de chaque étape.

Avant de lire cet article, assurez-vous que vous avez lu [Qu’est-ce que le système téléphonique](what-is-phone-system-in-office-365.md) et [voici ce que vous obtenez avec le système téléphonique](here-s-what-you-get-with-phone-system.md). Les deux derniers articles décrivent la configuration requise et les fonctionnalités du système téléphonique.

Cet article décrit les étapes suivantes :

- [Étape 1 : Acheter et attribuer une licence de système téléphonique](#step-1-buy-and-assign-a-phone-system-license)
- [Étape 2 : Choisir une option de connectivité RTC](#step-2-choose-a-pstn-connectivity-option)
- [Étape 3 : Obtenir des numéros de téléphone pour vos utilisateurs](#step-3-get-phone-numbers-for-your-users)
- [Étape 4 : Obtenir des numéros de téléphone pour les services](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Étape 5 : Si vous souhaitez configurer une file d’attente d’appels](#step-5-if-you-want-to-set-up-a-call-queue)
- [Étape 6 : Si vous souhaitez configurer un standard automatique](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Étape 7 : Configurer des crédits de communication pour les numéros gratuits](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Étape 1 : Acheter et attribuer une licence de système téléphonique

Pour attribuer une licence système téléphonique à un seul utilisateur, les étapes sont identiques à l’attribution d’une licence Microsoft 365. Vous pouvez également attribuer des licences à plusieurs utilisateurs en bloc. Pour plus d’informations sur les licences de système téléphonique disponibles et sur la façon d’acquérir et d’attribuer des licences, consultez les [licences de module complémentaire Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) et [les licences de module complémentaire Microsoft Teams](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Étape 2. Choisir une option de connectivité RTC

Pour permettre à vos utilisateurs d’effectuer et de recevoir des appels externes, vous devez connecter le système téléphonique au réseau téléphonique commuté (RTC). Microsoft propose plusieurs options pour se connecter au rtc, notamment :

- Forfait d’appels. Une solution tout-dans-le-cloud avec Microsoft comme opérateur RTC.

- Connect de l’opérateur. Si votre opérateur existant participe au programme Microsoft Operator Connect, il peut gérer les contrôleurs de frontière de session et les appels RTC pour vous.

- Routage direct. Utilisez votre propre opérateur RTC en connectant vos SBC au système téléphonique.

Pour plus d’informations sur toutes les options de connectivité, consultez [les options de connectivité RTC](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : Obtenir des numéros de téléphone pour vos utilisateurs

Avant de pouvoir configurer des utilisateurs de votre organisation pour passer et recevoir des appels téléphoniques, vous devez obtenir des numéros de téléphone pour eux.

Pour plus d’informations sur la gestion des numéros de téléphone pour vos utilisateurs, consultez les articles suivants. La façon dont vous gérez les nombres d’un utilisateur dépend de l’option de connectivité RTC que vous choisissez.

- [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md) : fournit une vue d’ensemble des types de numéros de téléphone avec des liens vers des articles spécifiques pour l’acquisition et la gestion des numéros en fonction de votre option de connectivité RTC.
Décrit les deux types de [numéros de téléphone utilisateur](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Affecter, modifier ou supprimer un numéro de téléphone pour un utilisateur](assign-change-or-remove-a-phone-number-for-a-user.md) : décrit comment attribuer et gérer les numéros de téléphone que vous avez acquis.

- [Nombre de numéros de téléphone que vous pouvez obtenir](how-many-phone-numbers-can-you-get.md) : décrit le nombre de numéros de téléphone que vous pouvez obtenir, en fonction des types de numéros de téléphone et des types de licences que vous avez achetés et attribués.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Étape 4 : Obtenir des numéros de téléphone pour les services (files d’attente d’appels, standards automatiques)

En plus d’obtenir des numéros de téléphone pour vos utilisateurs, vous pouvez acquérir des numéros de téléphone payants ou gratuits pour des services tels que les standards automatiques et les files d’attente d’appels. Un numéro de service peut gérer des centaines d’appels simultanément, tandis que le numéro de téléphone d’un utilisateur ne peut gérer que quelques appels simultanément.

Vous pouvez obtenir auprès de Microsoft des numéros de service inclus dans vos licences. Si vous disposez d’une connectivité RTC via Operator Connect ou le routage direct, vous pouvez utiliser les numéros de service fournis par votre propre opérateur ou opérateur.

Pour plus d’informations, consultez :

- [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md) : fournit une vue d’ensemble des types de numéros de téléphone avec des liens vers des articles spécifiques pour l’acquisition et la gestion des numéros en fonction de votre option de connectivité RTC.
Décrit les [numéros de téléphone de service](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponibles auprès de Microsoft qui sont inclus dans vos licences. Pour plus d’informations sur les numéros de service fournis par Operator Connect ou le routage direct, contactez votre fournisseur.

- [Nombre de numéros de téléphone que vous pouvez obtenir](how-many-phone-numbers-can-you-get.md) : décrit le nombre de numéros de téléphone que vous pouvez obtenir, en fonction des types de numéros de téléphone et des types de licences que vous avez achetés et attribués.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Étape 5 : Si vous souhaitez configurer une file d’attente d’appels

Les files d’attente d’appels incluent des messages d’accueil utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher l’agent d’appel disponible suivant pour gérer l’appel. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.

Pour plus d’informations sur les files d’attente d’appels, consultez [Créer une file d’attente d’appels](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Étape 6 : Si vous souhaitez configurer un standard automatique

Les standards automatiques permettent aux personnes qui appellent votre organisation de naviguer dans un système de menus pour les amener au service approprié, à la file d’attente d’appels, à la personne ou à l’opérateur approprié.

Pour plus d’informations sur la configuration des standards automatiques, consultez [Configurer un standard automatique](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Étape 7 : Configurer des crédits de communication pour les numéros gratuits

Si vous souhaitez utiliser des numéros gratuits avec Microsoft Teams, vous devez configurer des crédits de communication. Les appels gratuits sont facturés par minute et nécessitent un solde positif des crédits de communication.

Les crédits de communication sont un moyen pratique d’ajouter des numéros gratuits à utiliser comme suit :

- Avec les numéros de service pour les applications vocales, telles que les standards automatiques ou les files d’attente d’appels.

- Pour composer n’importe quel numéro de téléphone international lorsque vous disposez d’abonnements au forfait d’appels nationaux ou au-delà de ce qui est inclus dans un abonnement de forfait d’appels nationaux et internationaux.

- Pour composer et payer par minute une fois que vous avez épuisé votre allocation de minute mensuelle.

- Pour composer et payer par minute pour tous les appels sortants, si vous disposez d’un forfait d’appels avec paiement à l’utilisation.

Pour plus d’informations, consultez [Qu’est-ce que les crédits de communication ?](what-are-communications-credits.md) et [configurez les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).

## <a name="related-articles"></a>Articles connexes

- [Qu’est-ce que le système téléphonique ?](what-is-phone-system-in-office-365.md)

- [Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

- [Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-landing-page.md)
