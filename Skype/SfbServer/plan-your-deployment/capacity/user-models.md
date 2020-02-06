---
title: Modèles utilisateur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: Les modèles d’utilisateur décrits ici fournissent la base des mesures de planification de capacité et des recommandations décrites dans planification de la capacité utilisation du modèle utilisateur pour Skype entreprise Server.
ms.openlocfilehash: f1bf079fa425d98b3619eb4ccd975253784f4fbe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816033"
---
# <a name="user-models-in-skype-for-business-server"></a>Modèles utilisateur dans Skype entreprise Server
 
Les modèles d’utilisateur décrits ici fournissent la base des mesures de planification de capacité et des recommandations décrites dans planification de la [capacité utilisation du modèle utilisateur pour Skype entreprise Server](user-model.md).
  
## <a name="skype-for-business-server-user-models"></a>Modèles d’utilisateur Skype entreprise Server

Le tableau suivant décrit le modèle utilisateur pour l’enregistrement, les contacts, la messagerie instantanée et la présence pour Skype entreprise Server.
  
**Modèle utilisateur pour l’environnement et l’enregistrement**

|**Catégorie**|**Description**|
|:-----|:-----|
|Taille et distribution de déploiement  <br/> |Nous modélisons un déploiement important comptant trois sites centraux, avec un pool frontal par site.  <br/> |
|Pourcentage d’utilisateurs Active Directory  <br/> |Nous supposons que 70% de tous les utilisateurs d’Active Directory au sein de l’organisation sont activés pour Skype entreprise Server. 80% de ces utilisateurs activés sont connectés à Skype entreprise Server chaque jour (80% d’accès concurrentiel). Le nombre d’employés dans le reste de cette section concerne des utilisateurs connectés simultanément.  <br/> |
|Modifications Active Directory  <br/> |Nous supposons que 0,5% du total des utilisateurs sont créés et activés pour Skype entreprise dans Active Directory chaque semaine, et qu' 0,5% du total des utilisateurs sont désactivés à partir d’Active Directory et de Skype entreprise chaque semaine. 5% des utilisateurs disposent d’au moins un attribut Active Directory modifié chaque semaine.  <br/> |
|Groupes de distribution Active Directory  <br/> |Nous partons du principe que le nombre de groupes de distribution Active Directory au sein de l’organisation est égal à trois fois supérieur au nombre de tous les utilisateurs dans Active Directory. Les groupes de distribution possèdent les tailles suivantes :  <br/> • 64% possèdent 2-30 utilisateurs.  <br/> • 13% possèdent des utilisateurs de 31-50  <br/> • 10% possèdent des utilisateurs de 51-100  <br/> • 13% possèdent des utilisateurs de 101-500  <br/> |
|Utilisateurs VoIP (Voix sur IP)  <br/> |60% des utilisateurs de Skype entreprise Server sont activés pour les communications unifiées (UC) (c’est-à-dire, leurs numéros de téléphone sont détenus par Skype entreprise Server).  <br/> |
|Répartition des clients enregistrés  <br/> |65% de clients exécutent le logiciel Skype entreprise, notamment Skype entreprise et Lync Phone Edition.  <br/> 30% de clients exécutant un logiciel client à partir d’une version précédente de Lync.  <br/> 5% de clients utilisant Skype entreprise Web App.  <br/> Si la mobilité est activée, nous partons du principe que 40 % des utilisateurs utilisent la mobilité en même temps que les autres options de clients inscrits mentionnées précédemment. Dans ce cas, le rapport du point de présence multiple (MPOP) client est de 1/1,9. Si la mobilité est désactivée, ce rapport est de 1/1,5.  <br/> |
|Répartition des utilisateurs distants  <br/> |70 % des utilisateurs se connectent en interne.  <br/> 30% des utilisateurs se connectant par le biais d’un serveur Edge (il est possible que vous ayez éventuellement un directeur ici, mais ce n’est pas obligatoire).  <br/> |
|Répartition des contacts  <br/> |Un utilisateur peut avoir 1 000 contacts au maximum. Cela concerne moins de 1 % des utilisateurs. Moins de 25 % des utilisateurs ont 100 contacts ou plus.  <br/> La moyenne est de 80 contacts pour les utilisateurs d’un nuage public. Parmi ces utilisateurs :  <br/> • 50% des contacts sont au sein de l’organisation. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.  <br/> • 40% des contacts sont des utilisateurs Skype.  <br/> • 10% des contacts se trouvent dans les partenaires fédérés.  <br/> La moyenne est de 50 contacts pour les utilisateurs ne pouvant pas se connecter à un cloud public. Parmi ces utilisateurs :  <br/> • 80% des contacts sont au sein de l’organisation. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.  <br/> • les personnes qui utilisent des partenaires fédérés peuvent compter de 20%.  <br/> Chaque utilisateur possède 1 groupe de distribution dans sa liste de contacts. Pour les tests de performance, nous partons du principe que les groupes de distribution sont toujours développés.  <br/> |
|Durée d’une session  <br/> |En moyenne, un utilisateur se connecte 12 heures. Tous les utilisateurs se connectent dans les 120 minutes suivant le début de la session.  <br/> |
   
