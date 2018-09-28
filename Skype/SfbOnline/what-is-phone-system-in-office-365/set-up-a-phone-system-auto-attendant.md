---
title: Configurer un standard automatique pour le système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Découvrez comment configurer et tester les standards automatiques de système téléphonique (PBX nuage) pour efficace gestion des appels pour votre organisation. '
ms.openlocfilehash: bceda290adc10e806249cbd0938305ffa321d91f
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347265"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurer un standard automatique pour le système téléphonique

Standards automatiques permettent aux personnes qui appellent votre organisation et accédez à les atteindre le bon service, appelez la file d’attente, la personne ou l’opérateur un système de menus. Vous pouvez créer un standard automatique pour votre organisation à l’aide de la Skype entreprise centre d’administration. Pour créer un standard automatique, accédez à **Routage des appels** dans le volet de navigation de gauche, puis sélectionnez **Standards automatiques** > **Ajouter nouveau**.
  
Si vous souhaitez en savoir plus sur les standards automatiques, voir [Quelles sont les standards automatiques de système téléphonique ?](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

- Avant de pouvoir créer et configurer vos standards automatiques, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous obtenez les numéros gratuits service payant, ils s’affichent sur le **Skype pour le centre d’administration Business** > **vocale** > page de**numéros de téléphone** . Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](getting-service-phone-numbers.md), ou si vous souhaitez transférer et le numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service ; Accédez [ici](/microsoftteams/manage-phone-numbers-for-your-organization) à la place.

    > [!CAUTION]
    > Pour obtenir et utiliser les numéros de téléphone gratuit, vous devez configurer les crédits de Communications. Pour faire cela, consultez [Quelles sont les Communications crédits ?](/microsoftteams/what-are-communications-credits) et [configurer les Communications crédits pour votre organisation](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les standards automatiques. Les numéros des standards automatiques que vous pouvez avoir dépend de licences numéros **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour en savoir plus sur les licences, accédez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Enterprise Voice ou de leur attribuer des Plans de l’appel dans Office 365. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Étape 2 : création d'un standard automatique

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**


Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Standards automatiques**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="edit-general-info-page"></a>Page de modification des informations générales
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Nom** Entrez un nom d’affichage de la description pour le standard automatique. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Il sera répertorié dans la colonne **Nom** de l'onglet **Standards automatiques**.
***

![Numéro 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Ce paramètre est facultatif. Si vous le souhaitez, sélectionnez un numéro de téléphone pour le standard automatique. Vous pouvez choisir de n’importe quel numéro payant service disponibles ou le numéro de téléphone gratuit que vous avez pour votre organisation. Si aucune numéro n'est répertorié, vous devrez obtenir un numéro de service gratuit ou payant. Aller [ici](getting-service-phone-numbers.md) pour en obtenir. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Nombre 3](../images/sfbcallout3.png)<br/>**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné.
***
![14](../images/sfbcallout4.png)<br/>**Langue** Sélectionnez la langue que vous souhaitez utiliser pour votre standard automatique parmi les langues disponibles répertoriées. La langue que vous définissez ici est la langue que le standard automatique utilisera pour interagir avec des personnes qui appellent ce standard automatique et toutes les invites système seront énoncées dans cette langue.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>**Reconnaissance vocale** La reconnaissance vocale est disponible et si cette option est sélectionnée. Les utilisateurs qui appellent dans peuvent utiliser entrée vocale dans la langue définie. Vous pouvez désactiver la reconnaissance vocale en le désactivant si vous souhaitez uniquement permettent aux utilisateurs à utiliser leur clavier du téléphone.
***
![Numéro 6](../images/sfbcallout6.png)<br/>**Opérateur** Cette option est facultative ne doit pas nécessairement être définie pour le standard automatique. Toutefois, vous pouvez définir l’option **opérateur** des personnes appellent pour sortir les menus de parler à une personne pour leur permettre de pouvoir. <br/> <br/> La touche 0 est automatiquement affectée à l'option Opérateur. <br/> <br/> Si vous configurer ce paramètre, vous devez également indiquer aux personnes qui appellent que ceci est une option disponible dans le **menu options d’édition** dans la page **Gestion des appels en heures** . Si vous définissez un opérateur pour le standard automatique, vous devrez entrer le texte du message correspondant dans la zone **appelants entendront** ou modifier votre fichier audio pour inclure cette option. Par exemple, « pour l’opérateur, appuyez sur zéro. » <br/><br/>  L'opérateur peut être défini comme suit : 
*    **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365. <br/>

        > [!Note] 
        > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/> 

*    Une **file d'attente d'appels** que vous avez configurée. 
*    Vous pouvez la configurer de manière qu'une personne appelant soit renvoyée sur la messagerie. Pour ce faire, sélectionnez la **personne de votre société** et définir les appels de cette personne à transférer directement vers la messagerie vocale. 
   
### <a name="select-hours-of-operation-page"></a>Page de sélection des heures d'ouverture

Par défaut, les heures ouvrées sont définies à 24 heures sur 24, 7 jours par semaine, toutes les heures sont considérées comme des heures d’ouverture. Toutes les heures exclues des heures d'ouverture sont considérées comme des heures de fermeture. Si vous sélectionnez l’option **personnalisé** et définissez vos heures de bureau, puis une nouvelle page appelée **après que les heures de gestion des appels** est ajoutée où vous pouvez configurer la gestion des appels pour après les heures d’ouverture pour le standard automatique.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Sélectionnez l'option **Personnaliser** pour définir les heures d'ouverture spécifiques dans le calendrier. Lorsque vous sélectionnez **Personnaliser**, les heures d'ouverture seront définies du lundi au vendredi, de 09 h 00 à 17 h 00 par défaut.
***
![Numéro 2](../images/sfbcallout2.png)<br/>Pour modifier les heures d'ouverture, mettez en surbrillance les heures d'ouverture que vous voulez définir à l'aide du calendrier. Le calendrier permet de sélectionner les heures d’ouverture de 30 minutes, et les heures ouvrées que vous sélectionnez ici sera définies en fonction du fuseau horaire que vous avez définie dans la page **informations générales** . Pour configurer une coupure (pour le déjeuner, par exemple), désélectionnez ou faites glisser pour désélectionner l'heure dans le calendrier. Vous pouvez définir plusieurs sauts dans les heures de bureau. 
   
### <a name="select-business-hours-call-handling-page"></a>Sélectionner Page de gestion des appels des heures de bureau

> [!TIP]
> Si vous utilisez un planning des heures d'ouverture personnalisé, vous devrez également configurer le traitement des appels hors heures d'ouverture. Une page de **traitement des appels hors heures d'ouverture** sera ajoutée pour vous permettre de configurer ces options. Vous disposerez d'options identiques à celles de la page de **traitement des appels pendant les heures d'ouverture**. 
  
Vous pouvez configurer le message d’accueil et invites menus que les personnes appel de numéro de téléphone du standard automatique de votre organisation entendra pendant les heures ouvrées.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Message d'accueil de l'entreprise** Le message d'accueil pendant les heures d'ouverture est facultatif et peut être défini sur **Aucun**. Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.
*    **Aucun** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.
*    **Message d’accueil de créer un fichier personnalisé** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum). Par exemple, vous pouvez entrer « Bienvenue dans Contoso. Votre appel est important pour nous. dans la zone **appelants** .
*    **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil et puis téléchargez votre fichier audio (au format .wav, .mp3 ou .wma).
***
![Numéro 2](../images/sfbcallout2.png)<br/>Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant les heures ouvrées. Vous pouvez choisir parmi les options suivantes :
*    **Se déconnecter** Si vous l’activez, la personne l’appel sera déconnectée après audition un accueil pendant les heures.
*    **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
     *    **Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Enterprise Voice ou affectée Plans de l’appel dans Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/><br/>   
        > [!Note]
        > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/><br/>

     *    Une **File d’attente des appels** L'Usage d’une file d’attente des appels permet le transfert de l'appel vers une file d’attente existante que vous avez configurée.
     *    Un autre **standard automatique** , vous pouvez utiliser un fichier automatique standard pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués.
*    **Lire une invite des options de menu** Cette option vous permet de configurer une invite à lire.
***
![Nombre 3](../images/sfbcallout3.png)<br/>**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l'invite dans la zone **Les appelants entendront** ou enregistrer un fichier audio et dire par exemple « Pour contacter le département des Ventes, dites 1 ou appuyez sur 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. » **Créer une invite personnalisée** Si vous choisissez cette option, vous devez entrer le texte que le système devra lire (jusqu'à 1 000 caractères). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).
***
![Numéro 4](../images/sfbcallout4.png)<br/>**Numérotation par nom** Si vous choisissez cette option, vous activez des personnes appellent pour rechercher des personnes dans votre organisation à l’aide de la recherche dans l’annuaire. Vous pouvez sélectionner les personnes qui seront répertoriées comme disponibles ou non disponibles pour la Numérotation par nom en configurant ces options dans la page de **portée de la numérotation**. Tout utilisateur en ligne disposant d'une licence **   Phone System**  ou de tout utilisateur hébergé sur site à l'aide de Skype Professionnel Server 2015 ou Lync Server 2013 peut être trouvé avec Composer par Nom.<br/><br/>  

