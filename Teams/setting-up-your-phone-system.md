---
title: Configurer le système téléphonique de votre organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer le système téléphonique (PBX nuage) pour votre organisation. '
ms.openlocfilehash: 0ae2d890e87ecef217bfdafd2c547de7ae35414d
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047561"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configurer le système téléphonique de votre organisation

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Étape 1 : Vérifiez que le système téléphonique est disponible dans votre pays ou région

1.  Tout d’abord accéder à la [disponibilité de pays et de région pour conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)et sélectionnez votre pays ou région dans la liste en haut de la page. 
2.  Sous **Système téléphonique**, passez en revue la liste des fonctionnalités et les détails. 
3.  Si le système téléphonique est disponible, passez à l’étape 2. 

**Pour plus d’informations sur la disponibilité régionale du système téléphonique et de conférence audio, voir [disponibilité pays et régions de conférence audio et des plans d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Étape 2 : Acheter et affecter des licences système téléphonique et plans d’appel

To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). If you want to assign multiple users in bulk, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Étape 3 : Obtenir les numéros de téléphone pour vos utilisateurs

[] Avant d'autoriser les utilisateurs de votre organisation à passer et à recevoir des appels téléphoniques, vous devez obtenir vos numéros de téléphone par l'entremise du centre d'administration de Skype Entreprise.

Vous disposez de trois méthodes d’obtention des numéros pour vos utilisateurs :
- Obtenir de nouveaux numéros à l'aide du centre d'administration de Skype Entreprise
- Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise.
- Transfert de vos numéros existants du fournisseur de services ou de l'opérateur de téléphonie actuel.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Obtenir les nouveaux numéros de téléphone 
 
