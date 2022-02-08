---
title: Rapport de répartition des défaillances Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 'Résumé : Découvrez le rapport de répartition des défaillances dans Skype Entreprise Server.'
ms.openlocfilehash: 1cea85cb385ef7902dc896d468fea5ddfa71cc9d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384272"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Rapport de répartition des défaillances Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de répartition des défaillances dans Skype Entreprise Server.
  
Le rapport de répartition des défaillances classe les sessions qui ont échoué dans les catégories suivantes :
  
- Principales raisons de diagnostic
    
- Modalités principales
    
- Pools principaux
    
- Sources principales
    
- Principaux composants
    
- Utilisateurs les plus à l’avant
    
- Utilisateurs les plus à l’avant
    
- Agents utilisateurs de niveau supérieur
    
Vous pouvez utiliser ces catégories pour déterminer exactement où un problème se produit et, dans certains cas, pourquoi le problème se produit. Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo en échec au cours d’une journée donnée. Si vous regardez le rapport de répartition des défaillances, il peut montrer que 237 de ces sessions ont échoué dans votre pool de Dublin. Cela vous donne un bon point de départ pour suivre et diagnostiquer les causes de ces échecs. Si vous cliquez sur le pool de Dublin sous la catégorie **Pools** principaux, vous verrez un rapport de répartition des défaillances pour ce pool. Vous pouvez ensuite commencer à analyser la raison pour laquelle le pool de Dublin rencontre autant de difficultés.
  
## <a name="viewing-the-failure-distribution-report"></a>Affichage du rapport de répartition des défaillances

Vous pouvez accéder au rapport de répartition des défaillances à partir de l’un des rapports suivants en cliquant sur le **volume** d’échec attendu ou sur la mesure Du **volume** d’échec inattendu :
  
- [Rapport des principales défaillances dans Skype Entreprise Server](top-failures-report.md)
    
- [Rapport de diagnostic de conférence en Skype Entreprise Server](conference-diagnostic-report.md)
    
- [Rapport de diagnostic des activités D’égal à égal dans Skype Entreprise Server](peer-to-peer-activity-diagnostic-report.md)
    
Dans le rapport de répartition des défaillances, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le rapport des listes d’échecs [Skype Entreprise Server](failure-list-report.md) :
  
- Motifs de diagnostic principaux (sessions)
    
- Modalités principales (sessions)
    
- Pools principaux (sessions)
    
- Sources principales (sessions)
    
- Composants principaux (sessions)
    
- Utilisateurs émetteurs principaux (sessions)
    
- Utilisateurs destinataires principaux (sessions)
    
- Agents utilisateurs émetteurs principaux (sessions)
    
## <a name="using-the-failure-distribution-report"></a>Utilisation du rapport de répartition des défaillances

Selon la taille et la résolution de l’écran de votre moniteur, il est possible que certaines données affichées dans le rapport de répartition des défaillances soient tronquées lorsque vous les visualisez à l’écran. Cela est particulièrement vrai pour les mesures telles que les agents utilisateur, qui peuvent avoir des étiquettes très longues. Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut apparaître partiellement à l’écran : 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...
  
Heureusement, vous pouvez voir l’étiquette entière simplement en maintenant la souris au-dessus de la valeur tronquée.
  
L’ID de diagnostic est une mesure intéressante que vous pouvez filtrer à l’aide du rapport de répartition des défaillances. Si le même ID de diagnostic s’insérez dans d’autres rapports, vous pouvez filtrer sur cet ID dans le rapport de répartition des défaillances et obtenir une analyse très détaillée de l’endroit exact où, et à quelle fréquence, cet ID a été signalé au cours d’une session qui a échoué.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de répartition des problèmes vous permet de filtrer sur des éléments tels que le type d’activité (session d’égal à égal ou session de conférence) ou l’ID de diagnostic qui a accompagné chaque session qui a échoué.
  
Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.
  