> [!WARNING]
> Les utilisateurs hébergés sur site à l’aide de Lync 2010 **ne sont pas joignables** avec numérotation par nom.
***

!["Nombre 5"](../images/sfbcallout5.png)<br/>**Modifier les options de menu** Les options de menu peuvent être ajoutées ou supprimées à l'aide des touches du clavier. Pour ajouter une option de menu, appuyez sur la touche correspondante du clavier. La couleur des touches utilisées changera et la ligne d'options correspondantes apparaîtra en dessous. Pour supprimer une option de menu, cliquez sur la clé correspondante sur le contrôle pavé numérique pour désélectionner cette clé. La ligne de mappage clé sera supprimée.<br/><br/>  **Conseil :** Vous devrez mettre à jour le texte des invites de menu ou réenregistrer l’audio séparément lors de l’ajout à la suppression des options, car elle ne s’effectue automatiquement de l’invite de menu existants.  <br/><br/>  Une option de menu peut être ajoutée et supprimée dans n’importe quel ordre, et les mappages de clés ne doivent pas être continue. Il est possible, par exemple, pour créer un menu avec les touches 0, 1 et 3 mappés aux options, tandis que la touche 2 n’est pas utilisée.<br/><br/> 

> [!NOTE]
> Les touches * (répétition) et # (arrière) sont réservées par le système et ne peut pas être réaffectés. Si la reconnaissance vocale est activée, en appuyant sur * correspond à « Répéter » et # correspond avec les commandes vocales « Nouveau ».


