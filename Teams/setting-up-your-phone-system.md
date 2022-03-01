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
description: Guide détaillé détaillant la façon de configurer des Teams Système téléphonique pour votre organisation dans Microsoft 365.
ms.openlocfilehash: 1a8f7ed554a360b94e568058be29697c0f2b1767
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039982"
---
# <a name="set-up-phone-system-in-your-organization"></a>La configuration système téléphonique de votre organisation

Cet article fournit une feuille de route vers le contenu pour la configuration de la technologie Système téléphonique-Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités des Exchange de branche privée (PBX) dans le cloud Microsoft 365. Des liens vers des informations plus détaillées sont disponibles à la fin de chaque étape. 

Avant de lire cet article, assurez-vous de lire ce qui est [Système téléphonique](what-is-phone-system-in-office-365.md) et voici ce que vous obtenez [de Système téléphonique](here-s-what-you-get-with-phone-system.md). Les deux derniers articles décrivent Système téléphonique et fonctionnalités requises.    

Cet article décrit les étapes suivantes : 

- [Étape 1 : acheter et attribuer une licence Système téléphonique licence](#step-1-buy-and-assign-a-phone-system-license)  
- [Étape 2 : choisir une option de connectivité PSTN](#step-2-choose-a-pstn-connectivity-option) 
- [Étape 3 : obtenir des numéros de téléphone pour vos utilisateurs](#step-3-get-phone-numbers-for-your-users)
- [Étape 4 : obtenir des numéros de téléphone pour les services](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Étape 5 : si vous voulez configurer une file d’attente d’appels](#step-5-if-you-want-to-set-up-a-call-queue) 
- [Étape 6 : si vous voulez configurer un attendant automatique](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [Étape 7 : configurer les crédits de communication pour les numéros gratuits](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Étape 1 : acheter et attribuer une licence Système téléphonique licence

Pour attribuer une licence Système téléphonique utilisateur à un seul utilisateur, les étapes sont identiques à l’attribution d’Microsoft 365 licence. Vous pouvez également attribuer des licences à plusieurs utilisateurs en bloc. Pour plus d’informations sur les licences Système téléphonique disponibles et la manière d’acquérir et d’attribuer des licences, voir  [Teams licences](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de module complémentaire et Attribuer Microsoft Teams des [licences de module complémentaire](/teams-add-on-licensing/assign-teams-add-on-licenses.md).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Étape 2. Choisir une option de connectivité RSTN 
 
Pour permettre à vos utilisateurs d’effectuer et de recevoir des appels externes, vous devez vous Système téléphonique au réseau téléphonique commuté (PSTN). Microsoft propose plusieurs options pour la connexion au réseau PSTN, notamment : 

- Forfait d’appels. Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN. 

- Opérateur Connecter. Si votre opérateur existant participe au programme de gestion des Connecter d’opérateur Microsoft, il peut gérer les contrôleurs de session et d’appel PSTN pour vous. 

- Routage direct. Utilisez votre propre opérateur PSTN en connectant vos SBCs à Système téléphonique. 

Pour plus d’informations sur toutes les options de connectivité, voir [les options de connectivité PSTN](pstn-connectivity.md).   

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : obtenir des numéros de téléphone pour vos utilisateurs

Avant de pouvoir configurer les utilisateurs de votre organisation de sorte qu’ils passer et recevoir des appels téléphoniques, vous devez obtenir des numéros de téléphone pour eux.

Pour plus d’informations sur la gestion des numéros de téléphone pour vos utilisateurs, consultez les articles suivants. La façon dont vous gérez les numéros d’un utilisateur dépend de l’option de connectivité PSTN que vous choisissez.   

- [Gérer les numéros de téléphone](manage-phone-numbers-landing-page.md) pour votre organisation – Fournit une vue d’ensemble des types de numéros de téléphone avec des liens vers des articles spécifiques pour l’acquisition et la gestion des numéros en fonction de votre option de connectivité PSTN. Décrit les deux types de numéros [de téléphone des utilisateurs](manage-phone-numbers-landing-page.md#user-telephone-numbers). 
 
- [Attribution, modification ou suppression du](assign-change-or-remove-a-phone-number-for-a-user.md) numéro de téléphone d’un utilisateur : décrit comment attribuer et gérer les numéros de téléphone que vous avez acquis. 
 
- [Combien de numéros](how-many-phone-numbers-can-you-get.md) de téléphone pouvez-vous obtenir – Décrit le nombre de numéros de téléphone que vous pouvez obtenir en fonction des types de numéros de téléphone et des types de licences que vous avez achetées et attribuées. 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Étape 4 : obtenir des numéros de téléphone pour les services (files d’attente d’appels, files d’attente automatiques)

Outre l’obtention de numéros de téléphone pour vos utilisateurs, vous pouvez acquérir des numéros de téléphone gratuits ou gratuits pour des services tels que les postes de transport automatique et les files d’attente d’appels. Un numéro de service peut gérer des centaines d’appels simultanément, tandis que le numéro de téléphone d’un utilisateur ne peut gérer que quelques appels en même temps.   

Vous pouvez obtenir des numéros de service de Microsoft inclus dans votre licence. Si vous avez une connectivité RSTN via l’Connecter ou le routage direct, vous pouvez utiliser les numéros de service fournis par votre propre opérateur ou opérateur. 

Pour plus d’informations, consultez :

- [Gérer les numéros de téléphone](manage-phone-numbers-landing-page.md) pour votre organisation – Fournit une vue d’ensemble des types de numéros de téléphone avec des liens vers des articles spécifiques pour l’acquisition et la gestion des numéros en fonction de votre option de connectivité PSTN.  
Décrit les [numéros de téléphone de service](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponibles auprès de Microsoft inclus dans votre licence. Pour plus d’informations sur les numéros de service fournis par l’Connecter ou le routage direct, contactez votre fournisseur. 

- [Combien de numéros](how-many-phone-numbers-can-you-get.md) de téléphone pouvez-vous obtenir – Décrit le nombre de numéros de téléphone que vous pouvez obtenir en fonction des types de numéros de téléphone et des types de licences que vous avez achetées et attribuées. 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Étape 5 : si vous voulez configurer une file d’attente d’appels

Les files d’attente d’appels incluent des salutations qui sont utilisées lorsque quelqu’un appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel. Vous pouvez créer une ou plusieurs files d’attente pour votre organisation. 

Pour plus d’informations sur les files d’attente d’appels, voir [Créer une file d’attente d’appels](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Étape 6 : si vous voulez configurer un attendant automatique

Les employés automatiques peuvent parcourir un système de menus pour accéder au service, à la file d’attente d’appels, au personnel ou à l’opérateur qui leur sont proposés.  

Pour plus d’informations sur la configuration des attendants automatiques, voir  [Définir un attendant automatique](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Étape 7 : configurer les crédits de communication pour les numéros gratuits

Si vous voulez utiliser des numéros gratuits avec Microsoft Teams, vous devez configurer les crédits de communication. Les appels gratuits sont facturés par minute et un solde de crédits de communication positif est nécessaire. 

Les crédits de communication sont un moyen pratique d’ajouter des numéros gratuits à utiliser comme suit : 

- Avec des numéros de service pour les applications vocales, telles que les files d’attente automatiques ou les files d’attente d’appels. 

- Pour composer un numéro de téléphone international si vous avez des abonnements à l’offre Appels nationaux ou au-delà de ce qui est inclus dans un abonnement de plan d’appels nationaux et internationaux. 

- Pour appeler et payer par minute une fois que vous avez épuisé votre allotment de minutes mensuelles. 

Pour plus d’informations,  [voir Quel est le crédit de communication ?](what-are-communications-credits.md) et [configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Sujets associés

- [Qu’est-ce que le système téléphonique ?](what-is-phone-system-in-office-365.md)

- [Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

- [Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-landing-page.md)


    
  
 
