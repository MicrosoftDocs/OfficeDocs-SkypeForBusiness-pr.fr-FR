---
title: Set up a Phone System auto attendant
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
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
- Strat_SB_PSTN
description: 'Learn how to set up and test Phone System (Cloud PBX) auto attendants for efficient call handling for your organization. '
ms.openlocfilehash: 275aececccca18b82cbd08a4f4aa580d1696dcf9
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Set up a Phone System auto attendant

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. Pour créer un standard automatique, accédez à **Routage des appels** dans le volet de navigation de gauche, puis sélectionnez **Standards automatiques** > **Ajouter nouveau**.
  
If you want to learn more about auto attendants, see [What are Phone System auto attendants?](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service numbers, they will show up on the **Skype for Business admin center** > **Voice** > **Phone numbers** page. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md), or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). **User (subscriber)** numbers can't be assigned to auto attendants. If you are outside the United States, you can't use the Skype for Business admin center to get service numbers; go [here](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead.
    
    > [!CAUTION]
    > To get and use toll-free phone numbers, you need to set up Communications Credits. To do this see [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) and [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for auto attendants. The numbers of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. For example, run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Étape 2 : création d'un standard automatique

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Standards automatiques**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="edit-general-info-page"></a>Page de modification des informations générales
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Name** Enter a descriptive display name for your auto attendant. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Il sera répertorié dans la colonne **Nom** de l'onglet **Standards automatiques**.
***

![Number 2](../images/sfbcallout2.png)<br/>**Phone number** This setting is optional. If you like, select a phone number for your auto attendant. You can pick any available service toll or toll-free phone number that you have for your organization. Si aucune numéro n'est répertorié, vous devrez obtenir un numéro de service gratuit ou payant. Go [here](getting-service-phone-numbers.md) to get them. <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![Number 3](../images/sfbcallout3.png)<br/>**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.
***
![14](../images/sfbcallout4.png)<br/>**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées. The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.
***
![Number 5](../images/sfbcallout5.png)<br/>**Speech recognition** Speech recognition is available and if this option is selected. People that call in can use voice input in the language you set. You can disable speech recognition by clearing it if you want to only let people use their phone keypad.
***
![Number 6](../images/sfbcallout6.png)<br/>**Opérateur** Cette option est facultative ne doit pas nécessairement être définie pour le standard automatique. However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them. <br/> <br/> La touche 0 est automatiquement affectée à l'option Opérateur. <br/> <br/> If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page. If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option. For example, "For the Operator, press zero." <br/><br/>  L'opérateur peut être défini comme suit : 
*    **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. <br/>

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 isn't supported. <br/> 

*    Une **file d'attente d'appels** que vous avez configurée. 
*    Vous pouvez la configurer de manière qu'une personne appelant soit renvoyée sur la messagerie. To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail. 
   
### <a name="select-hours-of-operation-page"></a>Page de sélection des heures d'ouverture

By default, business hours are set to 24 hours a day, 7 days a week, so all hours are considered business hours. Toutes les heures exclues des heures d'ouverture sont considérées comme des heures de fermeture. If you select the **Custom** option and set your business hours, then a new page called **After hours call handling** will be added where you can configure the call handling for after business hours for the auto attendant.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Number 1](../images/sfbcallout1.png)<br/>Sélectionnez l'option **Personnaliser** pour définir les heures d'ouverture spécifiques dans le calendrier. Lorsque vous sélectionnez **Personnaliser**, les heures d'ouverture seront définies du lundi au vendredi, de 09 h 00 à 17 h 00 par défaut.  
***
![Number 2](../images/sfbcallout2.png)<br/>Pour modifier les heures d'ouverture, mettez en surbrillance les heures d'ouverture que vous voulez définir à l'aide du calendrier. The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page. Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier. You can set multiple breaks within business hours. 
   
### <a name="select-business-hours-call-handling-page"></a>Select business hours call handling page

> [!TIP]
> Si vous utilisez un planning des heures d'ouverture personnalisé, vous devrez également configurer le traitement des appels hors heures d'ouverture. Une page de **traitement des appels hors heures d'ouverture** sera ajoutée pour vous permettre de configurer ces options. Vous disposerez d'options identiques à celles de la page de **traitement des appels pendant les heures d'ouverture**. 
  
You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Message d'accueil de l'entreprise** Le message d'accueil pendant les heures d'ouverture est facultatif et peut être défini sur **Aucun**. Dans ce cas, l'appelant n'entendra aucun message avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.
*    **None** No greeting will be played when people call in to the auto attendant phone number.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Welcome to Contoso. Votre appel est important pour nous. in the **Callers will hear** box.
*    **Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).
***
![Number 2](../images/sfbcallout2.png)<br/>You can select what happens to calls that arrive during business hours. You can chose from the following options:
*    **Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.
*    **Redirect call** This can be used to automatically send the call to:
     *    **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/><br/>   
        > [!Note]
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

     *    A **Call Queue** Using a Call Queue allows the call to be transferred to an existing Call Queue that you have set up.
     *    Another **Auto attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.
*    **Lire une invite des options de menu** Cette option vous permet de configurer une invite à lire.
***
![Number 3](../images/sfbcallout3.png)<br/>**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l'invite dans la zone **Les appelants entendront** ou enregistrer un fichier audio et dire par exemple « Pour contacter le département des Ventes, dites 1 ou appuyez sur 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. » **Créer une invite personnalisée** Si vous choisissez cette option, vous devez entrer le texte que le système devra lire (jusqu'à 1 000 caractères). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).
***
![Number 4](../images/sfbcallout4.png)<br/>**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search. Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**. N’importe quel utilisateur en ligne avec une licence de **Système téléphonique** , ou tout utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013, vous pouvez trouver avec accès par nom.<br/><br/>  **Caution:** Users hosted on-premises using Lync 2010 **can't be reached** with Dial by Name.
***

