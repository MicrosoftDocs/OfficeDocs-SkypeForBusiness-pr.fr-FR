---
title: Modèles utilisateur dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: Les modèles utilisateur décrits ici constituent la base pour la mesures et les recommandations décrites dans la capacité de planification de la capacité planification de l’utilisation du modèle utilisateur de Skype pour Business Server 2015.
ms.openlocfilehash: d26929f7ed9cf24ca3d13bf4f2ea7bf30172413d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-models-in-skype-for-business-server-2015"></a>Modèles utilisateur dans Skype Entreprise Server 2015
 
Les modèles utilisateur décrits ici constituent la base pour la mesures et les recommandations décrites dans [utilisation du modèle utilisateur pour Skype pour Business Server 2015 de planification de la capacité](user-model.md)de planification de la capacité.
  
## <a name="skype-for-business-server-user-models"></a>Skype pour des modèles d’entreprise serveur utilisateur

Le tableau suivant décrit le modèle utilisateur pour l’enregistrement, contacts, la messagerie instantanée (IM) et présence de Skype pour Business Server.
  
**Environnement et enregistrement utilisateur modèle**

|**Catégorie**|**Description**|
|:-----|:-----|
|Taille et distribution de déploiement  <br/> |Nous modélisons un déploiement important comptant trois sites centraux, avec un pool frontal par site.  <br/> |
|Pourcentage d’utilisateurs Active Directory  <br/> |Nous supposons que 70 % de tous les utilisateurs Active Directory dans l’organisation sont activés pour Skype pour Business Server. 80 % de ces utilisateurs activés sont connecté à Skype pour Business Server chaque jour (concurrence de 80 %). Le nombre d’employés dans le reste de cette section concerne des utilisateurs connectés simultanément.  <br/> |
|Modifications Active Directory  <br/> |Nous supposons que 0,5 % du nombre total d’utilisateurs sont créés et activés pour Skype pour l’entreprise dans Active Directory, chaque semaine, et que 0,5 % du nombre total d’utilisateurs sont désactivés à partir d’Active Directory et à partir de Skype pour entreprise chaque semaine. 5 % des utilisateurs ont au moins un attribut Active Directory modifié chaque semaine.  <br/> |
|Groupes de distribution Active Directory  <br/> |Nous supposons que le nombre de groupes de distribution Active Directory de l’organisation est égal à trois fois le nombre de tous les utilisateurs dans Active Directory. Les groupes de distribution possèdent les tailles suivantes :  <br/> • 64 % des utilisateurs de la 2-30  <br/> • 13 % ont 31 à 50 utilisateurs  <br/> • 10 % ont 51 à 100 utilisateurs  <br/> • 13 % ont 101-500 utilisateurs  <br/> |
|Utilisateurs VoIP (Voix sur IP)  <br/> |60 % de Skype pour les utilisateurs de Business Server sont activés pour les communications unifiées (CU) (autrement dit, leur téléphone numéros appartiennent par Skype pour Business Server).  <br/> |
|Répartition des clients enregistrés  <br/> |65 % des clients exécutent Skype pour les logiciels d’entreprise, notamment Skype pour les entreprises et Lync Phone Edition.  <br/> 30 % des clients exécutant le logiciel client à partir d’une version précédente de Lync.  <br/> 5 % des clients d’entreprise Web App à l’aide de Skype.  <br/> Si la mobilité est activée, nous partons du principe que 40 % des utilisateurs utilisent la mobilité en même temps que les autres options de clients inscrits mentionnées précédemment. Dans ce cas, le rapport du point de présence multiple (MPOP) client est de 1/1,9. Si la mobilité est désactivée, ce rapport est de 1/1,5.  <br/> |
|Répartition des utilisateurs distants  <br/> |70 % des utilisateurs se connectent en interne.  <br/> 30 % des utilisateurs qui se connectent à un serveur de transport Edge (peut également avoir un directeur ici, mais il n’est pas obligatoire).  <br/> |
|Répartition des contacts  <br/> |Un utilisateur peut avoir 1 000 contacts au maximum. Cela concerne moins de 1 % des utilisateurs. Moins de 25 % des utilisateurs ont 100 contacts ou plus.  <br/> La moyenne est de 80 contacts pour les utilisateurs d’un nuage public. Parmi ces utilisateurs :  <br/> • 50 % des contacts sont au sein de l’organisation. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.  <br/> • 40 % des contacts sont des utilisateurs de Skype.  <br/> • 10 % des contacts sont des partenaires fédérés.  <br/> La moyenne est de 50 contacts pour les utilisateurs ne pouvant pas se connecter à un cloud public. Parmi ces utilisateurs :  <br/> • 80 % des contacts sont au sein de l’organisation. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.  <br/> • 20 % des contacts sont des partenaires fédérés.  <br/> Chaque utilisateur possède 1 groupe de distribution dans sa liste de contacts. Pour les tests de performance, nous partons du principe que les groupes de distribution sont toujours développés.  <br/> |
|Durée d’une session  <br/> |En moyenne, un utilisateur se connecte 12 heures. Tous les utilisateurs se connectent dans les 120 minutes suivant le début de la session.  <br/> |
   