Pour configurer vos options de menu, une fois que vous sélectionnez le(s) clé(s), vous devez : 
- **Entrez le nom de l’option** Il peut contenir jusqu'à 64 caractères et peut contenir plusieurs mots comme « Service clientèle » ou « opérations et motifs ». Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne qui appelle pourra soit appuyez sur 3, par exemple « 3 », ou dire « Service clientèle » pour sélectionner l’option mappée à la clé 3. 
- L’étape suivante consiste à sélectionner où l’appel doit être redirigé si la clé correspondante est activée, ou l’option est sélectionnée à l’aide de la reconnaissance vocale. L’appel peut être envoyé à : 
    - **Opérateur** Si l’opérateur a déjà été configuré, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffecté à une autre clé. Si l’opérateur n’est pas défini sur n’importe quelle touche, alors la commande vocale « Opérateur » sera désactivée aussi. 
    - **Une Personne de votre société** avec une licence de **Système téléphonique** qui est activée pour Voix de l'Entreprise ou affectée à un Plan d’appel dans Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.<br/><br/> 
    
        > [!Note] 
        > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge. <br/><br/>

    - Une **File d’attente d'appels** L'Usage d’une file d’attente d'appels permet le transfert de l'appel vers une file d’attente existante que vous avez configurée. 
    - Un autre **standard automatique** , vous pouvez utiliser un fichier automatique standard pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués.<br/><br/>
    
        > [!Note]
        > Les **heures d’ouverture** de standards automatiques imbriqués (ou de second niveau) seront également utilisé, y compris pour les appels envoyés à partir d’autres standards automatiques qui ont été définis.         
   