**Modèle utilisateur pour la messagerie instantanée et la présence**

|**Catégorie**|**Description**|
|:-----|:-----|
|Sessions de messagerie instantanée P2P  <br/> |En moyenne, chaque utilisateur ouvre six sessions de messagerie instantanée P2P par jour.  <br/> 10 messages instantanés par session.  <br/> Chaque message est associé à deux messages de type SIP et à 2 SIP 200 OK (pour les indicateurs d’État tels que\<«\> nom est en train d’écrire »)  <br/> |
|Sessions de messagerie instantanée de groupe  <br/> |Le nombre moyen de messages envoyés lors d’une session de messagerie instantanée pour groupes uniquement est de 5 par utilisateur.  <br/> Nombre moyen de messages envoyés dans la portion messagerie instantanée d’une conférence A/V est 2 par utilisateur.  <br/> |
|Interrogation de présence  <br/> |Globalement, nous estimons l’interrogation de présence à 60 interrogations par utilisateur et par heure. La moyenne par utilisateur est estimée à :  <br/> • Une scrutation quotidienne de la présence des utilisateurs sous l’onglet Organisation de l’utilisateur (mais pas de la liste des contacts). Le nombre moyen de personnes qui ne sont pas des contacts sous l’onglet Organisation de l’utilisateur est de 15 utilisateurs. Deux opérations d’affichage de carte de visite par jour.  <br/> • Un sondage de présence chaque fois que l’utilisateur clique sur un autre utilisateur pour démarrer une conversation, estimée à la fois par heure.  <br/> • Recherche de six utilisateurs par heure. Chaque fois que vous effectuez une recherche, une scrutation par lot est envoyée à tous les membres de la liste des résultats de recherche. Nous supposons que la taille moyenne des résultats de recherche est de 20. Si les résultats de la recherche s’affichent à l’écran, le sondage par lot est actualisé toutes les 5 minutes ; Nous partons du principe que deux mises à jour sont APPORTEES par heure.  <br/> • À l’ouverture ou la prévisualisation d’un e-mail dans Outlook, un sondage de la présence des utilisateurs dans les champs à : et CC : du courrier électronique, estimé à cinq messages électroniques par heure et quatre utilisateurs par courrier électronique.  <br/> |
|Abonnements aux informations de présence  <br/> |Lorsqu’un premier utilisateur ajoute un autre contact, il s’abonne à cinq catégories d’informations concernant ce contact. Des mises à jour de ces catégories d’informations sont envoyées automatiquement au premier utilisateur. <br/> Pour chaque client, une seule demande d’abonnement par lot est envoyée pour obtenir le statut de présence d’une moyenne de 40 contacts, avec 40 boîtes de dialogue supplémentaires afin d’obtenir la présence des contacts fédérés.  <br/> La présence des membres d’un groupe de distribution développé se détermine par les abonnements de présence permanents, et non par l’interrogation, et est modelée sous forme d’une expansion par utilisateur toutes les 2 heures.  <br/> Des abonnements courts peuvent se produire quand un utilisateur se connecte, il existe un abonnement par lot pour tous les contacts de l’utilisateur, et l’utilisateur se déconnecte bientôt. Nous partons du principe que 6 abonnements courts se font par utilisateur et par heure, où chaque abonnement dure 10 minutes. <br/> |
|Publication de présence  <br/> |En moyenne, le statut de présence est publié 4 fois par utilisateur et par heure, avec un maximum de 6 fois.  <br/> |
|Taille du document de présence  <br/> |La taille moyenne d’un document de présence complet est estimée à 4 Ko, avec un maximum de 25 Ko.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour l’utilisation d’un carnet d’adresses.
  