![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ** **
    
3. Dans le volet de navigation gauche, accédez à **voix** > **numéros de téléphone**, cliquez sur **Ajouter un nouveau numéro** ![Ajouter bouton ](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), puis cliquez sur**nouveaux numéros utilisateur**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Transfert de vos numéros de téléphone du fournisseur de services ou de l'opérateur de téléphonie
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- Si vous avez besoin de plus de 999 numéros de port, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour soumettre une demande de service de commande de port ou une commande pour obtenir tous les numéros de téléphone portées vers Office 365. 

**Pour plus d’informations sur l’obtention de nouveaux numéros de téléphone ou de transfert de numéros existants, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 4 : Obtenir les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Obtenir de nouveaux numéros de service

![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ** **

3. Dans le volet de navigation gauche, accédez à **voix** > **numéros de téléphone** > **Ajouter un nouveau numéro**, puis cliquez sur **nouveau numéro de service**.

    > [!IMPORTANT]
    > Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenir les nouveaux numéros qui ne sont pas disponibles dans le centre d’administration Skype entreprise
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Transférer des numéros de service existants

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Étape 5 : Si vous souhaitez configurer des Plans d’appel

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Ajouter des adresses d’urgence et des emplacements pour votre organisation

1. Dans la page de la **voix** , cliquez sur **emplacements d’urgence** > **Ajouter une nouvelle adresse**.

2. Dans le volet **Nouvelle adresse**, entrez un nom pour votre adresse, puis remplissez les autres zones.
    
     ![Quand vous renseignez une nouvelle adresse d'urgence, la mise en forme du nom de la rue peut causer une erreur.](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
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

1. Dans la page **utilisateurs Enterprise Voice** , sélectionnez les personnes qui vous souhaitez affecter un numéro de téléphone et l’adresse d’urgence.

2. Dans le volet Action, cliquez sur **Affecter un numéro**.

3. Dans la page **affecter des numéros** , dans la liste **Sélectionnez le numéro à attribuer** , sélectionnez le numéro de téléphone de l’utilisateur.

4. Pour sélectionner une adresse en cas d’urgence, entrez le nom de la ville dans la zone et cliquez sur **Rechercher**.

    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Après avoir affecté le numéro de téléphone et l'adresse d'urgence, sélectionnez **Enregistrer**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Demandez à vos utilisateurs sur leurs nouveaux numéros de téléphone


Nous vous recommandons d'envoyer un courrier ou d'utiliser le moyen de communication préféré de votre entreprise pour communiquer leurs nouveaux numéros de téléphone aux utilisateurs.

Voici comment ils peuvent voir ce numéro de téléphone dans leur application **Skype pour les entreprises** :

1. Connectez-vous à Skype Entreprise sur votre Bureau.
    
2. Sélectionnez **Paramètres** > **Outils** > **Options**. 
    
     ![Afin de voir votre numéro de téléphone, aller dans Paramètres > Outils > Options.](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Ensuite, sélectionnez **Téléphones**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Un utilisateur peut voir son numéro dans les équipes Microsoft en cliquant sur les appels dans le volet de navigation gauche.](media/teams-phone-number.png)

**Pour plus d’informations sur toutes les étapes impliquées dans la configuration d’un Plan d’appel, voir [configurer des Plans d'appel](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Étape 6 : Si vous souhaitez configurer la conférence Audio

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Pour les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](audio-conferencing-common-questions.md).
    
1. If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Les utilisateurs Microsoft Teams ne peut pas utiliser un fournisseur de services d’audioconférence tiers.

    - **Microsoft en tant que votre fournisseur de services d’audioconférence**: si vous souhaitez la solution la plus simple pour l’audioconférence, choisissez Microsoft en tant que votre fournisseur de services d’audioconférence.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Personnaliser les invitations de réunion dans Skype pour les entreprises](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Les numéros de connexion définis pour l'utilisateur seront ajoutés automatiquement aux invitations envoyées aux participants. Cependant, vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise.
    
   2. Définir les numéros de téléphone de conférence Audio qui sont inclus dans les organisateurs de réunion invite [dans Skype pour les entreprises](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) ou [Les équipes Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md). Il s’agit du numéro de téléphone qui s’affiche dans la réunion est planifiée par l’utilisateur.
    
   3. Définir les langues de standard automatique pour les services d’audioconférence [dans Skype pour les entreprises](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) ou [dans les équipes Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) par le standard automatique de conférence audio pour accueillir un appelant lorsqu’ils se connectent à un numéro de téléphone de conférence Audio. Cette étape s’applique uniquement si vous utilisez Microsoft en tant que fournisseur de services d’audioconférence.
    
   4. Définir la longueur de l’axe des réunions de conférence Audio [dans Skype pour les entreprises](/skypeforbusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings) ou [Les équipes Microsoft](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Pour plus d’informations sur la conférence Audio, voir [configurer la conférence Audio](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Étape 7 : Si vous souhaitez configurer une file d’attente des appels système téléphoniques

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Pour créer une nouvelle file d’attente d’appel, dans le **centre d’administration de Skype entreprise**, cliquez sur **routage des appels** > **files d’attente des appels**, cliquez sur **ajouter nouveau**, puis suivez les instructions à l' **étape 3** de [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Pour plus d’informations sur les files d’attente des appels, voir [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Étape 8 : Si vous souhaitez configurer un système téléphonique standard automatique

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Pour créer un nouveau standard automatique, dans le centre d’administration de Skype entreprise , cliquez sur **routage des appels** > **standards automatiques**, cliquez sur **ajouter nouveau**, puis suivez les instructions pour chaque page dans l' **étape 2** de [configurer un standard automatique de système téléphonique attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).

**Pour plus d’informations sur les standards automatiques de système téléphonique, consultez [configurer un standard automatique de système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Étape 9 : Affecter les numéros de téléphone des services (services d’audioconférence, files d’attente des appels, standards automatiques)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Pour une audioconférence, vous pouvez affecter un numéro dédié à un pont de conférence en accédant au **Centre d’administration d’Office 365** > **centres Admin** > **Skype pour les entreprises** > **conférence Audio**, puis cliquez sur le pont de conférence ou en consultant la rubrique [Modifier le numéro payant ou gratuit sur le pont de conférence Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Set up a Phone System Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).

- For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Create a Phone System call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

**Pour plus d’informations voir [Créer une attente système téléphonique appelée = "undefined" class="unusedGlossaryTerm">](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Étape 10 : Configurer les crédits de Communications pour votre organisation

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Pour connaitre le coût, [voir les tarifs ici](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Pour configurer les Communications crédits

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Dans la navigation de gauche du centre d’administration Office 365, accédez à la **facturation** > **abonnements** > **modules complémentaires** > **acheter des modules complémentaires**, puis choisissez **Crédits Communications** > **Acheter maintenant**.

3. Dans la page d’abonnement **Communications crédits** , renseignez vos informations, puis cliquez sur **suivant**.

4. Entrez vos informations de paiement, cliquez sur **passer la commande**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Pour plus d’informations sur la configuration des Communications crédits, voir [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Attribuer une licence crédits Communications aux utilisateurs

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Dans la navigation de gauche du centre d’administration Office 365, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez un ou plusieurs utilisateurs dans la liste.

3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. Dans la page **licences de produits** , activer/désactiver les **Communications crédits** **sur** pour affecter cette licence, puis cliquez sur **Enregistrer**.

    > [!NOTE]
    > Même si vous avez des utilisateurs auxquels une licence **Enterprise E5** , il est conseillé de faire.

**Pour plus d’informations sur l’attribution de licences Communications crédits, voir [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
