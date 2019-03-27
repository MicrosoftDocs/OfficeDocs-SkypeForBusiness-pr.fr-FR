---
title: Rapport de répartition dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 'Résumé : Découvrez le rapport de répartition dans Skype pour Business Server.'
ms.openlocfilehash: 6a8c5402555bc8334a9df36e2fff62ed2991bcff
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883251"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Rapport de répartition dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur le rapport de répartition dans Skype pour Business Server.
  
Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :
  
- Motifs de diagnostic principaux
    
- Modalités principales
    
- Pools principaux
    
- Sources principales
    
- Composants principaux
    
- Utilisateurs émetteurs principaux
    
- Utilisateurs destinataires principaux
    
- Agents utilisateurs émetteurs principaux
    
Vous pouvez utiliser ces catégories pour rechercher exactement le problème et, dans certains cas, déterminer la raison de ce problème. Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée. Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces sessions ont eu lieu dans le pool Dublin. C’est un bon point de départ pour rechercher et diagnostiquer les causes à l’origine de ces défaillances. Si vous cliquez sur le pool Dublin sous la catégorie **Pools principaux**, vous y trouverez un rapport de répartition des défaillances spécifique à ce pool. Vous pouvez ensuite commencer à analyser les raisons qui ont entraîné autant de difficultés dans le pool.
  
## <a name="viewing-the-failure-distribution-report"></a>Affichage du rapport de répartition des défaillances

Vous pouvez accéder au rapport de répartition des défaillances à partir de n’importe lequel des rapports suivants en cliquant sur la mesure **Nombre d’échecs attendus** ou **Nombre d’échecs inattendus** :
  
- [Rapport des principales défaillances dans Skype pour Business Server](top-failures-report.md)
    
- [Rapport de Diagnostic conférence dans Skype pour Business Server](conference-diagnostic-report.md)
    
- [Rapport de Diagnostic activités d’égal à égal dans Skype pour Business Server](peer-to-peer-activity-diagnostic-report.md)
    
Dans le rapport de répartition, vous pouvez cliquer sur une des mesures suivantes pour afficher le [Rapport de liste des défaillances dans Skype pour Business Server](failure-list-report.md):
  
- Motifs de diagnostic principaux (sessions)
    
- Modalités principales (sessions)
    
- Pools principaux (sessions)
    
- Sources principales (sessions)
    
- Composants principaux (sessions)
    
- Utilisateurs émetteurs principaux (sessions)
    
- Utilisateurs destinataires principaux (sessions)
    
- Agents utilisateurs émetteurs principaux (sessions)
    
## <a name="using-the-failure-distribution-report"></a>Utilisation du rapport de répartition des défaillances

Selon la taille de votre moniteur et sa résolution d’écran, il est possible que certaines des données indiquées dans le rapport de répartition des défaillances soient tronquées à l’écran. Cela se vérifie en particulier pour les mesures comme les agents utilisateurs qui ont des libellés très longs. Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut ne s’afficher que partiellement à l’écran : 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...
  
Fort heureusement, vous pouvez voir le libellé en entier en maintenant votre souris au-dessus de la valeur tronquée.
  
L’ID de diagnostic est une mesure intéressante sur laquelle vous pouvez filtrer dans le rapport de répartition des défaillances. Si le même ID de diagnostic s’affiche dans d’autres rapports, vous pouvez filtrer sur cet ID dans le rapport de répartition des défaillances et obtenir des informations très détaillées sur l’emplacement exact où a été signalé cet ID pendant une session ayant échoué et sa fréquence.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de répartition des défaillances vous permet de filtrer sur des critères tels que le type d’activité (session entre homologues ou session de conférence) ou à l’aide de l’ID de diagnostic qui a accompagné chaque session ayant échoué.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.
  
**Filtres du rapport de répartition des défaillances**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Type d’activité** <br/> | Type d’activité sur laquelle filtrer. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Égal à égal <br/>  Conférence <br/> |
|**Catégorie de session** <br/> | Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Opération réussie <br/>  Échec attendu <br/>  Échec inattendu <br/>  Un « échec attendu » est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent. Un « échec inattendu » est un échec qui se produit dans un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu. <br/> |
|**ID de diagnostic** <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Mesures pour les motifs de diagnostic principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.
  
**Mesures pour les motifs de diagnostic principaux**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué sur la base des ID de diagnostic. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs.  <br/> |
|**Motifs de diagnostic principaux** <br/> |Non  <br/> |ID de diagnostic généré dans une session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué où l’ID de diagnostic spécifié a été généré.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Mesures pour les modalités principales

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.
  
**Mesures pour les modalités principales**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué sur la base du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers entre homologues).  <br/> |
|**Modalités principales** <br/> |Non  <br/> |Type de session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué impliquant la modalité spécifiée.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Mesures pour les pools principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.
  
**Mesures pour les pools principaux**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué basé sur le pool de serveurs d’inscriptions ou serveur Edge où la session a eu lieu.  <br/> |
|**Pools principaux** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par pool de serveurs d’inscriptions ou serveur Edge.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Mesures pour les sources principales

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.
  
**Mesures pour les sources principales**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué par ordinateur.  <br/> |
|**Sources principales** <br/> |Non  <br/> |Nom de l’ordinateur impliqué dans la session ayant échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par ordinateur.  <br/> |
   
## <a name="metrics-for-top-components"></a>Mesures pour les composants principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des composants ayant rencontré le plus d’échecs.
  
**Mesures pour les composants principaux**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué selon le composant (par exemple, ExumRouting, GroupChat ou MediationServer).  <br/> |
|**Composants principaux** <br/> |Non  <br/> |Nom du composant impliqué dans la session ayant échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par composant.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Mesures pour les utilisateurs émetteurs principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs en essayant d’appeler quelqu’un d’autre (dénommés utilisateurs « De »).
  
**Mesures pour les utilisateurs émetteurs principaux**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à se joindre à la session.  <br/> |
|**Utilisateurs émetteurs principaux** <br/> |Non  <br/> |Adresse SIP de l’utilisateur invité à se joindre à la session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par utilisateur.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Mesures pour les utilisateurs destinataires principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs après avoir été appelés par quelqu’un d’autre (dénommés utilisateurs « À »).
  
|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.  <br/> |
|**Utilisateurs destinataires principaux** <br/> |Non  <br/> |Adresse SIP de l’utilisateur ayant initié la session.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par utilisateur.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Mesures pour les principaux agents d’utilisateur

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.
  
**Mesures pour les principaux agents d’utilisateur**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Non  <br/> |Classement relatif des sessions ayant échoué sur la base de l’agent d’utilisateur (logiciel) impliqué dans la session. Par exemple : RTCC/4.0.0.0 Inbound Routing/4.0.0.0.  <br/> |
|**Principaux agents d’utilisateurs** <br/> |Non  <br/> |Nom de l’agent d’utilisateur impliqué dans la session ayant échoué.  <br/> |
|**Sessions** <br/> |Non  <br/> |Nombre total de sessions ayant échoué par agent.  <br/> |
   

