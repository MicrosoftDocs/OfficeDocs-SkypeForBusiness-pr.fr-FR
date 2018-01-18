---
title: "Configurer une surveillance automatique de système téléphonique"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Découvrez comment configurer et tester les surveillances automatiques le système téléphonique (PBX Cloud) pour efficace gestion des appels pour votre organisation. "
ms.openlocfilehash: 294a91ec723d8234e2dbfec8da79441080263c30
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurer une surveillance automatique de système téléphonique

Surveillances automatiques permettent de personnes à contacter dans votre organisation et de naviguer dans un système de menus pour les atteindre le bon service, appelez la file d’attente, la personne ou l’opérateur. Vous pouvez créer une surveillance automatique pour votre organisation à l’aide de la Skype pour centre d’administration commerciale. Pour créer une surveillance automatique, atteindre le **routage des appels** dans la navigation de gauche, puis sélectionnez les **surveillances automatiques** > **Nouveau**.
  
Si vous souhaitez en savoir plus sur les surveillances automatiques, voir [ce que sont les surveillances du système téléphonique ?](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

- Avant de pouvoir créer et paramétrer des surveillances automatiques de votre, vous devrez obtenir ou transférer votre numéro payant existant ou un service gratuit numéros. Après avoir obtenu les numéros de service gratuit ou le numéro payant, ils apparaîtront sur le **Skype pour le centre d’administration Business** > **vocale** > page de**numéros de téléphone** . Pour obtenir vos numéros de service, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](getting-service-phone-numbers.md), ou si vous souhaitez de transfert et le numéro de service existant, consultez le [transfert vers Office 365, les numéros de téléphone](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). **Utilisateur (abonné)** ne peut être affecté à des surveillances automatiques. Si vous résidez hors des États-Unis, vous ne pouvez pas utiliser le Skype pour Business admin center pour obtenir les numéros de service ; allez [ici](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place.
    
    > [!CAUTION]
    > Pour obtenir et utiliser des numéros de téléphone, vous devez configurer les crédits de Communications. À suivre, consultez [que sont les crédits de Communications ?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) et [configurer les crédits de Communications pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Une licence Enterprise E3 et **Système téléphonique** ou une licence Enterprise E5, votre organisation doit avoir (au minimum). Le nombre de licences d’utilisateur **Système téléphonique** affectées affecte le nombre de numéros de service sont disponibles pour être utilisés pour les standards automatiques. Les numéros des surveillances automatiques que vous pouvez avoir sont dépendante sur les licences de **Système téléphonique** et **Les conférences Audio** numériques qui vous sont affectées dans votre organisation. Pour en savoir plus sur les licences, allez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels à un opérateur ou une option de menu est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Voix Entreprise ou de leur attribuer des Plans d’appel dans Office 365. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez également utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Étape 2 : création d'un standard automatique

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Standards automatiques**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="edit-general-info-page"></a>Page de modification des informations générales
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Nom** Entrez un nom d’affichage de la description de votre surveillance automatique. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Il doit être répertorié dans la colonne **nom** de l’onglet de **surveillances automatiques** .
***

![Numéro 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Ce paramètre est facultatif. Si vous le souhaitez, sélectionnez un numéro de téléphone de votre surveillance automatique. Vous pouvez choisir n’importe quel numéro de service disponible ou le numéro d’appel gratuit dont vous disposez pour votre organisation. S’il n’y a aucun numéro de téléphone répertorié, vous devrez obtenir un numéro de service ou d’un téléphone gratuit nombre. Allez [ici](getting-service-phone-numbers.md) pour les obtenir. <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.
***
![14](../images/sfbcallout4.png)<br/>**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre surveillance automatique à partir d’une des langues répertoriées. La langue définie ici est la langue dans laquelle la surveillance automatique utilisera pour interagir avec des personnes qui appellent cette surveillance automatique, et tous les invites du système seront lues dans cette langue.
***
![Numéro 5](../images/sfbcallout5.png)<br/>**Reconnaissance vocale** La reconnaissance vocale est disponible et si cette option est sélectionnée. Les personnes qui appellent dans peuvent utiliser entrée vocale dans la langue définie. Vous pouvez désactiver la reconnaissance vocale en effaçant son contenu si vous souhaitez uniquement permettent aux utilisateurs à utiliser leur clavier de téléphone.
***
![Numéro 6](../images/sfbcallout6.png)<br/>**Opérateur** Cela est facultatif et ne doit pas être définie pour la surveillance automatique. Toutefois, vous pouvez définir l’option **d’opérateur** pour les personnes qui appellent dans pour pouvoir sortir les menus parler à une personne pour les aider. <br/> <br/> La touche 0 est automatiquement affectée à l'option Opérateur. <br/> <br/> Si vous définissez ceci, vous devrez également dire aux gens qui appeler dans la mesure où il s’agit d’une option disponible dans la liste **Modifier les options de menu** sur la page de **Gestion des appels de heures** . Si vous définissez un opérateur sur votre surveillance automatique, vous devrez entrer le texte d’invite correspondant dans la zone **appelants** ou modifier votre fichier audio pour inclure cette option. Par exemple, « pour l’opérateur, appuyez sur la touche zéro. » <br/><br/>  L'opérateur peut être défini comme suit : 
*    **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour la Voix Entreprise ou affectée à l’appel de Plans dans Office 365. <br/>

        > [!Note] 
        > **Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/> 

*    **Appelez la file d’attente** que vous avez configurées. 
*    Vous pouvez configurer la personne appelant est envoyés vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définissez les appels de cette personne à transférer directement vers la messagerie vocale. 
   
### <a name="select-hours-of-operation-page"></a>Page de sélection des heures d'ouverture

Par défaut, les heures de bureau sont définies sur 24 heures sur 24, 7 jours par semaine, toutes les heures sont considérées comme les heures de bureau. Toutes les heures qui ne sont pas inclus dans les heures sont considérées comme après les heures de bureau. Si vous sélectionnez l’option **personnalisée** et définissez vos heures de bureau, une nouvelle page appelée **après que les heures de gestion des appellent** va être ajoutée où vous pouvez configurer la gestion des appels pour après les heures de bureau pour la surveillance automatique.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Sélectionnez l'option **Personnaliser** pour définir les heures d'ouverture spécifiques dans le calendrier. Lorsque vous sélectionnez **Personnaliser**, les heures d'ouverture seront définies du lundi au vendredi, de 09 h 00 à 17 h 00 par défaut.  
***
![Numéro 2](../images/sfbcallout2.png)<br/>Pour modifier les heures de bureau, mettez en surbrillance les heures que vous souhaitez définir à l’aide du calendrier. Le calendrier vous permet de sélectionner les heures de bureau par intervalles de 30 minutes et les heures que vous sélectionnez ici sera définies en fonction du fuseau horaire que vous définissez dans la page **informations générales** . Pour définir un saut (pause déjeuner, par exemple), désactivez l’option, ou faites glisser pour désélectionner l’heure dans le calendrier. Vous pouvez définir plusieurs sauts dans les heures ouvrables. 
   
### <a name="select-business-hours-call-handling-page"></a>Sélectionnez les heures de bureau appeler la page de gestion des

> [!TIP]
> Si vous utilisez un planning des heures d'ouverture personnalisé, vous devrez également configurer le traitement des appels hors heures d'ouverture. Une page de **traitement des appels hors heures d'ouverture** sera ajoutée pour vous permettre de configurer ces options. Vous disposerez d'options identiques à celles de la page de **traitement des appels pendant les heures d'ouverture**. 
  
Vous pouvez configurer greetings, les invites et les menus que les personnes appel au numéro de téléphone du service Surveillance du automatique de votre organisation est émis pendant les heures d’ouverture.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Accueil de la société** Accueil pendant les heures est facultatifs et peut être définies sur **Aucun**. Dans ce cas, l’appelant n’entendra aucun message ou un message d’accueil avant que l’appel est géré par l’une des options que vous sélectionnez. Vous pouvez également télécharger un fichier audio (en formats .wav, mp3 ou .wma) ou créer un message d’accueil personnalisé à l’aide de la synthèse vocale.
*    **Aucun** Aucun message d’accueil ne sera lu lorsque les utilisateurs appellent le numéro de téléphone de surveillance automatique.
*    **Créer un fichier personnalisé de salutation** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système de lecture (1000 caractères maximum). Par exemple, vous pouvez entrer « Bienvenue à Contoso. Votre appel est important pour nous. » dans la zone **appelants** .
*    **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil et de télécharger votre fichier audio (au format .wav, .mp3 ou .wma).
***
![Numéro 2](../images/sfbcallout2.png)<br/>Vous pouvez sélectionner ce qui se passe aux appels qui arrivent pendant les heures ouvrables. Vous pouvez choisir parmi les options suivantes :
*    **Se déconnecter** Si vous sélectionnez cette option, la personne l’appel sera déconnectée après avoir entendu un accueil pendant les heures.
*    **Rediriger l’appel** Cela peut servir à envoyer automatiquement l’appel à :
     *    **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour la Voix Entreprise ou affectée à l’appel de Plans dans Office 365. Vous pouvez configurer afin que la personne l’appel peut être envoyée à la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/><br/>   
        > [!Note]
        > **Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/><br/>

     *    Une **File d’attente de l’appeler** à l’aide d’une file d’attente de l’appel permet l’appel d’être transférés vers un appel file d’attente existante que vous avez configurées.
     *    Un autre **standard automatique** , vous pouvez utiliser un fichier auto surveillance pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des surveillances imbriqués.
*    **Invite du menu options de lecture** Il peuvent également servir pour vous permettre de définir une invite que vous souhaitez lire.
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l'invite dans la zone **Les appelants entendront** ou enregistrer un fichier audio et dire par exemple « Pour contacter le département des Ventes, dites 1 ou appuyez sur 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. » **Créer une invite personnalisée** Si vous choisissez cette option, vous devez entrer le texte que le système devra lire (jusqu'à 1 000 caractères). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).
***
![Numéro 4](../images/sfbcallout4.png)<br/>**Numérotation par nom** Si vous choisissez cette option, cela permettra de personnes appellent dans pour rechercher des personnes dans votre organisation à l’aide de la recherche dans l’annuaire. Vous pouvez sélectionner quelles personnes seront répertoriés comme disponible ou n’est pas disponible pour l’accès par nom par la configuration de ces options dans la page **étendue de composer** . N’importe quel utilisateur en ligne avec une licence de **Système téléphonique** , ou tout utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013, vous pouvez trouver avec accès par nom.<br/><br/>  **Attention :** Les utilisateurs hébergés sur site à l’aide de Lync 2010 **ne peut pas être atteinte** avec une numérotation par nom.
***

![Numéro 5](../images/sfbcallout5.png)<br/>**Modifier les options de menu** Les options de menu peuvent être ajoutées ou supprimées sur le clavier à l’aide des boutons de clé. Pour ajouter une option de menu, appuyez sur la touche correspondante sur le clavier. Les clés utilisées change de couleur et apparaît sous la ligne correspondante des options. Pour supprimer une option de menu, cliquez simplement sur la touche correspondante sur le contrôle du clavier pour désélectionner cette clé. La ligne de mappage de clé est supprimée.<br/><br/>  **Conseil :** Vous devez mettre à jour le texte des invites de menu ou de ré-enregistrer séparément les données audio lors de l’ajout à la suppression des options, car elle ne s’effectue automatiquement pour l’invite menu existant.  <br/><br/>  Les options de menu peuvent être ajoutées et supprimées dans n’importe quel ordre, et les mappages de clés n’ont à être continue. Il est possible, par exemple, pour créer un menu avec les touches de 0, 1 et 3 mis en correspondance avec les options, tandis que la clé 2 n’est pas utilisée.<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

Pour définir des options de menu, après avoir sélectionné l’ou les clés, vous devez : 
- **Entrez le nom de l’option** Il peut comporter jusqu'à 64 caractères et peut contenir plusieurs mots comme « Service client » ou « opérations et motifs ». Si la reconnaissance vocale est activée, le nom est reconnu automatiquement, et la personne appelant pourrez appuyez sur 3, dites « trois », ou dites « Service clientèle », activez la case à cocher mappée à la clé 3. 
- L’étape suivante consiste à sélectionner où l’appel doit être envoyé si la touche correspondante est enfoncée, ou si l’option est sélectionnée, à l’aide de la reconnaissance vocale. L’appel peut être envoyé à : 
    - **Opérateur** Si l’opérateur est déjà configuré, il est automatiquement mappé à la clé 0, mais il peut également être supprimé ou réaffectée à une autre clé. Si l’opérateur n’est pas défini sur n’importe quelle touche, puis la commande vocale « Opérateur » sera désactivée trop. 
    - Une **personne de votre société** avec une licence de **Système téléphonique** qui est activée pour la Voix Entreprise ou affectée à un Plan d’appel dans Office 365. Vous pouvez configurer afin que la personne l’appel peut être envoyée à la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale.<br/><br/> 
    
        > [!Note] 
        > **Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/><br/>

    - **Appelez la file d’attente** À l’aide d’une option de file d’attente d’appel permet l’appel à être transféré vers une file d’attente appel existant que vous avez configurées. 
    - **Standard automatique** Vous pouvez utiliser un standard automatique existant pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des surveillances imbriqués.<br/><br/>
    
        > [!Note]
        > Les **heures de bureau** de surveillances imbriqués (ou de second niveau) sera également utilisé, y compris pour les appels provenant d’autres standards automatiques qui ont été définies.         
   
### <a name="select-holidays-page"></a>Sélectionnez la page de jours fériés 

Vous pouvez ajouter jusqu'à 20 vacances planifiées pour chaque surveillance automatique.
  
![Définissez les jours fériés dans la surveillance automatique](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Ajoutez un jour férié** Entrez un nom pour votre nouveau vacances dans le champ **nom du jour férié** .<br/><br/> Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être uniques pour la surveillance automatique de même. Par exemple, ne peut pas avoir deux vacances nommés « Thanksgiving » dans la surveillance automatique de même.  
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Jour férié de salutation** Les jours fériés de salutation est facultatif et peut être défini sur **Aucun**. Dans ce cas, l’appelant n’entendra aucun message ou un message d’accueil avant que l’appel est géré par l’une des options que vous sélectionnez. Vous pouvez également télécharger un fichier audio (en formats .wav, mp3 ou .wma) ou créer un message d’accueil personnalisé à l’aide de la synthèse vocale.
*    **Aucun** Aucun message d’accueil ne sera lu lorsque les utilisateurs appellent le numéro de téléphone de surveillance automatique.
*    **Créer un fichier personnalisé de salutation** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système de lecture (1000 caractères maximum). Par exemple, vous pouvez entrer « Joyeux Noël ! Nos bureaux est fermés actuellement. » dans la zone **appelants** .
*    **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil vacances et télécharger votre fichier audio (au format .wav, .mp3 ou .wma).  
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Que se passe-t-il pour les appels après le message d’accueil ?** Vous pouvez sélectionner ce qui se passe pour les appels qui arrivent pendant ces vacances. Vous pouvez choisir parmi les options suivantes :
*    **Se déconnecter** La personne l’appel sera déconnectée après avoir entendu le message d’accueil vacances.
*    **Rediriger l’appel** Cela peut servir à envoyer automatiquement l’appel à :
     *    Une **personne de votre société** avec une licence de **Système téléphonique** qui est activée pour la Voix Entreprise ou affectée à l’appel de Plans dans Office 365. Vous pouvez configurer afin que la personne l’appel peut être envoyée à la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société**et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/><br/> 
     
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
*    **Tous les utilisateurs** À l’aide de cette option permet à toutes les personnes de votre organisation à inclure dans la recherche dans l’annuaire. Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , comme les utilisateurs hébergés sur site à l’aide de Skype pour Business Server 2015 ou Lync Server 2013 qui disposent de Plans d’appel dans Office 365, apparaît. 
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

Après avoir enregistré votre surveillance automatique, il apparaît sur la page de **surveillances automatiques** . Cela vous permettra de rapidement voir les options que vous avez définies, y compris le nom, numéro de téléphone, langue et état.
  
Si vous souhaitez apporter des modifications à une surveillance automatique, sélectionnez la surveillance automatique et puis dans le volet Actions, cliquez sur **Modifier**.
  
Vous pouvez également rapidement placer un appel de test à votre surveillance automatique en utilisant le bouton **de Test** dans le volet Actions.
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.
  
### <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.
  
||| 
|---|---|
[Nouvelle-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx)                                                                      | [Nouvelle-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx)                                                              |
| [Ensemble-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx)                                                                      | [Nouvelle-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Supprimer-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx)                                                                   | [Nouvelle-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx)                                                                                 | [Nouvelle-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx)                                                              |
| [Exportation-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Nouvelle-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx)                                                                                  |
| [Nouvelle-CsOnlineDateTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [Nouvelle-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/en-us/library/mt796483.aspx)                                                     | [Nouvelle-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx)                                                     | [Importation-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Nouvelle-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Voici ce que vous obtenez avec système de téléphone dans Office 365](here-s-what-you-get-with-phone-system.md)

[Numéros de téléphone de service lors de l’obtention de Skype pour les entreprises et les Teams Microsoft](getting-service-phone-numbers.md)

[Pays et région de disponibilité pour les conférences Audio et les Plans d’appel](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    