**Filtres du rapport de répartition des défaillances**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.<br/> |
|**Type d’activité** <br/> | Type d’activité à filtrer. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Pair à pair <br/>  Programme <br/> |
|**Catégorie de session** <br/> | Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Opération réussie <br/>  Échec attendu <br/>  Échec inattendu <br/>  Un « échec attendu » est un échec prévisible. Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue. Un « échec inattendu » est un échec qui se produit dans un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu. <br/> |
|**ID de diagnostic** <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Mesures pour les principales raisons de diagnostic

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction de l’ID de diagnostic le plus fréquemment signalé.
  
**Mesures pour les principales raisons de diagnostic**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions qui ont échoué en fonction des ID de diagnostic. L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles pour la résolution des erreurs.  <br/> |
|**Principales raisons de diagnostic** <br/> |Non  <br/> |ID de diagnostic généré dans une session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué lorsque l’ID de diagnostic spécifié a été généré.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Mesures des modalités principales

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des modalités de session qui ont connu le plus d’échecs.
  
**Mesures des modalités principales**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif basé sur l’échec de la session en fonction du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers d’égal à égal).  <br/> |
|**Modalités principales** <br/> |Non  <br/> |Type de session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué impliquant la modalité spécifiée.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Mesures pour les pools principaux

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des pools qui ont connu le plus d’échecs.
  
**Mesures pour les pools principaux**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions qui ont échoué en fonction du pool de serveurs d’inscriptions ou du serveur Edge où la session a été menée.  <br/> |
|**Pools principaux** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions en échec par pool de serveurs d’inscriptions ou serveur Edge.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Mesures pour les sources principales

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des ordinateurs qui ont connu le plus d’échecs.
  
**Mesures pour les sources principales**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Le classement relatif des sessions a échoué par ordinateur.  <br/> |
|**Sources principales** <br/> |Non  <br/> |Nom de l’ordinateur impliqué dans la session qui a échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué par ordinateur.  <br/> |
   
## <a name="metrics-for-top-components"></a>Mesures des principaux composants

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des composants qui ont connu le plus d’échecs.
  
**Mesures des principaux composants**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions qui ont échoué en fonction du composant (par exemple, ExumRouting, GroupChat ou MediationServer).  <br/> |
|**Principaux composants** <br/> |Non  <br/> |Nom du composant impliqué dans la session qui a échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué par composant.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Mesures pour les utilisateurs de premier niveau

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des utilisateurs qui ont connu le plus d’échecs lorsqu’ils ont tenté d’appeler quelqu’un d’autre (appelé utilisateurs « De »).
  
**Mesures pour les utilisateurs de premier niveau**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué en fonction de l’utilisateur qui a été invité à rejoindre la session.  <br/> |
|**Utilisateurs les plus à l’avant** <br/> |Non  <br/> |Adresse SIP de l’utilisateur invité à rejoindre la session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué par utilisateur.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Mesures pour les utilisateurs les plus à l’échelle

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction des utilisateurs qui ont connu le plus d’échecs lorsqu’un autre utilisateur a tenté de les appeler (appelés utilisateurs « À »).
  
|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué en fonction de l’utilisateur qui a initié la session.  <br/> |
|**Utilisateurs les plus à l’avant** <br/> |Non  <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué par utilisateur.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Mesures pour les principaux agents utilisateurs

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances en fonction du logiciel de point de terminaison qui a connu le plus d’échecs.
  
**Mesures pour les principaux agents utilisateurs**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Rank** <br/> |Non  <br/> |Classement relatif des sessions qui ont échoué en fonction de l’agent utilisateur (logiciel) impliqué dans la session. Par exemple : RTCC/4.0.0.0 Routage entrant/4.0.0.0.  <br/> |
|**Principaux agents utilisateurs** <br/> |Non  <br/> |Nom de l’agent utilisateur impliqué dans la session qui a échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions qui ont échoué par agent utilisateur.  <br/> |
   

