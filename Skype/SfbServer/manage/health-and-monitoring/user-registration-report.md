---
title: Rapport sur l’inscription des utilisateurs dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Résumé: en savoir plus sur le rapport sur l’inscription des utilisateurs dans Skype entreprise Server.'
ms.openlocfilehash: efdb701a61f527e3dd56c1f1e0662f3f1b7f0f8b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279668"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Rapport sur l’inscription des utilisateurs dans Skype entreprise Server
 
**Résumé:** En savoir plus sur le rapport sur l’inscription des utilisateurs dans Skype entreprise Server.
  
Le rapport sur l’inscription des utilisateurs donne un aperçu de l’activité de connexion des utilisateurs, en particulier des informations sur le nombre d’utilisateurs connectés à Skype entreprise Server pendant une période spécifiée (horaire, quotidienne, hebdomadaire, mensuel). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas qui a ouvert une session. Les rapports d’analyse ne fournissent pas d’informations sur les utilisateurs spécifiques utilisant Skype entreprise Server (et ceux qui ne le sont pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.
  
Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Les ouvertures de session externes représentent les utilisateurs qui se sont connectés depuis l’extérieur du pare-feu par le biais d’un serveur Edge (par exemple, un utilisateur qui s’est connecté à partir d’un cafés Internet compte comme une connexion externe). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.
  
En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs actifs qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée, a participé à une réunion Skype entreprise Server, a émis ou reçu un appel téléphonique ou a utilisé Skype entreprise Server pendant la période écoulée. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.
  
## <a name="accessing-the-user-registration-report"></a>Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilisation optimale du rapport d’enregistrement de l’utilisateur

Une fois que vous avez déployé Skype entreprise Server, l’une des questions fréquemment posées est la suivante: Comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie? Même s’il est quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour déterminer si des utilisateurs utilisent ou non Skype entreprise Server, vous devez effectuer deux opérations. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique le nombre d’utilisateurs distincts connectés à Skype entreprise Server.
  
Par comparaison, la métrique total des ouvertures de session indique le nombre total de fois où tout le monde s’est connecté à Skype entreprise Server. Par exemple, supposons que Ken Myer s’est connecté à Skype entreprise Server cinq fois par jour. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, l’utilisateur peut se connecter à l’aide d’un ordinateur de bureau, d’un ordinateur portable ou d’un téléphone IP qui se connecte automatiquement à Skype entreprise Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.
  
Pour mieux expliquer la différence entre le nombre total d’ouvertures de session et les utilisateurs uniques par ouverture de session, examinez les ouvertures de session pour une période donnée dans le tableau suivant.
  
|**User**|**Date/heure d’ouverture de session**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 08:45  <br/> |
|Ken Myer  <br/> |07/07/2015 08:46  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 09:17  <br/> |
|Ken Myer  <br/> |07/07/2015 09:22  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 09:31  <br/> |
   
Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Cela illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.
  
En plus de connaître le nombre d’ouvertures de session uniques, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Skype entreprise Server. Cette valeur peut être récupérée en ouvrant Skype entreprise Server Management Shell et en exécutant la commande Windows PowerShell suivante:
  
```
(Get-CsUser).Count
```

Si la commande précédente renvoie une valeur de 1 236 et que la métrique des utilisateurs de connexion unique renvoie une valeur moyenne de 667, qui vous suggère qu’un petit nombre de vos utilisateurs est en train de se connecter au système quotidiennement (c’est 667 divisée par 1 236, soit environ 54%).
  
> [!CAUTION]
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Cela signifie que vous avez réellement reçu des utilisateurs de 1 000 connectés à Skype entreprise Server, ce qui signifie que plus près de 80% de vos utilisateurs ont été connectés. 
  
Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La métrique utilisateurs actifs uniques indique le nombre d’utilisateurs uniques qui ont réellement utilisé Skype entreprise Server: ils ont effectué un appel téléphonique, ils ont rejoint une réunion Skype entreprise Server ou ont participé à une session de messagerie instantanée. Il s’agit d’informations utiles, car Skype entreprise Server peut être configuré pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows. Pour cette raison, il est possible que vous disposiez d’un grand nombre d’utilisateurs qui se connectent automatiquement à Skype entreprise lorsqu’ils se connectent à Windows tous les jours, mais qu’ils n’utilisent jamais réellement Skype entreprise Server pendant ce laps de temps.
  
La métrique unique des utilisateurs actifs fournit également des données plus significatives au sein d’une organisation dans laquelle les utilisateurs ne ferment pas de fenêtre à la fin de la journée. Au lieu de cela, ils verrouillent simplement leur ordinateur et laissent fonctionner Windows et Skype entreprise. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. Toutefois, les utilisateurs actifs uniques vous indiquent si les utilisateurs utilisent activement Skype entreprise ou un autre client Skype entreprise Server.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport sur l’inscription des utilisateurs vous permet d’afficher les données de l’ensemble de votre pool d’inscriptions et de vos serveurs Edge, ou d’afficher les données d’un pool individuel. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’enregistrement de l’utilisateur.
  
**Filtres du rapport d’enregistrement de l’utilisateur**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données. <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’enregistrement de l’utilisateur. 
  
**Mesures du rapport d’enregistrement de l’utilisateur**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Jour** <br/> **Toutes les semaines** <br/> **Mois** <br/> |Non  <br/> |Indique l’intervalle de temps sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, vous disposez de l’affichage heure par heure de l’activité d’inscription de l’utilisateur à cette date.  <br/> |
|**Nombre total d’ouvertures de sessions** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions réussies.  <br/> |
|**Ouvertures de sessions internes** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions dans le réseau interne.  <br/> |
|**Ouvertures de sessions externes** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions de l’extérieur du réseau interne, à l’aide du serveur Edge.  <br/> |
|**Utilisateurs uniques par ouverture de session** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont ouvert au moins une session. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.  <br/> |
|**Utilisateurs actifs uniques** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont été impliqués dans une session P2P ou de conférence. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.  <br/> |
   

