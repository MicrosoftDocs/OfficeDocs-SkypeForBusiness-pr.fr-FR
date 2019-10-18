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
f1keywords: None
ms.custom:
- Phone System
description: 'Apprenez à configurer votre système téléphonique (PBX Cloud) pour votre organisation. '
ms.openlocfilehash: 429cedb3d8bad25982e4eacdaa82f82cacfc75ae
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571534"
---
# <a name="setting-up-phone-system-in-your-organization"></a>La configuration système téléphonique de votre organisation

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Étape 1 : Vérifiez que le système téléphonique est disponible dans votre pays ou région

1.  Tout d’abord accéder à la [disponibilité de pays et de région pour conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)et sélectionnez votre pays ou région dans la liste en haut de la page. 
2.  Sous **Système téléphonique**, passez en revue la liste des fonctionnalités et les détails. 
3.  Si le système téléphonique est disponible, passez à l’étape 2. 

**Pour plus d’informations sur la disponibilité régionale du système téléphonique et de conférence audio, voir [disponibilité pays et régions de conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Étape 2 : Acheter et affecter des licences système téléphonique et plans d’appel

Pour affecter un système téléphonique et une licence de plan d’appel à un utilisateur unique, les étapes sont les mêmes que celles associées à l’affectation d’une licence Office 365. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md). Si vous voulez affecter plusieurs utilisateurs en bloc, voir [attribuer des licences Microsoft teams](assign-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : obtenir des numéros de téléphone pour vos utilisateurs

Pour que vous puissiez configurer les utilisateurs de votre organisation pour passer et recevoir des appels téléphoniques, vous devez obtenir des numéros de téléphone pour eux.

Trois méthodes s’offrent à vous pour obtenir des numéros pour vos utilisateurs :
- Obtenir de nouveaux numéros à l'aide du centre d'administration de Skype Entreprise
- Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise.
- Transfert de vos numéros existants du fournisseur de services ou de l’opérateur de téléphonie actuel vers Office 365.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Obtenir de nouveaux numéros de téléphone d’utilisateur 
 
![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**

1. Connectez-vous à Microsoft 365 à l’aide de votre compte professionnel ou scolaire.

2. Accédez au >  **Centre d’administration Microsoft 365****Skype entreprise**.
    
3. Dans le volet de navigation de gauche, sélectionnez**numéros de téléphone** **vocaux** > , cliquez sur **Ajouter un numéro** ![sur le bouton ajouter](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), affiché en tant que symbole plus, puis cliquez sur **nouveaux numéros d’utilisateur**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Transfert de vos numéros de téléphone du fournisseur de services ou de l'opérateur de téléphonie
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- Si vous avez besoin de porter plus de numéros de téléphone 999, voir [gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) afin d’effectuer une demande de transfert de tous ces numéros vers Office 365. 

**Pour plus d’informations sur l’obtention de nouveaux numéros de téléphone ou de transfert de numéros existants, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 4 : Obtenir les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Obtenir de nouveaux numéros de service

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Accédez au >  **Centre d’administration Microsoft 365****Skype entreprise**.

3. Dans le volet de navigation de**gauche, sélectionnez****numéros** > de téléphone **vocaux** > , puis cliquez sur **nouveaux numéros de service**.

    > [!IMPORTANT]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Transférer des numéros de service existants

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Étape 5 : Si vous souhaitez configurer des Plans d’appel

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Ajout d’adresses de secours et d’emplacements d’urgence pour votre organisation

1. Sur la page **voix** , sélectionnez **emplacements** > d’urgence,**Ajouter une nouvelle adresse**.

2. Dans le volet **nouvelle adresse** , entrez un nom pour votre adresse, puis remplissez les autres zones.
    
     ![Capture d’écran du volet nouvelle adresse](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Pour les clients anglais, si le nom de rue est un chiffre, n'oubliez pas d'inclure « st » ou « th » à la fin, comme illustré dans l'image ci-dessus.

3. Sélectionnez **Valider**.

    Le cas échéant, vous serez invité à corriger l'adresse.

    > [!CAUTION]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.

    > [!TIP]
    > Si l'adresse doit être corrigée pour les situations d'urgence, une bannière verte indique que l'adresse a été mise à jour.

4. Une fois l'adresse validée, sélectionnez **Enregistrer**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Attribuer les numéros de téléphone et les adresses d'urgence aux utilisateurs

> [!TIP]
> Si vous avez des personnes à votre entreprise juste avant cette étape, **plusieurs heures** peuvent s'écouler avant qu'elles s'affichent dans la page **Utilisateurs Voix**. Il y a donc un délai de latence.

1. Dans la page **utilisateurs voix** , sélectionnez les personnes auxquelles vous souhaitez affecter un numéro de téléphone et une adresse de secours.

2. Dans le volet Action, cliquez sur **Affecter un numéro**.

3. Dans la page **attribuer un numéro** , dans la liste Sélectionner le **numéro à attribuer** , sélectionnez le numéro de téléphone de l’utilisateur.

4. Pour sélectionner une adresse de secours, saisissez le nom de la ville dans la zone, puis choisissez **Rechercher**.

    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Après avoir affecté le numéro de téléphone et l'adresse d'urgence, sélectionnez **Enregistrer**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informer vos utilisateurs de leurs nouveaux numéros de téléphone


Nous vous recommandons d'envoyer un courrier ou d'utiliser le moyen de communication préféré de votre entreprise pour communiquer leurs nouveaux numéros de téléphone aux utilisateurs.

Pour pouvoir voir ce numéro de téléphone dans son application **Skype entreprise** , procédez comme suit :

1. Connectez-vous à Skype Entreprise sur votre Bureau.
    
2. Sélectionnez **Paramètres** > **Outils** > **Options**. 
    
     ![Capture d’écran des options du menu outils](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Ensuite, sélectionnez **Téléphones**. 
    
    ![Capture d’écran des options du téléphone skype entreprise](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Capture d’écran des options disponibles après avoir cliqué sur appels](media/teams-phone-number.png)

**Pour plus d’informations sur toutes les étapes impliquées dans la configuration d’un Plan d’appel, voir [configurer des Plans d'appel](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Étape 6 : Si vous souhaitez configurer la conférence Audio

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Pour les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](audio-conferencing-common-questions.md).
    
1. Si vous avez acheté des licences de compléments de services d' **audioconférence** et de crédits de communications, attribuez-les également. Pour obtenir des instructions, consultez [attribuer des licences Microsoft teams](assign-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Les utilisateurs Microsoft Teams ne peut pas utiliser un fournisseur de services d’audioconférence tiers.

    - **Microsoft en tant que votre fournisseur de services d’audioconférence**: si vous souhaitez la solution la plus simple pour l’audioconférence, choisissez Microsoft en tant que votre fournisseur de services d’audioconférence.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Personnalisez les invitations aux réunions dans Skype entreprise](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Les numéros d’accès définis pour l’utilisateur sont automatiquement ajoutés aux invitations aux réunions envoyées aux participants. Néanmoins, vous pouvez ajouter votre propre aide et liens légaux, un message texte et un graphisme de petite entreprise.
    
   2. Définissez les numéros de téléphone de l’audioconférence pour les organisateurs de la réunion inclus dans les invitations [dans Skype entreprise](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) ou [Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md). Il s’agit du numéro de téléphone qui s’affichera dans la réunion planifiée par l’utilisateur.
    
   3. Définissez les langues du standard automatique pour l’audioconférence [dans Skype entreprise](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) ou [dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que le standard automatique de l’audioconférence utilise pour appeler un appelant lorsqu’il compose le numéro de téléphone d’une conférence audio. Cette étape s’applique uniquement si vous utilisez Microsoft comme fournisseur de services audio.
    
   4. Définissez la longueur du code confidentiel pour les réunions de conférence audio [dans Microsoft teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Pour plus d’informations sur l’audioconférence, voir [configurer l’audioconférence pour Microsoft teams](set-up-audio-conferencing-in-teams.md).**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Étape 7 : Si vous souhaitez configurer une file d’attente d’appels Cloud

Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui rejoignent les appels sont écouter de la musique pendant l’attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Pour créer une file d’attente d’appels, dans le **Centre d’administration de Skype entreprise**, cliquez sur**files d’attente**des appels de **routage** > des appels, cliquez sur **Ajouter nouveau**, puis suivez les instructions de l' **étape 3** de [la rubrique créer une file d’attente des appels Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Pour plus d’informations sur les files d’attente d’appels, voir [créer une file d’attente des appels Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Étape 8 : Si vous voulez configurer un standard automatique Cloud

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Pour créer un standard automatique, dans le centre d’administration de Skype entreprise, cliquez sur**standards**de **routage** > des appels, cliquez sur **Ajouter nouveau**, puis suivez les instructions de chaque page à l' **étape 2** de [la rubrique créer un standard automatique Cloud. ](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**Pour plus d’informations sur les standards automatiques Cloud, voir [configurer un standard automatique Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 9 : Affecter les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Pour les conférences audio, vous pouvez attribuer un numéro dédié à un pont de conférence en accédant aux > **centres** > d’administration du centre**d'** >  **administration Microsoft 365****et en** cliquant sur le bouton Conference Bridge ou en consultant [les numéros payants ou les numéros gratuits de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Pour les standards automatiques, vous pouvez attribuer un numéro dédié à un standard automatique en accédant aux centres d’administration du**** > Centre > d' **administration Microsoft 365**dans les**centres** > d’administration de**Skype entreprise** > .** **et en cliquant sur le standard automatique. Dans la page **général** , le numéro de service dont vous disposez est déjà répertorié dans la liste déroulante **numéro de téléphone** . Pour plus d’informations, consultez [configurer un standard automatique Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).
- Pour les files d’attente d’appels, vous pouvez attribuer un numéro dédié à une file d’attente**d’appels en** > accédant aux**centres** > d’administration du **Centre** > **d'** > administration de Microsoft 365 et en cliquant sur**** dans la file d’attente d’appels. Le numéro de téléphone indiqué dans la liste déroulante **numéro de téléphone** apparaît sur la page **général** . Pour plus d’informations, consultez [créer une file d’attente des appels Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).

**Pour plus d’informations voir [Créer une attente système téléphonique appelée = "undefined" class="unusedGlossaryTerm">](/microsoftteams/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Étape 10 : configurer les crédits de communication pour votre organisation

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Pour connaitre le coût, [voir les tarifs ici](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Pour configurer les Communications crédits

1. Connectez-vous à Microsoft 365 à l’aide de votre compte professionnel ou scolaire.

2. Dans le volet de navigation de gauche du centre d’administration, accédez à**abonnements** > de **facturation** > **-modules** > complémentaires**acheter des modules complémentaires**, puis cliquez sur **crédits** > de communication**acheter maintenant**.

3. Dans la page d’abonnement **Communications crédits** , renseignez vos informations, puis cliquez sur **suivant**.

4. Entrez vos informations de paiement, cliquez sur **passer la commande**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Pour plus d’informations sur la configuration des Communications crédits, voir [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Attribuer une licence crédits Communications aux utilisateurs

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Dans le volet de navigation de gauche du centre d’administration Microsoft 365, **accédez à** > utilisateurs**actifs**, puis sélectionnez un ou des utilisateurs dans la liste.

3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. Sur la page **licences de produits** , activez/désactivez l’option crédits de **communication** **pour affecter** cette licence, puis cliquez sur **Enregistrer**.

    > [!NOTE]
    > Même si certains de vos utilisateurs sont affectés à une licence **entreprise E5** , il est recommandé d’effectuer cette opération.

**Pour plus d’informations sur l’attribution de licences Communications crédits, voir [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Voir aussi
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
