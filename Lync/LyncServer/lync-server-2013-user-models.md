---
title: 'Lync Server 2013 : Modèles utilisateur'
TOCTitle: Modèles utilisateur Lync Server 2013
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49891532
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modèles utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les modèles utilisateur présentés ici servent de base pour les mesures de planification de capacité et les recommandations décrites dans la rubrique [Planification de capacité pour Lync Server 2013 avec les modèles utilisateur](lync-server-2013-capacity-planning-using-the-user-models.md).

## Modèles utilisateur Lync Server 2013

Le tableau ci-dessous décrit le modèle utilisateur pour l’inscription, les contacts, la messagerie instantanée et la présence pour Lync Server 2013.

### Modèle utilisateur pour l’environnement et l’inscription

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taille et distribution de déploiement</p></td>
<td><p>Nous modélisons un déploiement large comptant trois sites centraux, avec un pool frontal par site.</p></td>
</tr>
<tr class="even">
<td><p>Pourcentage d’utilisateurs Active Directory</p></td>
<td><p>Nous supposons que 70 % de tous les utilisateurs Active Directory de l’entreprise sont activés pour Lync Server. 80 % des utilisateurs activés sont quotidiennement connectés à Lync Server (simultanément). Les nombres d’employés dans le reste de cette section concernent des utilisateurs connectés simultanément.</p></td>
</tr>
<tr class="odd">
<td><p>Modifications d’Active Directory</p></td>
<td><p>Nous partons du principe que 0,5 % de tous les utilisateurs sont créés et activés pour Lync dans Active Directory chaque semaine, et que 0,5 % sont désactivés d’Active Directory et de Lync chaque semaine. 5 % des utilisateurs ont au moins un attribut Active Directory modifié chaque semaine.</p></td>
</tr>
<tr class="even">
<td><p>Groupes de distribution Active Directory</p></td>
<td><p>Nous partons du principe que le nombre de groupes de distribution Active Directory dans l’organisation est égal à trois fois le nombre total des utilisateurs Active Directory. Les groupes de distribution ont les tailles suivantes :</p>
<ul>
<li><p>64 % se composent de 2 à 30 utilisateurs.</p></li>
<li><p>13 % se composent de 31 à 50 utilisateurs.</p></li>
<li><p>10 % se composent de 51 à 100 utilisateurs.</p></li>
<li><p>13 % se composent de 101 à 500 utilisateurs.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs VoIP (Voix sur IP)</p></td>
<td><p>60 % des utilisateurs Lync Server sont activés pour les communications unifiées (c’est-à-dire que leurs numéros de téléphone appartiennent à Lync Server).</p></td>
</tr>
<tr class="even">
<td><p>Répartition des clients inscrits</p></td>
<td><p>65 % des clients exécutent Lync 2013, y compris Lync et Lync Phone Edition.</p>
<p>30 % des clients exécutent un logiciel client à partir d’une version antérieure de Lync.</p>
<p>5 % des clients utilisent Lync Web App.</p>
<p>Si la mobilité est activée, nous partons du principe que 40 % des utilisateurs utilisent la mobilité en même temps que les autres options de clients inscrits mentionnées précédemment. Dans ce cas, le rapport du point of présence multiple (MPOP, Multiple Point Of Presence) client est de 1/1,9. Si la mobilité est désactivée, le rapport MPOP est de 1/1,5.</p></td>
</tr>
<tr class="odd">
<td><p>Répartition des utilisateurs distants</p></td>
<td><p>70 % des utilisateurs se connectent en interne.</p>
<p>30 % des utilisateurs se connectent par l’intermédiaire d’un serveur Edge et d’un directeur.</p></td>
</tr>
<tr class="even">
<td><p>Répartition des contacts</p></td>
<td><p>Un utilisateur peut avoir 1 000 contacts au maximum. Cela concerne moins de 1 % des utilisateurs. Moins de 25 % des utilisateurs ont 100 contacts ou plus.</p>
<p>La moyenne est de 80 contacts pour les utilisateurs d’un nuage public. Parmi ces utilisateurs :</p>
<ul>
<li><p>50% des contacts font partie de l’entreprise. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.</p></li>
<li><p>40 % des contacts sont des utilisateurs de nuage public (utilisateurs AOL, Yahoo!, MSN ou Google Talk, par exemple).</p></li>
<li><p>10% des contacts sont des partenaires fédérés.</p>

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
> </ul>

