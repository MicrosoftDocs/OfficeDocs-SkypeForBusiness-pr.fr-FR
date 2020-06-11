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
description: Guide pas à pas expliquant comment configurer le système téléphonique (PBX Cloud) pour votre organisation dans Microsoft 365 ou Office 365.
ms.openlocfilehash: c1ced5aa9a6fdbfeb5cb02948607c7be7df7fbd8
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691030"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurer le système téléphonique au sein de votre organisation

Vous trouverez ci-dessous un guide pas à pas pour configurer le système téléphonique dans Microsoft 365 ou Office 365. Des liens vers des informations plus détaillées sont disponibles à la fin de chaque étape.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Étape 1 : Vérifiez que le système téléphonique est disponible dans votre pays ou région

1.    Tout d’abord accéder à la [disponibilité de pays et de région pour conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)et sélectionnez votre pays ou région dans la liste en haut de la page. 
2.    Sous **Système téléphonique**, passez en revue la liste des fonctionnalités et les détails. 
3.    Si le système téléphonique est disponible, passez à l’étape 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Étape 2 : Acheter et affecter des licences système téléphonique et plans d’appel

Pour affecter un système téléphonique et une licence de plan d’appel à un utilisateur unique, les étapes sont les mêmes que celles associées à l’affectation d’une licence Microsoft 365 ou Office 365.  Vous pouvez également affecter des licences à plusieurs utilisateurs en bloc. Pour plus d’informations, voir [affecter des licences de compléments Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).

