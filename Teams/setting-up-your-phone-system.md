---
title: La configuration système téléphonique de votre organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
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
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Guide détaillé détaillant la façon de configurer Phone System (PBX cloud) pour votre organisation dans Microsoft 365 ou Office 365.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701212"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurer le système téléphonique dans votre organisation

Voici un guide étape par étape pour la configuration de Phone System dans Microsoft 365 ou Office 365. Des liens vers des informations détaillées supplémentaires sont disponibles à la fin de chaque étape.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Étape 1 : Vérifiez que le système téléphonique est disponible dans votre pays ou région

1.    Tout d’abord accéder à la [disponibilité de pays et de région pour conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)et sélectionnez votre pays ou région dans la liste en haut de la page. 
2.    Sous **Système téléphonique**, passez en revue la liste des fonctionnalités et les détails. 
3.    Si le système téléphonique est disponible, passez à l’étape 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Étape 2 : Acheter et affecter des licences système téléphonique et plans d’appel

Pour affecter une licence de système téléphonique et de plan d’appel à un seul utilisateur, les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365.  Vous pouvez également attribuer des licences à plusieurs utilisateurs en bloc. Pour plus d’informations, [voir Attribuer des licences de module complémentaire Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

Si les forfaits d’appels ne sont pas disponibles pour votre pays ou région, utilisez le routage direct pour connecter votre infrastructure téléphonique locale au système téléphonique.  Pour plus d’informations, [voir Routage direct du système téléphonique.](direct-routing-landing-page.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : obtenir des numéros de téléphone pour vos utilisateurs

Avant de pouvoir configurer les utilisateurs de votre organisation de sorte qu’ils passer et recevoir des appels téléphoniques, vous devez obtenir des numéros de téléphone pour eux.

Vous pouvez obtenir des numéros de trois façons différentes pour vos utilisateurs :
- Obtenez de nouveaux numéros à l’aide du Centre d’administration Teams.
- Obtenez de nouveaux numéros qui ne sont pas disponibles dans le Centre d’administration Teams.
- Transférez vos numéros existants de votre fournisseur de services ou de votre opérateur de téléphonie actuel vers Microsoft 365 ou Office 365.

Vous devez utiliser la page **Ajouter des nombres** pour voir, rechercher et acquérir ces nombres. Vous pouvez effectuer une recherche par pays/région, état et ville, puis entrer le nombre de numéros de téléphone dont vous aurez besoin pour vos utilisateurs.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Obtenir de nouveaux numéros de téléphone utilisateur à l’aide du Centre d’administration Teams

1. Connectez-vous à Microsoft 365 à l’aide de votre compte scolaire ou scolaire.

2. Allez dans le **Centre d’administration Teams.**
    
3. Dans le navigation de gauche, cliquez sur **Numéros** de téléphone vocal, cliquez sur  >  Ajouter, puis suivez les invites. 
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtenir de nouveaux numéros qui ne sont pas disponibles dans le Centre d’administration Teams
  
Parfois (en fonction de votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros à l’aide du Centre d’administration Teams. Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer. Pour savoir comment demander de nouveaux numéros d’utilisateur, [consultez Gérer les numéros de téléphone pour votre organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Transfert de vos numéros de téléphone du fournisseur de services ou de l'opérateur de téléphonie
  
- Si vous avez besoin d’au moins 999  numéros de téléphone pour vos utilisateurs, vous pouvez utiliser l’Assistant Demande de ports de nouveaux numéros locaux dans le Centre d’administration Teams. Suivez les étapes de la procédure de [transfert de numéros de téléphone vers Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) pour transférer vos numéros de téléphone.
    
- Si vous devez porter plus de 999 numéros de téléphone, voir Gérer les numéros de téléphone pour votre organisation afin d’envoyer une demande ou une demande de service de demande de port. [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

Pour plus d’informations sur l’obtention de nouveaux numéros de téléphone ou de transfert de numéros existants, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 4 : Obtenir les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

Outre l’obtention de numéros de téléphone pour vos utilisateurs à partir de Microsoft 365 ou Office 365, vous pouvez rechercher et acquérir des numéros de téléphone gratuits ou gratuits pour des services tels que l’audioconférence (pour les ponts de conférence), les serveurs automatiques et les files d’attente d’appels. Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d’appels simultanément, alors qu’un numéro de téléphone d’utilisateur ne peut gérer que quelques appels à la fois.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Obtenir de nouveaux numéros de service à l’aide du Centre d’administration Teams


1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Allez dans le **Centre d’administration Teams.**

3. Dans le volet de navigation gauche, cliquez sur **Ajouter** un nouveau numéro de téléphone vocal, puis cliquez  >    >  sur **Nouveau numéro de service.**

    > [!IMPORTANT]
    > Pour que l’option Voix s’offre à vous dans le volet de navigation gauche du  Centre d’administration Teams, vous devez d’abord acheter au moins une licence **Entreprise E5,** une licence de module module logiciel phone ou une licence de module de conférence  **audio.**

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtenir de nouveaux numéros qui ne sont pas disponibles dans le Centre d’administration Teams
  
Parfois (en fonction de votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros à l’aide du Centre d’administration Teams. Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer. Pour savoir comment demander de nouveaux numéros, voir Gérer les numéros [de téléphone pour votre organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>Transférer des numéros de service existants

Si vous voulez transférer des numéros de service depuis votre fournisseur ou opérateur de services actuel, vous devez envoyer une demande de transfert manuellement à Microsoft. Vous devez envoyer des demandes de transfert distinctes pour chaque type de numéro de service (gratuit ou gratuit) que vous transférez à l’aide d’une lettre d’autorisation (LOA). Dans la lettre d’autorisation (LOA), vous devez sélectionner le type de numéro de service correct. Lorsque vous contactez le support Microsoft, spécifiez que vous transférez un numéro de service *(et* non un numéro d’utilisateur ou d’abonné), ou que la capacité d’appels simultanés peut ne pas être suffisante pour gérer les volumes d’appels. Si vous souhaitez transférer les numéros de téléphone ou effectuer d’autres opérations avec vos numéros de téléphone, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Étape 5 : Si vous souhaitez configurer des Plans d’appel

Si vous avez suivi les étapes ci-dessus, vous avez déjà acheté et affecté du système téléphonique, les licences et un Plan d’appel (étape 2) et acquis des numéros de téléphone pour vos utilisateurs (étape 3), donc votre plan d'appel est partiellement configuré. Pour suivre les procédures de configuration d’un forfait d’appels, [consultez Configurer les forfaits d’appels.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Étape 6 : Si vous souhaitez configurer la conférence Audio

Parfois, des personnes de votre organisation devront utiliser un téléphone pour rejoindre une réunion. Microsoft Teams inclut la fonctionnalité d’audioconférence pour cette situation uniquement. Les personnes peuvent se rendre aux réunions Teams à l’aide d’un téléphone, au lieu d’utiliser l’application Teams sur un appareil mobile ou un PC.
Pour plus d’informations sur la façon de configurer l’audioconférence, consultez [Configurer l’audioconférence pour Teams.](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Étape 7 : si vous voulez configurer une file d’attente d’appels dans le cloud

Les files d’attente d’appels cloud incluent des salutations qui sont utilisées lorsque quelqu’un appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel pendant que l’appelant écoute la musique mise en attente. Vous pouvez créer une ou plusieurs files d’attente pour votre organisation.

Pour plus d’informations sur les files d’attente d’appels, voir [Créer une file d’attente d’appels cloud.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Étape 8 : si vous voulez configurer un attendant automatique dans le cloud

Les employés automatiques peuvent appeler votre organisation et parcourir un système de menus pour accéder au service, à la file d’attente d’appels, au personnel ou à l’opérateur qui leur sont proposés. Vous pouvez créer un attendant automatique pour votre organisation à l’aide du Centre d’administration Teams.

Pour plus d’informations sur la configuration d’une fonction de attendendant automatique dans le cloud, voir [Configurer un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 9 : Affecter les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

Une fois vos numéros de service à **l’étape 4 ci-dessus**, vous devez les affecter à chaque type de service que vous souhaitez. Par exemple, si vous souhaitez un numéro de téléphone de service dédié (gratuit ou gratuit), vous devez affecter le numéro au pont de conférence.

- Pour l’audioconférence, vous pouvez affecter un numéro dédié à un pont de conférence en vous rendre sur des ponts de conférence du Centre d’administration **Teams** et en respectant les  >    >   invites.  Pour plus d’informations, voir Modifier les numéros gratuits ou gratuits [sur votre pont d’audioconférence.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- Pour les attendants automatiques, vous pouvez affecter un numéro dédié à un moyen de traitement automatique en vous rendez dans les contrôles automatiques du Centre d’administration **Teams,** puis suivez  >    >   les invites.  Pour plus d’informations, [voir Configurer un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)

- Pour les files d’attente d’appels, vous pouvez affecter un numéro dédié à une file d’attente d’appels en vous rendre dans les files d’attente du Centre d’administration **Teams** des appels vocaux et en suivez  >    >   les invites. Pour plus d’informations, voir [Créer une file d’attente d’appels cloud.](create-a-phone-system-call-queue.md)

Pour plus d’informations voir [Créer une attente système téléphonique appelée = "undefined" class="unusedGlossaryTerm">](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Étape 10 : configurer les crédits de communication pour votre organisation

Si vous souhaitez utiliser des numéros gratuits avec Microsoft Teams, vous devez configurer les crédits de communication. Microsoft vous recommande de configurer les crédits de communication pour les utilisateurs de vos forfaits d’appels (nationaux ou internationaux) et de l’audioconférence qui ont besoin de pouvoir appeler vers n’importe quelle destination. De nombreux pays/de nombreuses régions sont inclus, mais il est possible que certaines destinations ne soient pas incluses dans votre offre d’appels ou dans vos abonnements à l’audioconférence. 

Si vous ne définissez pas la facturation des crédits de communication et si vous n’affectez pas de licences crédits de communication à vos **utilisateurs** et que vous n’avez plus de minutes d’appel pour votre organisation (selon votre plan d’appels ou d’audioconférence dans votre pays/région), ces utilisateurs ne pourront plus appeler ou sortir d’un appel sortant d’une réunion d’audioconférence. Pour plus d’informations, notamment sur les montants des fonds [recommandés,](what-are-communications-credits.md) voir Quels sont les crédits de communication ? et Configurer les [crédits de communication pour votre organisation.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>Sujets associés
[Voici ce que vous obtenez avec Phone System dans Microsoft 365 ou Office 365](here-s-what-you-get-with-phone-system.md)

[Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