**Messagerie instantanée et présence utilisateur modèle**

|**Catégorie**|**Description**|
|:-----|:-----|
|Sessions de messagerie instantanée P2P  <br/> |En moyenne, chaque utilisateur ouvre six sessions de messagerie instantanée P2P par jour.  <br/> 10 messages instantanés par session.  <br/> Chaque message est mis en correspondance par deux messages INFO SIP et OK de 200 SIP 2 (pour les indicateurs d’état tel que «\<nom\> est saisie »)  <br/> |
|Sessions de messagerie instantanée de groupe  <br/> |Le nombre moyen de messages envoyés lors d’une session de messagerie instantanée pour groupes uniquement est de 5 par utilisateur.  <br/> Nombre moyen de messages envoyés dans la portion messagerie instantanée d’une conférence A/V est 2 par utilisateur.  <br/> |
|Interrogation de présence  <br/> |Globalement, nous estimons l’interrogation de présence à 60 interrogations par utilisateur et par heure. La moyenne par utilisateur est estimée à :  <br/> • Une interrogation par jour de la présence des utilisateurs dans l’onglet organisation de l’utilisateur (mais non la liste Contacts). Nombre moyen de contacts non-dans l’onglet organisation de l’utilisateur est 15 utilisateurs. Deux opérations d’affichage de carte de visite par jour.  <br/> • Sondage d’une présence chaque fois que l’utilisateur clique sur un autre utilisateur pour démarrer une conversation, estimée à la fois par heure.  <br/> • Six utilisateur recherche par heure. Chaque fois qu’une recherche est effectuée, un sondage de traitement par lots est envoyé pour tout le monde dans la liste de résultats de recherche. Nous supposons que la taille moyenne des résultats de la recherche est de 20. Si les résultats de recherche restent à l’écran, l’interrogation du lot est actualisée toutes les 5 minutes ; Nous supposons qu’il y aura deux ces mises à jour par heure.  <br/> • Lorsque l’utilisateur ouvre ou affiche un aperçu d’un message électronique dans Outlook, un sondage de la présence d’utilisateurs dans le champ à : et CC : champs du message, estimé à cinq d’e-mails par heure et quatre utilisateurs par e-mail.  <br/> |
|Abonnements aux informations de présence  <br/> |Lorsqu’un utilisateur ajoute un autre en tant que contact, le premier utilisateur est abonnée à cinq catégories d’informations concernant le second utilisateur. Des mises à jour de ces catégories d’informations sont envoyées automatiquement au premier utilisateur. <br/> Pour chaque client, une seule demande d’abonnement par lot est envoyée pour obtenir le statut de présence d’une moyenne de 40 contacts, avec 40 boîtes de dialogue supplémentaires afin d’obtenir la présence des contacts fédérés.  <br/> La présence des membres d’un groupe de distribution développé se détermine par les abonnements de présence permanents, et non par l’interrogation, et est modelée sous forme d’une expansion par utilisateur toutes les 2 heures.  <br/> Abonnements courtes se produisent lorsqu’un utilisateur se connecte, il existe un abonnement par lots pour les contacts de tous les utilisateurs et puis l’utilisateur bientôt se déconnecte. Nous partons du principe que 6 abonnements courts se font par utilisateur et par heure, où chaque abonnement dure 10 minutes. <br/> |
|Publication de présence  <br/> |En moyenne, le statut de présence est publié 4 fois par utilisateur et par heure, avec un maximum de 6 fois.  <br/> |
|Taille du document de présence  <br/> |La taille moyenne d’un document de présence complet est estimée à 4 Ko, avec un maximum de 25 Ko.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour l’utilisation d’un carnet d’adresses.
  
**Modèle d’utilisateur adresse manuel Utilisation**