### <a name="select-holidays-page"></a>Sélectionnez page de congés 

Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.
  
![Définition des congés dans le standard automatique](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Ajouter un jour férié** Entrez un nom pour votre nouveau congé dans le champ **nom du congé** .<br/><br/> Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être unique pour le même standard automatique. Par exemple, vous ne pouvez pas de jours fériés nommés « Actiondegrâce » dans le même standard automatique.  
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Message d’accueil de congé** Le message d’accueil du congé est facultatif et peut être définie sur **None**. Dans ce cas, l'appelant n'entendra aucun message ou salutation avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale.
*    **Aucun** Aucun message d’accueil ne sera lu quand personnes appellent au numéro de téléphone du standard automatique.
*    **Message d’accueil de créer un fichier personnalisé** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système pour lire (1000 caractères maximum). Par exemple, vous pouvez entrer « bonne année ! Nos bureaux sont actuellement fermés. dans la zone **appelants** .
*    **Télécharger un fichier audio** Si vous choisissez cette option, enregistrer le message d’accueil de congé et puis téléchargez votre fichier audio (au format .wav, .mp3 ou .wma).  
***
![Nombre 3](../images/sfbcallout3.png)<br/>**Que se passe-t-il pour les appels après le message d’accueil ?** Vous pouvez sélectionner que se passe-t-il pour les appels qui arrivent pendant cette période de congé. Vous pouvez choisir parmi les options suivantes :
*    **Se déconnecter** La personne qui appel sera déconnectée après avoir entendu le message d’accueil du congé.
*    **Rediriger un appel** Cela peut servir à envoyer automatiquement l’appel vers :
     *    Une**  Personne de votre société**  disposant  d'une licence de ** Système téléphonique**  qui est activée pour Voix de l'Enterprise ou de plans d'appels associés dans Office 365. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société**et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/><br/> 
     
         > [!Note] 
         > **Une Personne dans votre entreprise** peut être un utilisateur en ligne ou un utilisateur hébergé sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Lync Server 2010 n’est pas pris en charge.<br/><br/>

     *    Une **File d’appel en attente** pour transférer l’appel à un file d'appel existante que vous avez configurées.
     *    Un autre **standard automatique**, pour créer un second niveau d’options de menu qui contient un sous-menu. Il s’agit des standards automatiques imbriqués. <br/><br/>
     
         > [!Note]
         > Par défaut, tous les appels arrivant pendant une période de congé sont définies pour déconnecter la session après le message d’accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.

***
![Numéro 4](../images/sfbcallout4.png)<br/>**Quand souhaiterez-vous que le congé commence et finisse?** Entrez la date de début du congé au format jj/mm/aaaa, puis sélectionnez une heure de début, date de fin et l’heure de fin, à l’invite de la table de plage de date.<br/><br/>Vous pouvez spécifier jusqu'à 10 différentes plages de dates pour une période de congé. Par exemple, vous pouvez ajouter des plages de dates pour les jours fériés réveillon du nouvel an jusqu'à dix ans. Une période de congé peut s’étendre sur plusieurs jours.<br/><br/>Pour ajouter d’autres plages de jours fériés (par exemple, pour l’année suivante), cliquez sur **Ajouter un autre**, puis entrez un nouveau jeu de dates de début et de fin pour la période de congé.<br/><br/>Jours fériés imbriqués sont également pris en charge. Par exemple, vous pouvez imbriquer plusieurs congés dans un délai de « vacances » : 
*    **24 décembre par le biais du 3 janvier :** « Bonnes vacances ! Nos bureaux sont actuellement fermés. Il s’ouvre à nouveau le 4 janvier. »
*    ** 25 décembre : **     « Joyeux Noël ! Nos bureaux sont actuellement fermés. Il s’ouvre à nouveau le 4 janvier. »
*    **Le 1er janvier :** « Heureuse année ! Nos bureaux sont actuellement fermés. Il s’ouvre à nouveau le 4 janvier. »
   
Après avoir enregistré votre standard automatique, vos congés apparaissent sous l’onglet de **congés** , où vous pouvez modifier, ajouter ou modifier les paramètres de la période de congé.
  
### <a name="select-dial-scope-page"></a>Page de sélection de la portée de la numérotation

Dans cette page, vous pouvez configurer les utilisateurs de votre organisation seront répertoriés dans le répertoire et disponibles pour la numérotation par nom lorsqu’une personne qui appelle votre organisation.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>L'option **Inclure** présente deux choix :
*    **Tous les utilisateurs en ligne** Cette option permet d'inclure toutes les personnes de votre organisation dans la recherche dans l'annuaire. Tous les utilisateurs en ligne avec une licence de **Système téléphonique** , ainsi que les utilisateurs hébergés sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013 qui ont des Plans d’appel dans Office 365, apparaîtront. 
*    **Personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, une liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation et les personnes ajoutées à ce groupe dans Office 365, liste de distribution ou groupe de sécurité qui sont soit **utilisateurs en ligne avec un Licence de système téléphonique** ou hébergée sur site à l’aide de Skype Professionnel Server 2015 ou Lync Server 2013. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité. <br/><br/> 

    > [!Caution]
    > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>À l’aide de l’option **Exclure** , vous disposez de deux options :
*    **Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire. 
*    **Personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe dans Office 365, liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et tous les utilisateurs ajoutés à ce groupe d’Office 365, liste de distribution, ou groupes de sécurité seront exclus de la recherche dans l’annuaire. Vous pouvez ajouter plusieurs groupes d’Office 365, les listes de distribution et les groupes de sécurité. <br/><br/> 

    > [!Caution]
    > Les utilisateurs locaux des déploiements de Lync Server 2010 ne s’affichera lorsqu’un utilisateur recherche l’annuaire à l’aide de la numérotation par nom.          
   
> [!NOTE]
> Cela peut prendre jusqu'à 36 heures pour un nouvel utilisateur à leur nom apparaît dans le répertoire lorsqu’une personne utilise la numérotation par un nom pour la reconnaissance vocale. 
  
Une fois que vous entrez tous les champs obligatoires et que vous définissez des menus et les options de gestion des appels, cliquez sur **Enregistrer**.
  
## <a name="editing-and-testing-auto-attendants"></a>Modification et le test des standards automatiques

Après avoir enregistré votre standard automatique, il sera répertorié dans la page des **standards automatiques**. Cela vous permettra de voir rapidement les options que vous avez configuré, notamment le nom, numéro de téléphone, langue et le statut.
  
Si vous souhaitez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis cliquez sur **Modifier**dans le volet Actions.
  
Vous pouvez également rapidement placer un test d’appel pour le standard automatique en utilisant le bouton de **Test** dans le volet Actions.
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.
  
### <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.
  
||| 
|---|---|
[Nouvelle CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [Nouvelle CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [Nouvelle CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [Nouvelle CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [Nouvelle CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Nouvelle CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [Nouvelle CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [Nouvelle CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [Nouvelle CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Nouvelle CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Que sont les standards automatiques de système téléphonique ?](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Exemple de petite entreprise - configurer un standard automatique](tutorial-org-aa.yml)  