![Number 5](../images/sfbcallout5.png)<br/>**Modifier les options de menu** Les options de menu peuvent être ajoutées ou supprimées à l'aide des touches du clavier. Pour ajouter une option de menu, appuyez sur la touche correspondante du clavier. La couleur des touches utilisées changera et la ligne d'options correspondantes apparaîtra en dessous. Pour supprimer une option de menu, cliquez simplement sur la touche correspondante sur le contrôle du clavier pour désélectionner cette clé. La ligne de mappage de clé est supprimée.<br/><br/>  **Tip:** You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.  <br/><br/>  Any menu option can be added and removed in any order, and the key mappings don't have to be continuous. Il est possible, par exemple, pour créer un menu avec les touches de 0, 1 et 3 mis en correspondance avec les options, tandis que la clé 2 n’est pas utilisée.<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

Pour définir des options de menu, après avoir sélectionné l’ou les clés, vous devez : 
- **Entrez le nom de l’option** Il peut comporter jusqu'à 64 caractères et peut contenir plusieurs mots comme « Service client » ou « opérations et motifs ». Si la reconnaissance vocale est activée, le nom est reconnu automatiquement, et la personne appelant pourrez appuyez sur 3, dites « trois », ou dites « Service clientèle », activez la case à cocher mappée à la clé 3. 
- The next step is to select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition. The call can be sent to: 
    - **Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.<br/><br/> 
    
        > [!Note] 
        > **Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/><br/>

    - **Appelez la file d’attente** À l’aide d’une option de file d’attente d’appel permet l’appel à être transféré vers une file d’attente appel existant que vous avez configurées. 
    - **Standard automatique** Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu. These are called nested auto attendants.<br/><br/>
    
        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.         
   
### <a name="select-holidays-page"></a>Select holidays page 

You can add up to 20 scheduled holidays to each auto attendant.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Ajoutez un jour férié** Entrez un nom pour votre nouveau vacances dans le champ **nom du jour férié** .<br/><br/> Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être uniques pour la surveillance automatique de même. Par exemple, ne peut pas avoir deux vacances nommés « Thanksgiving » dans la surveillance automatique de même.  
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Holiday Greeting** The Holiday Greeting is optional and can be set to **None**. Dans ce cas, l'appelant n'entendra aucun message avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.
*    **Aucun** Aucun message d’accueil ne sera lu lorsque les utilisateurs appellent le numéro de téléphone de surveillance automatique.
*    **Créer un fichier personnalisé de salutation** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système de lecture (1000 caractères maximum). Par exemple, vous pouvez entrer « Joyeux Noël ! Nos bureaux est fermés actuellement. » dans la zone **appelants** .
*    **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil vacances et télécharger votre fichier audio (au format .wav, .mp3 ou .wma).  
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Que se passe-t-il pour les appels après le message d’accueil ?** Vous pouvez sélectionner ce qui se passe pour les appels qui arrivent pendant ces vacances. Vous pouvez choisir parmi les options suivantes :
*    **Se déconnecter** La personne l’appel sera déconnectée après avoir entendu le message d’accueil vacances.
*    **Rediriger l’appel** Cela peut servir à envoyer automatiquement l’appel à :
     *    Une **personne de votre société** avec une licence de **Système téléphonique** qui est activée pour la Voix Entreprise ou affectée à l’appel de Plans dans Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société**et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/><br/> 
     
         > [!Note] 
         > **Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.<br/><br/>

     *    **Appelez la file d’attente** pour transférer l’appel vers un existant appeler file d’attente que vous avez configurées.
     *    Un autre **standard automatique**, pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des surveillances imbriqués. <br/><br/>
     
         > [!Note]
         > Par défaut, tous les appels arrivant au cours d’une période de congé sont définies pour se déconnecter après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.