|**Mode de recherche de carnet d’adresses**|**Utilisation de**|
|:-----|:-----|
|Requête web du carnet d’adresses uniquement (toutes les requêtes sont effectuées par le service de requête web du carnet d’adresses)  <br/> |Quatre requêtes de préfixe quotidiennes par utilisateur.  <br/> 60 requêtes de recherche exacte quotidiennes par utilisateur. 40 % de ces requêtes sont traitées par lot, avec une moyenne de 20 contacts par requête. Les 60 % restants concernent un seul contact.  <br/> 25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.  <br/> Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.  <br/> |
|Mode mixte : utilisation du fichier de carnet d’adresses et des requêtes web. Il s’agit du mode par défaut.  <br/> |Deux types de requête uniquement sont transmis sur le réseau, à savoir les requêtes de photos et les requêtes de recherche dans toute l’entreprise.  <br/> 25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.  <br/> Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.  <br/> |
   
Le tableau ci-dessous décrit le modèle de conférence.
  
**Modèle de conférence**

|**Catégorie**|**Description**|
|:-----|:-----|
|Réunions planifiées/réunions immédiates  <br/> |60 % des réunions sont planifiées, 40 % ne le sont pas.  <br/> De toutes les réunions planifiées, nous partons du principe que 80 % correspondent à des conférences affectées et qui sont des occurrences de conférences périodiques. 10 % sont des réunions ouvertes uniques. 8 % correspondent à des réunions anonymes uniques et 2 % sont des réunions fermées uniques.  <br/> |
|Répartition des clients de conférence  <br/> |Pour les réunions planifiées :  <br/> • 65 % des utilisateurs de conférence utiliser Skype pour 2016 de l’entreprise.  <br/> • 5 % des utilisateurs de conférence utiliser Skype pour Business Web App.  <br/> • 30 % des utilisateurs de conférence utiliser des clients antérieurs, y compris Lync 2013 et Microsoft Lync 2010.  <br/> Pour les réunions non planifiées :  <br/> • 70 % des utilisateurs de conférence utiliser Skype pour les entreprises.  <br/> • 30 % des utilisateurs de conférence utiliser des clients antérieurs, y compris Lync 2013 et Microsoft Lync 2010.  <br/> |
|Simultanéité des réunions  <br/> |5 % des utilisateurs participeront à des conférences pendant les heures de travail. Ainsi, dans un pool de 80 000 utilisateurs, il peut arriver que 4 000 utilisateurs participent à tout moment à des conférences.  <br/> |
|Répartition des appels audio d’une réunion  <br/> |40 % d’appels audio VoIP et de conférences rendez-vous combinés, avec un ratio d’utilisateurs VoIP par rapport aux utilisateurs d’appels entrants égal à 3:1.  <br/> 35 % d’appels audio VoIP uniquement.  <br/> 15 % d’audioconférences rendez-vous uniquement.  <br/> 10 % sans appel audio (conférences de messagerie instantanée uniquement, avec une moyenne de cinq messages envoyés par utilisateur).  <br/> |
|Utilisation de différents médias dans le cadre des conférences  <br/> |75 % des conférences ont lieu sur Internet, notamment par des méthodes de collaboration audio ou autres.  <br/> Pour ces conférences, les autres méthodes de collaboration sont les suivantes :  <br/> **Remarque :** Ces nombres ajouter jusqu'à plus de 100 %, car une conférence peut avoir plusieurs méthodes de collaboration. <br/> • 50 % ajouter le partage d’application. Nous supposons qu’un utilisateur envoie des données avec un pic de 1,1 Mo par seconde.  <br/> • 50 % ajouter la messagerie instantanée (avec une moyenne de 2 messages par utilisateur).  <br/> • 20 % ajouter des données de collaboration, y compris PowerPoint ou tableau blanc dans ces, une moyenne de 2 fichiers PowerPoint présentées par la conférence, avec une taille moyenne de fichier de PowerPoint de 10 Mo (sans vidéo intégrée) ou 30 Mo (avec vidéo intégrée). Moyenne de 20 annotations par tableau blanc.  <br/> • 20 % ajouter de la vidéo. De ces utilisateurs, 70 % participent à des conférences activées pour la vidéo multiview, où chaque utilisateur reçoit 2 à 3 flux vidéo.  <br/> • 15 % ajouter des notes partagées.  <br/> |
|Répartition des participants aux réunions  <br/> |50 % d’utilisateurs internes authentifiés.  <br/> 25 % d’utilisateurs distants authentifiés.  <br/> 15 % d’utilisateurs anonymes.  <br/> 10 % d’utilisateurs fédérés.  <br/> |
|Répartition de la participation aux réunions  <br/> |Il est simulé que les utilisateurs se joignent à la réunion dans les 5 premières minutes.  <br/> |
   
Dans les pools de Front-End régulières, Skype pour Business Server a une taille maximale de réunion prises en charge de 250 utilisateurs. Chaque pool peut héberger 250 utilisateurs à la fois. Quand une réunion regroupant autant de participants a lieu, le pool peut également héberger d’autres conférences plus petites. Vous pouvez également prendre en charge les réunions rassemblant jusqu’à 1 000 utilisateurs en configurant un pool dédié pour les héberger. Pour plus d’informations, consultez [planification de réunions de grande taille dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).
  