</li>
</ul>
<p>La moyenne est de 50 contacts pour les utilisateurs ne pouvant pas se connecter à un nuage public. Parmi ces utilisateurs :</p>
<ul>
<li><p>80 % des contacts font partie de l’entreprise. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.</p></li>
<li><p>20 % des contacts sont des partenaires fédérés.</p>
<p>Chaque utilisateur possède 1 groupe de distribution dans leur liste des contacts. Pour les tests de performance, nous partons du principe que les groupes de distribution sont toujours développés.</p></li>
</ul>
<p>25 % des contacts d’un utilisateur passent par le protocole XMPP.</p></td>
</tr>
<tr class="odd">
<td><p>Durée d’une session</p></td>
<td><p>En moyenne, un utilisateur se connecte 12 heures. Tous les utilisateurs se connectent dans les 120 minutes suivant le début de la session.</p></td>
</tr>
</tbody>
</table>


### Modèle utilisateur pour la messagerie instantanée et la présence

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sessions de messagerie instantanée P2P</p></td>
<td><p>En moyenne, chaque utilisateur ouvre six sessions de messagerie instantanée P2P par jour.</p>
<p>10 messages instantanés par session.</p>
<p>Chaque message est mis en équivalence par deux messages INFO SIP et par deux messages SIP 200/OK (pour les indicateurs de statut tels que « &lt;Nom&gt; tape du texte »).</p></td>
</tr>
<tr class="even">
<td><p>Interrogation de présence</p></td>
<td><p>Globalement, nous estimons l’interrogation de présence à 60 interrogations par utilisateur et par heure. La moyenne par utilisateur est estimée à :</p>
<ul>
<li><p>Une interrogation par jour de présence des utilisateurs sous l’onglet d’organisation de l’utilisateur (mais pas dans la liste des contacts). En moyenne, 15 utilisateurs ne sont pas des contacts sous l’onglet d’organisation de l’utilisateur. Deux opérations d’affichage de carte de visite par jour.</p></li>
<li><p>Une interrogation de présence à chaque fois que l’utilisateur clique sur le nom d’un autre utilisateur pour démarrer une conversation, estimée à une par heure.</p></li>
<li><p>Six recherches utilisateur sont effectuées par heure. À chaque recherche, une interrogation par lot est envoyée à tout le monde dans la liste des résultats de recherche. Nous supposons que la taille moyenne des résultats de recherche est de 20. Pour les résultats restant à l’écran, l’interrogation par lot est actualisée toutes les 5 minutes. Nous partons du principe que deux actualisations se font par heure.</p></li>
<li><p>Lorsque l’utilisateur ouvre ou prévisualise un message électronique dans Outlook, une interrogation de présence des utilisateurs dans les champs À : et CC : du message, estimée à cinq messages électroniques par heure et quatre utilisateurs par message.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Abonnements aux informations de présence</p></td>
<td><p>Lorsqu’un premier utilisateur ajoute un autre contact, il s’<em>abonne</em> à cinq catégories d’informations concernant ce contact. Des mises à jour de ces catégories d’informations sont automatiquement envoyées au premier utilisateur.</p>
<p>Pour chaque client, une seule demande d’abonnement par lot est envoyée pour obtenir le statut de présence d’une moyenne de 40 contacts, avec 40 boîtes de dialogue supplémentaires afin d’obtenir la présence des contacts fédérés.</p>
<p>La présence des membres d’un groupe de distribution développé se détermine par les abonnements de présence permanents, et non par l’interrogation, et est modelée sous forme d’une expansion par utilisateur toutes les 2 heures.</p>
<p>Les <em>abonnements courts</em> se produisent si un utilisateur ouvre une session, qu’il existe un abonnement par lot pour tous les contacts de l’utilisateur et que l’utilisateur ferme sa session peu de temps après. Nous partons du principe que 6 abonnements courts se font par utilisateur et par heure, où chaque abonnement dure 10 minutes.</p></td>
</tr>
<tr class="even">
<td><p>Publication de présence</p></td>
<td><p>En moyenne, le statut de présence est publié 4 fois par utilisateur et par heure, avec un maximum de 6 fois.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Taille du document de présence</p></td>
<td><p>La taille moyenne d’un document de présence complet est estimée à 4 Ko, avec un maximum de 25 Ko.</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous décrit le modèle utilisateur pour l’utilisation d’un carnet d’adresses.