**Modèle utilisateur pour l’utilisation d’un carnet d’adresses**

|**Mode de recherche d’un carnet d’adresses**|**Utilisation**|
|:-----|:-----|
|Requête web du carnet d’adresses uniquement (toutes les requêtes sont effectuées par le service de requête web du carnet d’adresses)  <br/> |Quatre requêtes de préfixe quotidiennes par utilisateur.  <br/> 60 requêtes de recherche exacte quotidiennes par utilisateur. 40 % de ces requêtes sont traitées par lot, avec une moyenne de 20 contacts par requête. Les 60 % restants concernent un seul contact.  <br/> 25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.  <br/> Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.  <br/> |
|Mode mixte : utilisation du fichier de carnet d’adresses et des requêtes web. Il s’agit du mode par défaut.  <br/> |Deux types de requête uniquement sont transmis sur le réseau, à savoir les requêtes de photos et les requêtes de recherche dans toute l’entreprise.  <br/> 25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.  <br/> Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.  <br/> |
   
Le tableau ci-dessous décrit le modèle de conférence.
  
**Modèle de conférence**

|**Catégorie**|**Description**|
|:-----|:-----|
|Réunions planifiées/réunions immédiates  <br/> |60 % des réunions sont planifiées, 40 % ne le sont pas.  <br/> De toutes les réunions planifiées, nous partons du principe que 80 % correspondent à des conférences affectées et qui sont des occurrences de conférences périodiques. 10 % sont des réunions ouvertes uniques. 8 % correspondent à des réunions anonymes uniques et 2 % sont des réunions fermées uniques.  <br/> |
|Répartition des clients de conférence  <br/> |Pour les réunions planifiées :  <br/> • 65% des utilisateurs de conférences utilisent Skype entreprise 2016.  <br/> • 5% des utilisateurs de la Conférence peuvent utiliser Skype entreprise Web App.  <br/> • 30% des utilisateurs de conférences utilisent des clients antérieurs, y compris Lync 2013 et Microsoft Lync 2010.  <br/> Pour les réunions non planifiées :  <br/> • 70% des utilisateurs de conférences utilisent Skype entreprise.  <br/> • 30% des utilisateurs de conférences utilisent des clients antérieurs, y compris Lync 2013 et Microsoft Lync 2010.  <br/> |
|Simultanéité des réunions  <br/> |5 % des utilisateurs participeront à des conférences pendant les heures de travail. Ainsi, dans un pool de 80 000 utilisateurs, il peut arriver que 4 000 utilisateurs participent à tout moment à des conférences.  <br/> |
|Répartition des appels audio d’une réunion  <br/> |40 % d’appels audio VoIP et de conférences rendez-vous combinés, avec un ratio d’utilisateurs VoIP par rapport aux utilisateurs d’appels entrants égal à 3:1.  <br/> 35 % d’appels audio VoIP uniquement.  <br/> 15 % d’audioconférences rendez-vous uniquement.  <br/> 10 % sans appel audio (conférences de messagerie instantanée uniquement, avec une moyenne de cinq messages envoyés par utilisateur).  <br/> |
|Utilisation de différents médias dans le cadre des conférences  <br/> |75 % des conférences ont lieu sur Internet, notamment par des méthodes de collaboration audio ou autres.  <br/> Pour ces conférences, les autres méthodes de collaboration sont les suivantes :  <br/> **Remarque :** Ces nombres additionnent plus de 100% car une conférence peut avoir plusieurs méthodes de collaboration. <br/> • 50% Ajouter le partage d’application. Nous supposons qu’un utilisateur envoie des données avec un pic de 1,1 Mo par seconde.  <br/> • 50% Ajouter la messagerie instantanée (avec une moyenne de 2 messages par utilisateur).  <br/> • 20% Ajouter la collaboration sur les données, notamment PowerPoint ou tableau blanc, et une moyenne de 2 fichiers PowerPoint proposés par conférence, avec une taille de fichier PowerPoint moyenne de 10 Mo (sans vidéo incorporée) ou 30 Mo (avec vidéo incorporée). Moyenne de 20 annotations par tableau blanc.  <br/> • vidéo de 20%. De ces utilisateurs, 70 % participent à des conférences activées pour la vidéo multiview, où chaque utilisateur reçoit 2 à 3 flux vidéo.  <br/> • 15% Ajouter des notes partagées.  <br/> |
|Répartition des participants aux réunions  <br/> |50 % d’utilisateurs internes authentifiés.  <br/> 25 % d’utilisateurs distants authentifiés.  <br/> 15 % d’utilisateurs anonymes.  <br/> 10 % d’utilisateurs fédérés.  <br/> |
|Répartition de la participation aux réunions  <br/> |Il est simulé que les utilisateurs se joignent à la réunion dans les 5 premières minutes.  <br/> |
   
