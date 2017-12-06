---
title: "Configurer un standard automatique de système téléphonique"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# Configurer un standard automatique de système téléphonique

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/6fc2687c-0abf-43b8-aa54-7c3b2a84b67c). 
  
Les standards automatiques permettre aux utilisateurs qui appeler votre organisation et parcourir un système de menus à les atteindre le bon service, appelez file d'attente, la personne ou l'opérateur. Vous pouvez créer un standard automatique pour votre organisation à l'aide de la Skype pour centre d'administration entreprise. Pour créer un nouveau standard automatique, accédez à **routage d'appel** dans le volet de navigation gauche, puis sélectionnez **les standards automatiques** > **Ajouter nouveau**.
  
Si vous voulez en savoir plus sur les standards automatiques, voir [Quelles sont les standards automatiques système téléphonique ?](what-are-phone-system-auto-attendants.md).
  
## Étape 1 : prise en main

- Avant de pouvoir créer et configurer vos standards automatiques, vous devrez obtenir ou transférer votre numéro payant existant ou un service gratuit nombres. Une fois que vous obtenez le numéro payant ou les nombres de service gratuit, ils s'affichent sur **Skype centre d'administration entreprise** > **vocale** > page de **numéros de téléphone**. Pour obtenir vos numéros de service, voir [Obtention des numéros de téléphone des services Skype Entreprise](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md), ou si vous souhaitez transférer et numéro de service existant, voir [Transférer des numéros de téléphone vers Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). Numéros des **utilisateurs (abonné)** ne peut pas être affectées aux standards automatiques. Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype centre d'administration entreprise pour obtenir des numéros de service ; Accédez[Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place.
    
    > [!CAUTION]
    > Pour obtenir et utiliser des numéros de téléphone, vous devez configurer les Communications crédits. À suivre, consultez [Que sont les Communications crédits ?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) et[Configurer les Communications crédits pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Votre organisation doit avoir (au minimum) une licence entreprise E3 plus **Système téléphonique** ou une licence entreprise E5. Le nombre de licences utilisateur **Système téléphonique** affectés affecte le nombre de numéros de service sont disponibles pour être utilisés pour les standards automatiques. Les nombres de standards automatiques que vous pouvez avoir dépendant les numéros **Système téléphonique** et **Audioconférence** des licences qui sont affectées dans votre organisation. Pour en savoir plus sur les licences, accédez[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu est un utilisateur en ligne avec une licence **Système téléphonique**, vous devez les activer pour Enterprise Voice ou appel d'offre dans Office 365 leur attribuer. Voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Vous pouvez également utiliser Windows PowerShell. Par exemple exécuter :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`. 
  
## Étape 2 : création d'un standard automatique

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Standards automatiques**, puis cliquez sur **Ajouter nouveau**:
  
### Page de modification des informations générales

Dans la page **Modifier les informations générales**:
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nom** Entrez un nom d'affichage de la description pour le standard automatique. Le nom est requis et peut contenir jusqu'à 64 caractères, espaces compris. Il apparaît dans la colonne **nom** sous l'onglet **standards automatiques**.  <br/> |
|**2** <br/> |**Numéro de téléphone** Ce paramètre est facultatif. Si vous le souhaitez, sélectionnez un numéro de téléphone pour le standard automatique. Vous pouvez choisir n'importe quel numéro payant service disponible ou le numéro de téléphone gratuit dont vous disposez pour votre organisation. S'il n'y a aucun numéro de téléphone répertorié, vous devrez obtenir un numéro payant service ou téléphone gratuit nombre. Accédez[Obtention des numéros de téléphone des services Skype Entreprise](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) pour les obtenir. <br/> > [!NOTE]> Les numéros d' **utilisateurs (abonnés)** ne peuvent pas être attribués à des standards automatiques.          |
|**3** <br/> |**Fuseau horaire** Vous devez définir le fuseau horaire pour votre standard automatique, mais il ne doit pas nécessairement correspondre à celui de l'adresse principale de votre organisation. Vous pouvez définir un fuseau horaire différent pour chaque standard automatique et les horaires d'ouverture du standard automatique seront définies en fonction du fuseau horaire sélectionné. <br/> |
|**4** <br/> |**Langue** Sélectionnez la langue que vous souhaitez utiliser pour le standard automatique à partir d'une des langues répertoriées. La langue que vous définissez ici est la langue dans laquelle le standard automatique utilisera pour interagir avec des personnes qui appeler ce standard automatique, et toutes les invites système seront lu dans cette langue. <br/> |
|**5** <br/> |**La reconnaissance vocale** Reconnaissance vocale est disponible et si cette option est sélectionnée. Les personnes qui rejoignent peuvent utiliser entrée vocale dans la langue définie. Vous pouvez désactiver la reconnaissance vocale en le désactivant si vous voulez uniquement permettre aux utilisateurs d'utiliser leur clavier téléphonique. <br/> |
|**6** <br/> |**Opérateur** Cette étape est facultative et ne doit pas être définies pour le standard automatique. Toutefois, vous pouvez définir l'option **opérateur** pour les personnes qui rejoignent doivent pouvoir sortir les menus à parler à une personne afin de. <br/>  La touche 0 est automatiquement affectée à l'option Opérateur. <br/>  Si vous configuré ces paramètres, vous devrez également Informez les personnes qui appeler dans où il s'agit d'une option dans **menu options d'édition** disponible dans la page **Gestion des appels les heures de bureau**. Si vous définissez un opérateur sur votre standard automatique, vous devrez entrer le texte d'invite correspondant dans la zone **appelants** ou modifier votre fichier audio pour inclure cette option. Par exemple, « pour l'opérateur, appuyez sur zéro. » <br/>  L'opérateur peut être défini comme suit : <br/>  Une **personne de votre société** avec une licence **Système téléphonique** qui est activée pour voix entreprise ou affectée appel d'offre dans Office 365. <br/> > [!NOTE]> **Personne de votre société** peut être un utilisateur en ligne ou un utilisateur hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013. Lync Server 2010 n'est pas pris en charge.           Une **file d'attente d'appels** que vous avez configurée. <br/>  Vous pouvez le configurer la la personne appelant est envoyés vers la messagerie vocale. Pour ce faire, sélectionnez **personne de votre société** et définissez les appels soient transférés directement vers la messagerie vocale de cette personne. <br/> |
   
### Page de sélection des heures d'ouverture

Par défaut, les heures de bureau sont définies à 24 heures, les jours, toutes les heures sont considérées comme les heures de bureau. Toutes les heures qui ne sont pas inclus dans les heures de bureau sont considérés comme après les heures de bureau. Si vous sélectionnez l'option **personnalisée** et définissez vos heures de travail, puis une nouvelle page appelée **après la gestion des appels heures** est ajoutée dans lequel vous pouvez configurer la gestion des appels pour après les heures de bureau pour le standard automatique.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |Sélectionnez l'option **Personnaliser** pour définir les heures d'ouverture spécifiques dans le calendrier. Lorsque vous sélectionnez **Personnaliser**, les heures d'ouverture seront définies du lundi au vendredi, de 09 h 00 à 17 h 00 par défaut.  <br/> |
|**2** <br/> |Pour modifier les heures de bureau, mettez en surbrillance les heures d'ouverture pour définir l'aide du calendrier. Le calendrier vous permet de sélectionner les heures de bureau de 30 minutes et les heures de travail que vous sélectionnez ici sera définies selon le fuseau horaire que vous avez défini dans la page **informations générales**. Pour configurer un saut (par exemple, une pause déjeuner), désactivez l'option ou faites glisser pour désélectionner l'heure dans le calendrier. Vous pouvez définir plusieurs sauts dans les heures de bureau.  <br/> |
   
### Sélectionnez les heures de bureau appeler page de gestion des

> [!TIP]
> Si vous utilisez un planning des heures d'ouverture personnalisé, vous devrez également configurer le traitement des appels hors heures d'ouverture. Une page de **traitement des appels hors heures d'ouverture** sera ajoutée pour vous permettre de configurer ces options. Vous disposerez d'options identiques à celles de la page de **traitement des appels pendant les heures d'ouverture**. 
  
Vous pouvez configurer le message d'accueil, les invites et les menus que les personnes appel dans numéro de téléphone standard automatique de votre organisation entendront pendant les heures d'ouverture.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**Message d'accueil de l'entreprise** Le message d'accueil pendant les heures d'ouverture est facultatif et peut être défini sur **Aucun**. Dans ce cas, l'appelant n'entendra aucun message avant le traitement de son appel par l'une des options sélectionnées. Vous pouvez également charger un fichier audio (au format .wav, mp3 ou .wma), ou créer un messager d'accueil personnalisé à l'aide de la synthèse vocale. **Aucun** Aucun message d'accueil n'est émis lorsque les personnes appellent le numéro de téléphone standard automatique. **Créer un fichier personnalisé formule d'appel** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système à lire (jusqu'à 1000 caractères). Par exemple, vous pouvez entrer « Bienvenue Contoso. Votre appel est important pour nous. » dans la zone **appelants**. **Télécharger un fichier audio** Si vous sélectionnez cette option, enregistrer le message d'accueil, puis téléchargez votre fichier audio (au format .wav, MP3 ou .wma).|
|**2**| Vous pouvez sélectionner qu'advient-il des appels arrivent pendant les heures de bureau. Vous pouvez choisir parmi les options suivantes : **Déconnecter** Si vous sélectionnez cette option, l'appelant sera déconnecté après avoir écouté un message d'accueil d'heures d'ouverture. **Rediriger l'appel** Cette option peut être utilisée pour envoyer automatiquement l'appel vers : **Personne de votre société** avec une licence **Système téléphonique** qui est activée pour voix entreprise ou affectée appel d'offre dans Office 365. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez **personne de votre société** et définissez cette personne doit avoir leurs appels transférés directement vers la messagerie vocale.> [!NOTE]> **Personne de votre société** peut être un utilisateur en ligne ou un utilisateur hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013. Lync Server 2010 n'est pas pris en charge.           Une **file d'attente d'appels** L'utilisation d'une file d'attente permet de transférer l'appel vers une file d'attente d'appels que vous avez configurée. Un autre **standard automatique** Vous pouvez utiliser un standard automatique existant pour créer un second niveau d'options de menu contenant un sous-menu, appelé standard automatique imbriqué. **Lire une invite des options de menu** Cette option vous permet de configurer une invite à lire.|
|**3**|**Invite de menu** Pour créer une invite de menu principale, vous pouvez utiliser la synthèse vocale ou charger un fichier audio (.wav, .mp3 ou .wma). Vous pouvez taper l'invite dans la zone **Les appelants entendront** ou enregistrer un fichier audio et dire par exemple « Pour contacter le département des Ventes, dites 1 ou appuyez sur 1. Pour contacter le département des Services, dites 2 ou appuyez sur 2. Pour contacter le service clientèle, dites 3 ou appuyez sur 3. Pour contacter l'opérateur, dites 0 ou appuyez sur 0. Pour réécouter ce menu, appuyez sur étoile ou dites répéter. » **Créer une invite personnalisée** Si vous choisissez cette option, vous devez entrer le texte que le système devra lire (jusqu'à 1 000 caractères). **Charger un fichier audio** Si vous choisissez cette option, vous devrez enregistrer le message d'accueil puis charger votre fichier audio (au format .wav, .mp3 ou .wma).|
|**4**|**Numérotation par nom** Si vous choisissez cette option, cela permettra personnes qui rejoignent pour rechercher des personnes de votre organisation à l'aide de la recherche dans l'annuaire. Vous pouvez sélectionner que les utilisateurs seront répertoriés comme disponible ou n'est pas disponible pour les appels par nom en configurant ces options dans la page **étendue de numérotation**. Tout utilisateur possédant une licence **Système téléphonique** en ligne, ou tout utilisateur hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013, vous pouvez trouver avec numérotation par son nom.> [!CAUTION]> Les utilisateurs hébergés en local à l'aide de Lync 2010 **ne peuvent pas être atteintes** avec numérotation par son nom.          |
|**5**|**Modifier les options de menu** Options du menu peuvent être ajoutées ou supprimées sur le clavier à l'aide des boutons clés. Pour ajouter une option de menu, appuyez sur la touche correspondante à l'aide du clavier. Les touches en cours d'utilisation met en couleur et la ligne correspondante des options s'affichent en dessous. Pour supprimer une option de menu, cliquez simplement sur la touche correspondante au contrôle du pavé numérique pour désélectionner cette touche. La ligne de mappage de clé a été supprimée.> [!TIP]> Vous devez mettre à jour le texte des invites de menu ou réenregistrer le son séparément lors de l'ajout à la suppression des options, car il ne s'effectue automatiquement pour l'invite de menu existant.           Une option de menu peut être ajoutée et supprimée dans n'importe quel ordre, et les mappages de clés ne doivent pas être continue. Il est possible, par exemple, pour créer un menu avec touches 0, 1 et 3 mappés aux options, alors que la clé 2 n'est pas utilisée.> [!NOTE]> Les touches * (répétition) et # (arrière) sont réservés par le système et ne peut pas être réaffectée. Si la reconnaissance vocale est activée, appuyez sur * correspondra à « Répéter » et # correspondra avec les commandes vocales « Précédent ».           |
|| Pour configurer vos options de menus, sélectionnez la ou les touches et procédez comme suit : **Entrez le nom de l'option** Cela peut contenir jusqu'à 64 caractères et peut contenir plusieurs mots tels que « Service clientèle » ou « opérations et motifs ». Si la reconnaissance vocale est activée, le nom sera automatiquement reconnu et la personne appelant seront en mesure une press 3, dites « trois », ou dites « Service clientèle », activez la case à cocher mappée à clé 3. L'étape suivante consiste à sélectionner la destination de transfert de l'appel lorsque l'appelant appuie sur la touche correspondance ou que l'option est sélectionnée à l'aide de la reconnaissance vocale. L'appel peut être envoyé vers : **Opérateur** Si l'opérateur a déjà été configurée, il est automatiquement mappé à la clé de 0, mais il peut également être supprimé ou réaffectée à une autre clé. Si l'opérateur n'est pas défini sur une touche quelconque, les commandes vocales « Opérateur » seront désactivés trop. Une **personne de votre société** avec une licence **Système téléphonique** qui est activée pour voix entreprise ou affectée un Plan d'appel dans Office 365. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez **personne de votre société** et définissez cette personne doit avoir leurs appels transférés directement vers la messagerie vocale.> [!NOTE]> **Personne de votre société** peut être un utilisateur en ligne ou un utilisateur hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013. Lync Server 2010 n'est pas pris en charge.          **Appeler file d'attente** En utilisant une option de file d'attente d'appel permet l'appel d'être transférés vers une file d'attente appel existant que vous avez configuré. Un **standard automatique** Vous pouvez utiliser un standard automatique existant pour créer un second niveau d'options de menu contenant un sous-menu, appelé standard automatique imbriqué.> [!NOTE]>  Les **horaires d'ouverture** de standards automatiques imbriquée (ou de second niveau) seront également utilisées, notamment pour les appels envoyés à partir d'autres standards automatiques qui ont été créés.          |
   
### Sélectionnez les jours fériés page (disponible pour les clients Preview uniquement)

Vous pouvez ajouter jusqu'à 20 jours fériés planifiées à chaque standard automatique.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
|||
|:-----|:-----|
|**1**|**Ajouter un jour férié** Entrez un nom pour votre jour férié dans le champ **nom du jour férié**.Noms des jours fériés peuvent contenir jusqu'à 64 caractères et doivent être uniques pour le standard automatique de même. Par exemple, vous ne peut pas contenir deux jours fériés intitulées « Fête du travail » dans le même standard automatique.|
|**2**|**Formule d'appel des jours fériés** Les jours fériés salutation est facultative et peut être défini sur **Aucun**. Dans ce cas, l'appelant n'entendront aucun message ou une carte de vœux avant que l'appel est géré par l'une des options que vous sélectionnez. Vous pouvez également télécharger un fichier audio (dans les formats .wav, mp3 ou .wma), ou créer un message d'accueil personnalisé à l'aide de la fonctionnalité de synthèse vocale. **Aucun** Aucun message d'accueil n'est émis lorsque les personnes appellent le numéro de téléphone standard automatique. **Créer un fichier personnalisé formule d'appel** Si vous choisissez cette option, entrez le texte que vous souhaitez que le système à lire (jusqu'à 1000 caractères). Par exemple, vous pouvez entrer « bonne année ! Nos bureaux est actuellement fermé. » dans la zone **appelants**. **Télécharger un fichier audio** Si vous sélectionnez cette option, enregistrer le message d'accueil de vacances, puis téléchargez votre fichier audio (au format .wav, MP3 ou .wma).|
|**3**|**Que se passe-t-il pour les appels après la carte de vœux ?** Vous pouvez sélectionner ce qui se passe pour les appels arrivent pendant ces vacances. Vous pouvez choisir parmi les options suivantes : **Se déconnecter** La personne appelant sera déconnectée après avoir entendu le message d'accueil congés. **Rediriger l'appel** Cette option peut être utilisée pour envoyer automatiquement l'appel vers : Une **personne de votre société** avec une licence **Système téléphonique** qui est activée pour voix entreprise ou affectée appel d'offre dans Office 365. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez la **personne de votre société** et définissez cette personne doit avoir leurs appels transférés directement vers la messagerie vocale.> [!NOTE]> **Personne de votre société** peut être un utilisateur en ligne ou un utilisateur hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013. Lync Server 2010 n'est pas pris en charge.           Une **File d'attente d'appel** pour transférer l'appel à un appel file d'attente existante que vous avez configuré Un autre **standard automatique**, pour créer un deuxième niveau des options de menu contenant un sous-menu. Il s'agit standards automatiques imbriquée. > [!NOTE]>  Par défaut, tous les appels arrivant pendant une période de jours fériés sont définis pour vous déconnecter après le message d'accueil (le cas échéant), vous devez spécifier une redirection si vous souhaitez un comportement différent.          |
|**4**|**Auxquelles vous voulez le jour férié de début et fin ?** Entrez la date de début du jour férié au format jj/mm/aaaa, puis sélectionnez une heure de début, une date de fin et une heure de fin, que vous y êtes invité dans la table de plage de dates.Vous pouvez spécifier jusqu'à 10 différentes plages de dates pour un jour férié. Par exemple, vous pouvez ajouter des plages de dates pour les jours fériés réveillon du nouvel an de dix ans. Un jour férié peut couvrir plusieurs jours.Pour ajouter d'autres date du jour férié plages (par exemple, pour l'année suivante), cliquez sur **Ajouter un autre**, puis entrez un nouvel ensemble de dates de début et de fin du jour férié.Les jours fériés imbriqués sont également pris en charge. Par exemple, vous pouvez imbriquer plusieurs jours fériés dans un intervalle de temps « vacances » : **· Le mois de décembre 24 via 3 janvier :** « fêtes de fin ! Nos bureaux est fermées actuellement. Nous s'ouvre à nouveau sur janvier 4e. » **· 25 décembre :** « Noël ! Nos bureaux est fermées actuellement. Nous s'ouvre à nouveau sur janvier 4e. » **· 1er janvier :** « bonne année ! Nos bureaux est fermées actuellement. Nous s'ouvre à nouveau sur janvier 4e. »|
   
Après avoir enregistré votre standard automatique, fêtes apparaissent sous l'onglet **des jours fériés**, où vous pouvez modifier, ajouter ou modifier les paramètres de congés.
  
### Page de sélection de la portée de la numérotation

Dans cette page, vous pouvez configurer les utilisateurs de votre organisation seront répertoriés dans votre annuaire et disponibles pour les appels par nom lorsqu'une personne les appels à votre organisation.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | L'option **Inclure** présente deux choix : <br/> **Tous les utilisateurs** À l'aide de cette option permet de toutes les personnes de votre organisation à inclure dans la recherche dans l'annuaire. Tous les utilisateurs en ligne avec une licence **Système téléphonique**, ainsi que les utilisateurs hébergés en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013 disposant d'appel d'offre dans Office 365, s'affichent.  <br/> **Personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe Office 365, une liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation et les personnes ajouté à ce groupe Office 365, une liste de distribution ou un groupe de sécurité qui sont soit **des utilisateurs en ligne avec un Licence du système téléphonique** ou hébergé en local à l'aide de Skype entreprise Server 2015 ou Lync Server 2013. Vous pouvez ajouter plusieurs groupes Office 365, les listes de distribution et les groupes de sécurité. <br/> > [!CAUTION]>  Utilisateurs locaux dans les déploiements de Lync Server 2010 ne sont pas répertoriés lorsqu'une personne recherche dans l'annuaire à l'aide de numérotation par son nom.          |
|**2** <br/> | L'option **Exclure** présente deux choix : <br/> **Aucun** Cette option indiquera qu'aucun utilisateur en ligne ne sera exclu de la recherche dans l'annuaire. <br/> **Personnalisé** Si vous utilisez cette option, vous pouvez rechercher un groupe Office 365, une liste de distribution ou un groupe de sécurité qui a été créé dans votre organisation, et toutes les personnes ajouté à ce groupe Office 365, liste de distribution, ou groupes de sécurité seront exclus de la recherche dans l'annuaire. Vous pouvez ajouter plusieurs groupes Office 365, les listes de distribution et les groupes de sécurité. <br/> > [!CAUTION]>  Utilisateurs locaux dans les déploiements de Lync Server 2010 ne sont pas répertoriés lorsqu'une personne recherche dans l'annuaire à l'aide de numérotation par son nom.          |
   
> [!NOTE]
> Il peut prendre jusqu'à 36 heures pour un utilisateur pour que leur nom apparaît dans le répertoire lorsque quelqu'un utilise numérotation par nom avec la reconnaissance vocale. 
  
Une fois que vous entrez tous les champs requis et configurez la gestion des menus et options d'appels, cliquez sur **Enregistrer**.
  
## Modification et le test standards automatiques

Une fois que vous avez enregistré votre standard automatique, il doit être répertorié dans la page **standards automatiques**. Cela vous permettra de voir rapidement les options que vous avez configuré, y compris le nom, numéro de téléphone, langue et état.
  
Si vous souhaitez apporter des modifications à un standard automatique, sélectionnez le standard automatique, puis cliquez sur **Modifier** dans le volet Action.
  
Vous pouvez également rapidement placer un appel test pour le standard automatique en utilisant le bouton **tester** dans le volet Action.
  
## Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des standards automatiques.
  
### Applets de commande de standard automatique

Voici les applets de commande requis pour gérer un standard automatique.
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
|[Exporter-CsOrganizationalAutoAttendantHolidays (clients Preview uniquement)](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Get-CsOrganizationalAutoAttendantHolidays (clients Preview uniquement)](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Importer-CsOrganizationalAutoAttendantHolidays (clients Preview uniquement)](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
|[Nouveau-CsOnlineDateTimeRange (clients Preview uniquement)](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   
### Informations supplémentaires sur PowerShell Windows

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