### Modèle utilisateur pour l’utilisation d’un carnet d’adresses

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mode de recherche d’un carnet d’adresses</th>
<th>Utilisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Requête web du carnet d’adresses uniquement (toutes les requêtes sont effectuées par le service de requête web du carnet d’adresses)</p></td>
<td><p>Quatre requêtes de préfixe quotidiennes par utilisateur.</p>
<p>60 requêtes de recherche exacte quotidiennes par utilisateur. 40 % de ces requêtes sont traitées par lot, avec une moyenne de 20 contacts par requête. Les 60 % restants concernent un seul contact.</p>
<p>25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.</p>
<p>Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.</p></td>
</tr>
<tr class="even">
<td><p>Mode mixte : utilisation du fichier de carnet d’adresses et des requêtes web Il s’agit du mode par défaut.</p></td>
<td><p>Deux types de requêtes uniquement sont transmises sur le réseau, à savoir les requêtes de photos et les requêtes de recherche dans toute l’entreprise.</p>
<p>25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.</p>
<p>Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous décrit le modèle de conférence.

### Modèle de conférence

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Réunions planifiées/réunions immédiates</p></td>
<td><p>60 % des réunions sont planifiées, 40 % ne le sont pas.</p>
<p>De toutes les réunions planifiées, nous partons du principe que 80 % correspondent à des conférences affectées et qui sont des occurrences de conférences périodiques. 10 % sont des réunions ouvertes uniques. 8 % correspondent à des réunions anonymes uniques et 2 % sont des réunions fermées uniques.</p></td>
</tr>
<tr class="even">
<td><p>Répartition des clients de conférence</p></td>
<td><p>Pour les réunions planifiées :</p>
<ul>
<li><p>65% des utilisateurs de conférence font appel à Lync 2013.</p></li>
<li><p>5 % des utilisateurs de conférence font appel à Microsoft Lync Web App.</p></li>
<li><p>30 % des utilisateurs de conférence font appel à des clients antérieurs, y compris Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 et Microsoft Office Communicator Web Access (version 2007).</p></li>
</ul>
<p>Pour les réunions non planifiées :</p>
<ul>
<li><p>70 % des utilisateurs de conférence font appel à Lync 2013.</p></li>
<li><p>30 % des utilisateurs de conférence font appel à des clients antérieurs, y compris Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 et Microsoft Office Communicator Web Access (version 2007).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Simultanéité des réunions</p></td>
<td><p>5 % des utilisateurs participeront à des conférences pendant les heures de travail. Ainsi, dans un pool de 80 000 utilisateurs, il peut arriver que 4 000 utilisateurs participent à tout moment à des conférences.</p></td>
</tr>
<tr class="even">
<td><p>Répartition des appels audio d’une réunion</p></td>
<td><p>40 % d’appels audio VoIP et de conférences rendez-vous combinés, avec un ratio d’utilisateurs VoIP par rapport aux utilisateurs d’appels entrants égal à 3:1.</p>
<p>35 % d’appels audio VoIP uniquement.</p>
<p>15 % d’audioconférences rendez-vous uniquement.</p>
<p>10 % sans appel audio (conférences de messagerie instantanée uniquement, avec une moyenne de cinq messages envoyés par utilisateur).</p></td>
</tr>
<tr class="odd">
<td><p>Utilisation de divers médias dans le cadre des conférences</p></td>
<td><p>75 % des conférences ont lieu sur Internet, notamment par des méthodes de collaboration audio ou autres.</p>
<p>Pour ces conférences, les autres méthodes de collaboration sont les suivantes :</p>