Dans les pools front-end standard, Skype entreprise Server dispose d’une taille de réunion maximum prise en charge d’utilisateurs 250. Chaque pool peut héberger 250 utilisateurs à la fois. Quand une réunion regroupant autant de participants a lieu, le pool peut également héberger d’autres conférences plus petites. Vous pouvez également prendre en charge les réunions rassemblant jusqu’à 1 000 utilisateurs en configurant un pool dédié pour les héberger. Pour plus d’informations, reportez-vous à la section [planifier des réunions de grande envergure dans Skype entreprise Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Les conférences sont simulées comme suit :
  
- 85 % des conférences comptent quatre participants.
    
- 10 % des conférences comptent six participants.
    
- 5 % des conférences comptent 11 participants.
    
- Une conférence importante compte 250 utilisateurs.
    
Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les conférences auxquelles participent des utilisateurs d’appels entrants.
  
**Modèle utilisateur pour les conférences rendez-vous**

|**Catégorie**|**Description**|
|:-----|:-----|
|Authentifié/anonyme  <br/> |70 % des appelants se joignent anonymement et sont invités à entrer un nom enregistré. 30 % participent en tant qu’utilisateurs authentifiés.  <br/> |
|Durée de conversation et attente musicale  <br/> |Durée moyenne de conversation sans attente musicale : 50 secondes.  <br/> 50 % des appelants entendent une musique d’attente pendant 5 minutes en moyenne.  <br/> |
|Numérotation DTMF  <br/> |15 % des conférences rendez-vous ont des responsables téléphoniques. 10 % des conférences mixtes qui incluent des utilisateurs d’appels entrants ont également des responsables téléphoniques.  <br/> 20 % des responsables téléphoniques utilisent deux commandes DTMF par conférence.  <br/> |
|Langues d’annonce  <br/> |Les simulations utilisent l’anglais comme langue pour les annonces.  <br/> |
   
Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les salles d’attente de conférence.
  
**Modèle d’utilisateur pour les salles d’attente de conférence**

|**Catégorie**|**Description**|
|:-----|:-----|
|Nombre d’utilisateurs dans la salle d’attente  <br/> |5 % des utilisateurs d’appels entrants et 25 % d’utilisateurs d’autres catégories passent par la salle d’attente.  <br/> |
|Autorisation à quitter la salle d’attente  <br/> |Pendant les simulations, le présentateur autorise tous les utilisateurs à participer avant l’expiration du délai du client.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour d’autres sessions P2P.
  
**Modèle utilisateur pour les sessions P2P**

|**Catégorie**|**Description**|
|:-----|:-----|
|Partage d’application  <br/> |Chaque utilisateur participe à cinq sessions de partage d’application P2P par mois, avec une moyenne de 0,25 session par jour.  <br/> |
|Transfert de fichiers  <br/> |Chaque utilisateur participe à une session de transfert de fichiers P2P par mois (dans le cadre d’une session de messagerie instantanée), avec une moyenne de 0,05 session par jour. En moyenne, le volume transféré lors d’une session est de 1 Mo.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour les stratégies.
  
**Modèle utilisateur des stratégies**

|**Catégorie**|**Description**|
|:-----|:-----|
|Stratégies de conférence, de présence et d’archivage  <br/> |Nous partons du principe qu’il y a une stratégie globale, 10 stratégies de conférence, 4 stratégies d’archivage et 10 stratégies de présence.  <br/> |
|Stratégie vocale  <br/> |Nous supposons qu’il existe une stratégie globale et 2 stratégies de mots clés par site. 100 % des sites ont une stratégie de site et 30 % des utilisateurs sont gérés par une stratégie par utilisateur. Nous prenons pour hypothèse un plan de numérotation par site et deux itinéraires par site.  <br/> |
   
## <a name="busy-hour"></a>Heure de pointe

Pour les sessions P2P, la charge maximale est calculée à partir des « tentatives d’appels aux heures de pointe » (BHCA). Cette mesure utilisée dans le secteur de la téléphonie suppose que 50 % de tous les appels d’une journée seront passés en 20 % du temps. Elle est calculée à l’aide de la formule suivante :
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Lors d’un test de performance, l’heure de pointe a été simulée en exécutant des sessions VoIP et d’autres sessions P2P aux heures de pointe pendant au moins 1,6 heure par jour.
  
Le pic de charge des conférences suppose que 75 % de toutes les conférences d’une journée de huit heures ont lieu pendant quatre heures de pointe. Ces heures de pointe représentent 1,5 fois la charge de conférence moyenne.
  
## <a name="enterprise-voice-to-pstn-calls"></a>Appels voix entreprise vers RTC

Les affirmations suivantes s’appliquent aux appels vocaux d’entreprise :
  
- 60% des utilisateurs sont activés pour voix entreprise et 60% de ces utilisateurs sont activés pour la fonction d’appel RTC.
    
- Chacun de ces derniers utilisateurs passe 4 appels RTC pendant les heures de pointe. Chaque appel dure 3 minutes.
    
- 65 % des appels vocaux RTC utilisent la déviation du trafic multimédia.
    
## <a name="mobility"></a>Mobilité

40 % des utilisateurs inscrits sont présumés être activés pour la mobilité. Pour chacun d’entre eux, nous partons du principe que l’activité du client mobile vient s’ajouter à celle des autres instances MPOP de l’utilisateur, à l’exception des interactions en conférence pour lesquelles le client de mobilité n’est qu’un autre type de client pouvant être utilisé pour participer à des conférences.
  
## <a name="persistent-chat"></a>Conversation permanente

Nous supposons que 25 % des utilisateurs inscrits participent à des sessions de conversation permanentes avec les caractéristiques suivantes :
  
- 1,5 salle de conversation par utilisateur sont prévues en moyenne.
    
- Chaque salle de conversation engendre 12 demandes d’interrogation par heure, en ciblant une moyenne de 10 utilisateurs chacune.
    
## <a name="response-group-and-call-park"></a>Response Group et parcage d’appel

Nous supposons que 0,15 % des utilisateurs inscrits appartiennent à des groupes Response group. Nous partons du principe que 0,02 % des utilisateurs inscrits ont des appels parqués à tout moment donné.
  