***
![Numéro 4](../images/sfbcallout4.png)<br/>**Lorsque vous souhaitez que les jours fériés de début et de fin ?** Entrez votre date de début du jour férié au format de jj/mm/aaaa, puis sélectionnez une heure de début, date de fin et l’heure de fin, que vous y êtes invité dans la table de plage de date.<br/><br/>Vous pouvez spécifier jusqu'à 10 différentes plages de dates pour un jour férié. Par exemple, vous pouvez ajouter des plages de dates pour les jours fériés réveillon du nouvel an pendant 10 ans. Un jour férié peut s’étendre sur plusieurs jours.<br/><br/>Pour ajouter d’autres vacances date plages (par exemple, pour l’année suivante), cliquez sur **Ajouter une autre**et puis entrez un nouvel ensemble de dates de début et de fin du jour férié.<br/><br/>Jours fériés imbriqués sont également pris en charge. Par exemple, vous pouvez imbriquer plusieurs jours fériés dans un délai de « vacances » : 
*    **Le 24 décembre via le 3 janvier :** « Bonnes fêtes ! Nos bureaux est fermés actuellement. Nous s’ouvre à nouveau sur le 4 janvier. »
*    **25 décembre :** « Joyeux Noël ! Nos bureaux est fermés actuellement. Nous s’ouvre à nouveau sur le 4 janvier. »
*    **1 janvier :** « Joyeux Noël ! Nos bureaux est fermés actuellement. Nous s’ouvre à nouveau sur le 4 janvier. »
   
Après avoir enregistré votre surveillance automatique, vos vacances s’affichent sous l’onglet de **jours fériés** , où vous pouvez modifier, ajouter ou modifier les paramètres d’absence.
  
### <a name="select-dial-scope-page"></a>Page de sélection de la portée de la numérotation

Sur cette page, vous pouvez configurer les utilisateurs de votre organisation seront répertoriés dans votre répertoire et disponibles pour l’accès par nom lorsqu’une personne appelle dans votre organisation.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>L'option **Inclure** présente deux choix :
*    **Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire. Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , comme les utilisateurs hébergés sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013 qui disposent de Plans d’appel dans Office 365, apparaît. 
*    **Personnalisé** Si vous utilisez cette option, vous pouvez effectuer une recherche pour un groupe d’Office 365, une liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et les personnes ajoutées à ce groupe d’Office 365, une liste de distribution ou un groupe de sécurité qui sont soit **aux utilisateurs en ligne avec un Licence de système téléphonique** ou hébergée sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité. <br/><br/> 

    > [!Caution]
    > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche le répertoire à l’aide de la numérotation par nom. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>À l’aide de l’option **Exclure** , vous disposez de deux options :
*    **Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire. 
*    **Personnalisé** Si vous utilisez cette option, vous pouvez effectuer une recherche pour un groupe d’Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et tous les utilisateurs ajoutés à ce groupe d’Office 365, liste de distribution, ou les groupes de sécurité seront exclus de la recherche dans l’annuaire. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité. <br/><br/> 

    > [!Caution]
    > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche le répertoire à l’aide de la numérotation par nom.          
   
> [!NOTE]
> Il peut prendre jusqu'à 36 heures pour un nouvel utilisateur pour que leur nom apparaît dans le répertoire lorsqu’une personne utilise la numérotation par nom avec la reconnaissance vocale. 
  
Après avoir entré tous les champs obligatoires et que vous configurer appel gestion des menus et options, cliquez sur **Enregistrer**.
  
## <a name="editing-and-testing-auto-attendants"></a>Modification et le test des surveillances automatiques

Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**. Cela vous permettra de rapidement voir les options que vous avez définies, y compris le nom, numéro de téléphone, langue et état.
  
Si vous souhaitez apporter des modifications à une surveillance automatique, sélectionnez la surveillance automatique et puis dans le volet Actions, cliquez sur **Modifier**.
  
Vous pouvez également rapidement placer un appel de test à votre surveillance automatique en utilisant le bouton **de Test** dans le volet Actions.
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.
  
### <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.
  
||| 
|---|---|
[Nouvelle-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [Nouvelle-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Ensemble-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [Nouvelle-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Supprimer-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [Nouvelle-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [Nouvelle-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Exportation-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Nouvelle-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [Nouvelle-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [Nouvelle-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [Nouvelle-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Importation-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Nouvelle-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