> [!NOTE]  
> Le total des nombres suivants dépasse 100 %, car une conférence peut faire appel à plusieurs méthodes de collaboration.


<ul>
<li><p>50 % utilisent le partage d’application. Nous supposons qu’un utilisateur envoie des données avec un pic de 1,1 Mo par seconde.</p></li>
<li><p>50 % font appel à la messagerie instantanée (avec en moyenne 2 messages par utilisateur).</p></li>
<li><p>20 % ont recours à la collaboration de données, à travers de PowerPoint ou d’un tableau blanc, par exemple. En moyenne, 2 fichiers PowerPoint d’environ 10 Mo (sans vidéo incorporée) ou 30 Mo (avec vidéo incorporée) chacun sont présentés au cours d’une conférence. On dénombre 20 annotations par tableau blanc en moyenne.</p></li>
<li><p>20 % utilisent de la vidéo. De ces utilisateurs, 70 % participent à des conférences activées pour la vidéo multiview, où chaque utilisateur reçoit 2 à 3 flux vidéo.</p></li>
<li><p>15 % ajoutent des notes partagées.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Répartition des participants aux réunions</p></td>
<td><p>50 % d’utilisateurs internes authentifiés.</p>
<p>25 % d’utilisateurs distants authentifiés.</p>
<p>15 % d’utilisateurs anonymes.</p>
<p>10 % d’utilisateurs fédérés.</p></td>
</tr>
<tr class="odd">
<td><p>Répartition de la participation aux réunions</p></td>
<td><p>Il est simulé que les utilisateurs se joignent à la réunion dans les 5 premières minutes.</p></td>
</tr>
</tbody>
</table>


Dans les pools frontaux habituels, Lync Server 2013 prend en charge jusqu’à 250 utilisateurs au cours d’une réunion. Chaque pool peut héberger 250 utilisateurs au cours d’une même réunion. Quand une réunion regroupant autant de participants a lieu, le pool peut également héberger d’autres conférences plus petites. Vous pouvez aussi prendre en charge les réunions rassemblant jusqu’à 1 000 utilisateurs en configurant un pool dédié pour les héberger. Pour plus d’informations, reportez-vous à [Prise en charge des réunions importantes dans Lync Server 2013](lync-server-2013-support-for-large-meetings.md).

Les conférences sont simulées comme suit :

  - 85 % des conférences comptent quatre participants.

  - 10 % des conférences comptent six participants.

  - 5 % des conférences comptent 11 participants.

  - Une conférence importante compte 250 utilisateurs.

Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les conférences auxquelles participent des utilisateurs d’appels entrants.

### Modèle utilisateur pour les conférences rendez-vous

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authentifié/anonyme</p></td>
<td><p>70 % des appelants se joignent anonymement et sont invités à entrer un nom enregistré. 30 % participent en tant qu’utilisateurs authentifiés.</p></td>
</tr>
<tr class="even">
<td><p>Durée de conversation et attente musicale</p></td>
<td><p>Durée moyenne de conversation sans attente musicale : 50 secondes.</p>
<p>50 % des appelants entendent une musique d’attente pendant 5 minutes en moyenne.</p></td>
</tr>
<tr class="odd">
<td><p>Numérotation en fréquences vocales ou DTMF (Dual Tone Multi-Frequency)</p></td>
<td><p>15 % des conférences rendez-vous ont des responsables téléphoniques. 10 % des conférences mixtes qui incluent des utilisateurs d’appels entrants ont également des responsables téléphoniques.</p>
<p>20 % des responsables téléphoniques utilisent deux commandes DTMF par conférence.</p></td>
</tr>
<tr class="even">
<td><p>Langues d’annonce</p></td>
<td><p>Les simulations utilisent l’anglais comme langue pour les annonces.</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les salles d’attente de conférence.