Si les offres d’appels ne sont pas disponibles dans votre pays ou région, envisagez d’utiliser le routage direct pour connecter votre infrastructure de téléphonie locale au système téléphonique.  Pour plus d’informations, voir [routage direct du système téléphonique](direct-routing-landing-page.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : obtenir des numéros de téléphone pour vos utilisateurs

Pour que vous puissiez configurer les utilisateurs de votre organisation pour passer et recevoir des appels téléphoniques, vous devez obtenir des numéros de téléphone pour eux.

Trois méthodes s’offrent à vous pour obtenir des numéros pour vos utilisateurs :
- Obtenez de nouveaux numéros à l’aide du centre d’administration Teams.
- Obtenez de nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Teams.
- Transfert de vos numéros existants du fournisseur de services ou de l’opérateur de téléphonie actuel vers Microsoft 365 ou Office 365.

Vous devez utiliser la page **Ajouter des numéros** pour afficher, Rechercher, acquérir et réserver ces numéros. Vous pouvez effectuer une recherche par pays/région, État et ville, puis entrer le nombre de numéros de téléphone dont vous avez besoin pour vos utilisateurs.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Obtenir de nouveaux numéros de téléphone d’utilisateur à l’aide du centre d’administration teams

1. Connectez-vous à Microsoft 365 à l’aide de votre compte professionnel ou scolaire.

2. Accédez au **Centre d’administration teams**.
    
3. Dans le volet de navigation de **Voice**gauche, sélectionnez numéros de  >  **téléphone**vocaux, cliquez sur **Ajouter**, puis suivez les instructions.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtenir de nouveaux numéros qui ne sont pas disponibles dans le centre d’administration teams
  
Parfois (en fonction de votre pays ou région) vous ne serez pas en mesure d’obtenir vos nouveaux numéros à l’aide du centre d’administration Teams. Dans ce cas, vous devez télécharger un formulaire et le renvoyer. Pour savoir comment demander de nouveaux numéros d’utilisateur, reportez-vous à la rubrique [gestion des numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Transfert de vos numéros de téléphone du fournisseur de services ou de l'opérateur de téléphonie
  
- Si vous avez besoin de plus de 999 numéros de téléphone pour vos utilisateurs, vous pouvez utiliser l’Assistant Nouvelle demande de transfert de **numéros locaux** dans le centre d’administration Teams. Suivez les étapes décrites dans l’article [transférer des numéros de téléphone vers Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) pour transférer vos numéros de téléphone.
    
- Si vous avez besoin de porter plus de numéros de téléphone 999, voir [gérer les numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour qu’ils envoient une demande ou une commande de service de transfert. 

Pour plus d’informations sur l’obtention de nouveaux numéros de téléphone ou de transfert de numéros existants, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 4 : Obtenir les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

En plus d’obtenir des numéros de téléphone pour vos utilisateurs à partir de Microsoft 365 ou d’Office 365, vous pouvez effectuer des recherches et acquérir des numéros de téléphone gratuits ou payants pour les services tels que les conférences audio (pour les ponts de conférence), les standards automatiques et les files d’attente d’appels. Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d’appels simultanément, alors que le numéro de téléphone d’un utilisateur peut uniquement gérer quelques appels simultanément.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Obtention de nouveaux numéros de service dans le centre d’administration teams


1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.

2. Accédez au **Centre d’administration teams**.

3. Dans le volet de navigation gauche, **Voice**sélectionnez  >  **numéros de téléphone**vocaux  >  ,**Ajoutez nouveau numéro**, puis cliquez sur **nouveaux numéros de service**.

    > [!IMPORTANT]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration Teams, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtenir de nouveaux numéros qui ne sont pas disponibles dans le centre d’administration teams
  
Parfois (en fonction de votre pays ou région) vous ne serez pas en mesure d’obtenir vos nouveaux numéros à l’aide du centre d’administration Teams. Dans ce cas, vous devrez télécharger un formulaire et le renvoyer. Pour plus d’informations sur la demande de nouveaux numéros, voir [gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 

### <a name="port-or-transfer-existing-service-numbers"></a>Transférer des numéros de service existants

Si vous voulez transférer des numéros de service depuis votre fournisseur ou opérateur de services actuel, vous devez envoyer une demande de transfert manuellement à Microsoft. Vous devez transmettre des commandes de port distinctes pour chaque type de numéro de service (numéro payant ou gratuit) que vous allez transférer en utilisant une lettre d’autorisation (LOA). Dans la lettre d’autorisation (LOA), vous devez sélectionner le type de service approprié. Lorsque vous contactez le support technique de Microsoft, spécifiez que vous transférez un numéro de service (*et non un numéro d’utilisateur ou d’abonné*), ou si la capacité d’appels simultanés ne doit pas être suffisante pour gérer les volumes d’appels. Si vous souhaitez transférer les numéros de téléphone ou effectuer d’autres opérations avec vos numéros de téléphone, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Étape 5 : Si vous souhaitez configurer des Plans d’appel

Si vous avez suivi les étapes ci-dessus, vous avez déjà acheté et affecté du système téléphonique, les licences et un Plan d’appel (étape 2) et acquis des numéros de téléphone pour vos utilisateurs (étape 3), donc votre plan d'appel est partiellement configuré. Pour suivre les procédures de configuration d’un forfait d’appels, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Étape 6 : Si vous souhaitez configurer la conférence Audio

Parfois, des personnes de votre organisation devront utiliser un téléphone pour rejoindre une réunion. Microsoft teams inclut la fonction de conférence audio uniquement pour cette situation. Les personnes peuvent appeler des réunions teams à l’aide d’un téléphone, au lieu d’utiliser l’application teams sur un appareil mobile ou un PC.
Pour plus d’informations sur la configuration de l’audioconférence, voir [configurer l’audioconférence pour teams](set-up-audio-conferencing-in-teams.md).

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Étape 7 : Si vous souhaitez configurer une file d’attente d’appels Cloud

Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui appellent écoutent de la musique pendant l’attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.

Pour plus d’informations sur les files d’attente d’appels, voir [créer une file d’attente des appels Cloud](create-a-phone-system-call-queue.md).

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Étape 8 : Si vous voulez configurer un standard automatique Cloud

Les standards automatiques permettent aux personnes qui rejoignent votre organisation d’appeler votre organisation et de naviguer dans un système de menu pour les faire passer au service approprié, à la file d’attente des appels, à la personne ou à l’opérateur. Vous pouvez créer un standard automatique pour votre organisation à l’aide du centre d’administration Teams.

Pour plus d’informations sur la configuration d’une auto-attendendant du Cloud, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 9 : Affecter les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

Une fois vos numéros de service à **l’étape 4 ci-dessus**, vous devez les affecter à chaque type de service que vous souhaitez. Par exemple, si vous souhaitez utiliser un numéro de téléphone de service dédié (payant ou gratuit), vous devez affecter le numéro au pont de conférence.

- Pour les conférences audio, vous pouvez attribuer un numéro dédié à un pont de conférence en accédant à réunions du **Centre d’administration teams**  >  **Meetings**  >  **Conference bridges** et en suivant les invites.  Pour plus d’informations, reportez-vous à [modifier les numéros payants ou les numéros gratuits de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- S’il s’agit de standards automatiques, vous pouvez attribuer un numéro dédié à un standard automatique en accédant aux standards automatiques de la voix du **Centre d’administration teams**  >  **Voice**  >  **Auto attendants** et en suivant les invites.  Pour plus d’informations, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).

- Pour les files d’attente d’appels, vous pouvez attribuer un numéro dédié à une file d’attente d’appels en accédant aux files d’attente d’appels vocaux du **Centre d’administration teams**  >  **Voice**  >  **Call queues** et en suivant les invites. Pour plus d’informations, consultez [créer une file d’attente des appels Cloud](create-a-phone-system-call-queue.md).

Pour plus d’informations voir [Créer une attente système téléphonique appelée = "undefined" class="unusedGlossaryTerm">](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Étape 10 : configurer les crédits de communication pour votre organisation

Si vous souhaitez utiliser des numéros sans frais avec Microsoft Teams, vous devez configurer des crédits de communication. Microsoft vous recommande de configurer des crédits de communication pour vos forfaits d’appels (nationaux ou internationaux) et les utilisateurs de l’audioconférence qui ont besoin d’être en mesure de passer des appels vers n’importe quelle destination. De nombreux pays ou régions sont inclus, mais certaines destinations peuvent ne pas être incluses dans les abonnements de votre plan d’appel ou de votre audioconférence. 

Si vous ne configurez pas la facturation et attribuez une licence de **crédit** à vos utilisateurs et que vous avez des minutes pour votre organisation (en fonction de votre forfait d’appel ou de votre plan de visioconférence dans votre pays/région), les utilisateurs ne seront pas en mesure de passer des appels ou des appels sortants à partir des réunions de conférence audio. Pour plus d’informations, y compris les montants de financement recommandés, voir [qu’est-ce que les crédits de communication ?](what-are-communications-credits.md) et [configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Rubriques connexes
[Voici ce que vous pouvez obtenir avec le système téléphonique dans Microsoft 365 ou Office 365](here-s-what-you-get-with-phone-system.md)

[Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