Les conférences sont simulées comme suit :
  
- 85 % des conférences comptent quatre participants.
    
- 10 % des conférences comptent six participants.
    
- 5 % des conférences comptent 11 participants.
    
- Une conférence importante compte 250 utilisateurs.
    
Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les conférences auxquelles participent des utilisateurs d’appels entrants.
  
**Modèle utilisateur de conférence à distance**

|**Catégorie**|**Description**|
|:-----|:-----|
|Authentifié/anonyme  <br/> |70 % des appelants se joignent anonymement et sont invités à entrer un nom enregistré. 30 % participent en tant qu’utilisateurs authentifiés.  <br/> |
|Durée de conversation et attente musicale  <br/> |Durée moyenne de conversation sans attente musicale : 50 secondes.  <br/> 50 % des appelants entendent une musique d’attente pendant 5 minutes en moyenne.  <br/> |
|Numérotation DTMF  <br/> |15 % des conférences rendez-vous ont des responsables téléphoniques. 10 % des conférences mixtes qui incluent des utilisateurs d’appels entrants ont également des responsables téléphoniques.  <br/> 20 % des responsables téléphoniques utilisent deux commandes DTMF par conférence.  <br/> |
|Langues d’annonce  <br/> |Les simulations utilisent l’anglais comme langue pour les annonces.  <br/> |
   
Le tableau ci-dessous fournit des détails sur le modèle utilisateur pour les salles d’attente de conférence.
  
**Modèle d’utilisateur de salle de conférence**

|**Catégorie**|**Description**|
|:-----|:-----|
|Nombre d’utilisateurs dans la salle d’attente  <br/> |5 % des utilisateurs d’appels entrants et 25 % d’utilisateurs d’autres catégories passent par la salle d’attente.  <br/> |
|Autorisation à quitter la salle d’attente  <br/> |Pendant les simulations, le présentateur autorise tous les utilisateurs à participer avant l’expiration du délai du client.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour d’autres sessions P2P.
  
**Peer-to-Peer Sessions utilisateur modèle**

|**Catégorie**|**Description**|
|:-----|:-----|
|Partage d’application  <br/> |Chaque utilisateur participe à cinq sessions de partage d’application P2P par mois, avec une moyenne de 0,25 session par jour.  <br/> |
|Transfert de fichiers  <br/> |Chaque utilisateur participe à une session de transfert de fichiers P2P par mois (dans le cadre d’une session de messagerie instantanée), avec une moyenne de 0,05 session par jour. En moyenne, le volume transféré lors d’une session est de 1 Mo.  <br/> |
   
Le tableau ci-dessous décrit le modèle utilisateur pour les stratégies.
  
**Les stratégies utilisateur modèle**

|**Catégorie**|**Description**|
|:-----|:-----|
|Stratégies de conférence, de présence et d’archivage  <br/> |Nous partons du principe qu’il y a une stratégie globale, 10 stratégies de conférence, 4 stratégies d’archivage et 10 stratégies de présence.  <br/> |
|Stratégie vocale  <br/> |Nous supposons qu’il existe une stratégie globale et 2 stratégies de mots clés par site. 100 % des sites ont une stratégie de site et 30 % des utilisateurs sont gérés par une stratégie par utilisateur. Nous prenons pour hypothèse un plan de numérotation par site et deux itinéraires par site.  <br/> |
   
## <a name="busy-hour"></a>Heure de pointe

Pour les sessions P2P, la charge maximale est calculée à partir des « tentatives d’appels aux heures de pointe » (BHCA). Cette mesure utilisée dans le secteur de la téléphonie suppose que 50 % de tous les appels d’une journée seront passés en 20 % du temps. Elle est calculée à l’aide de la formule suivante :
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Lors d’un test de performance, l’heure de pointe a été simulée en exécutant des sessions VoIP et d’autres sessions P2P aux heures de pointe pendant au moins 1,6 heure par jour.
  
Le pic de charge des conférences suppose que 75 % de toutes les conférences d’une journée de huit heures ont lieu pendant quatre heures de pointe. Ces heures de pointe représentent 1,5 fois la charge de conférence moyenne.
  
## <a name="enterprise-voice-to-pstn-calls"></a>Voix Entreprise pour les appels RTPC

Les hypothèses suivantes s’appliquent aux appels de Voix Entreprise :
  
- 60 % des utilisateurs sont activés pour les Voix Entreprise et 60 % de ces utilisateurs sont activés pour RTPC appelant.
    
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
  