### Modèle d’utilisateur pour les salles d’attente de conférence

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre d’utilisateurs dans la salle d’attente</p></td>
<td><p>5 % des utilisateurs d’appels entrants et 25 % d’utilisateurs d’autres catégories passent par la salle d’attente.</p></td>
</tr>
<tr class="even">
<td><p>Autorisation à quitter la salle d’attente</p></td>
<td><p>Pendant les simulations, le présentateur autorise tous les utilisateurs à participer avant l’expiration du délai du client.</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous décrit le modèle utilisateur pour d’autres sessions P2P.

### Modèle utilisateur pour les sessions P2P

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partage d’application</p></td>
<td><p>Chaque utilisateur participe à cinq sessions de partage d’application P2P par mois, avec une moyenne de 0,25 session par jour.</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>Chaque utilisateur participe à une session de transfert de fichiers P2P par mois (dans le cadre d’une session de messagerie instantanée), avec une moyenne de 0,05 session par jour. En moyenne, le volume transféré au cours d’une session est de 1 Mo.</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous décrit le modèle utilisateur pour les stratégies.

### Modèle utilisateur des stratégies

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stratégies de conférence, de présence et d’archivage</p></td>
<td><p>Nous partons du principe qu’il y a une stratégie globale, 10 stratégies de conférence, 4 stratégies d’archivage et 10 stratégies de présence.</p></td>
</tr>
<tr class="even">
<td><p>Stratégie de la voix</p></td>
<td><p>Nous supposons qu’il existe une stratégie globale et 2 stratégies de mots clés par site. 100 % des sites ont une stratégie de site et 30 % des utilisateurs sont gérés par une stratégie par utilisateur. Nous prenons pour hypothèse un plan de numérotation par site et deux itinéraires par site.</p></td>
</tr>
</tbody>
</table>


## Heure de pointe

Pour les sessions P2P, la charge maximale est calculée à partir des « tentatives d’appels aux heures de pointe » (BHCA, Busy Hour Call Attempt). Cette mesure utilisée dans le secteur de la téléphonie suppose que 50 % de tous les appels d’une journée seront passés en 20 % du temps. Elle se calcule à l’aide de la formule suivante :

`BHCA=(total calls * 0.5) / 1.6`

Au cours d’un test de performance, l’heure de pointe a été simulée en exécutant des sessions VoIP et d’autres sessions P2P aux heures de pointe pendant au moins 1,6 heure par jour.

Le pic de charge des conférences suppose que 75 % de toutes les conférences d’une journée de huit heures ont lieu pendant quatre heures de pointe. Ces heures de pointe représentent 1,5 fois la charge de conférence moyenne.

## Voix Entreprise pour les appels RTC

Les hypothèses suivantes s’appliquent aux appels Voix Entreprise :

  - 50 % des utilisateurs sont activés pour la Voix Entreprise et 60 % sont activés pour les appels RTC.

  - Chacun de ces derniers utilisateurs passe 4 appels RTC pendant les heures de pointe. Chaque appel dure 3 minutes.

  - 65 % des appels vocaux RTC utilisent la déviation du trafic multimédia.

## Mobilité

40 % des utilisateurs inscrits sont présumés être activés pour la mobilité. Pour chacun d’entre eux, nous partons du principe que l’activité du client mobile vient s’ajouter à celle des autres instances MPOP de l’utilisateur, à l’exception des interactions en conférence pour lesquelles le client de mobilité n’est qu’un autre type de client pouvant être utilisé pour participer à des conférences.

## conversation permanente

Nous supposons que 25 % des utilisateurs inscrits participent à des sessions de chat permanentes avec les caractéristiques suivantes :

  - 1,5 salles de conversation par utilisateur sont prévues en moyenne.

  - Chaque salle de conversation engendre 12 demandes d’interrogation par heure, en ciblant une moyenne de 10 utilisateurs chacune.

## Response Group et parcage d’appel

Nous supposons que 0,15 % des utilisateurs inscrits appartiennent à des groupes Response group. Nous partons du principe que 0,02 % des utilisateurs inscrits ont des appels parqués à tout moment donné.

