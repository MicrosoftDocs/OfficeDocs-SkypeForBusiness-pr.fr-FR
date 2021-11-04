---
title: Rapport d’enregistrement de l’utilisateur Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Résumé : Découvrez le rapport d’enregistrement de l’utilisateur Skype Entreprise Server.'
ms.openlocfilehash: e137fae97f9b39f45dd619d2ed90a4180897c713
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778324"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Rapport d’enregistrement de l’utilisateur Skype Entreprise Server
 
**Résumé :** Découvrez le rapport d’enregistrement de l’utilisateur dans Skype Entreprise Server.
  
Le rapport d’enregistrement de l’utilisateur fournit une vue d’ensemble de l’activité d’ouverture de session utilisateur, notamment des informations sur le nombre d’utilisateurs qui se sont connectés à Skype Entreprise Server pendant une période spécifiée (toutes les heures, tous les jours, toutes les semaines, tous les mois). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas qui a ouvert une session. Les rapports de surveillance ne fournissent pas d’informations sur les utilisateurs spécifiques qui utilisent Skype Entreprise Server (et ceux qui ne le sont pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.
  
Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Les connexions externes représentent les utilisateurs qui se sont connectés à l’extérieur du pare-feu via un serveur Edge (par exemple, un utilisateur qui s’est connecté à partir d’un café Internet compte comme une connexion externe). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.
  
En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs actifs qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée, qui a participé à une réunion Skype Entreprise Server, qui a effectué ou reçu un appel téléphonique, ou qui a utilisé des Skype Entreprise Server pendant cette période. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.
  
## <a name="accessing-the-user-registration-report"></a>Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilisation optimale du rapport d’enregistrement de l’utilisateur

Une fois que vous avez déployé Skype Entreprise Server une question fréquemment posée est la suivante : Comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie ? Bien qu’il soit quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour déterminer si les utilisateurs utilisent Skype Entreprise Server, vous devez faire deux choses. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique le nombre de personnes distinctes qui se sont connectées à Skype Entreprise Server.
  
Par comparaison, la mesure Nombre total d’connexions indique le nombre total de fois où quelqu’un s’est connecté à Skype Entreprise Server. Par exemple, supposons que Ken Myer s’est connecté Skype Entreprise Server cinq fois en une seule journée. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, un utilisateur peut se connecter à l’aide de son ordinateur de bureau, de son ordinateur portable et d’un téléphone IP qui se connecte automatiquement à Skype Entreprise Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.
  
Pour mieux expliquer la différence entre le nombre total d’ouvertures de session et les utilisateurs uniques par ouverture de session, examinez les ouvertures de session pour une période donnée dans le tableau suivant.
  
|**Utilisateur**|**Date/heure d’ouverture de session**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 8:45  <br/> |
|Ken Myer  <br/> |7/7/2015 8:46  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:17  <br/> |
|Ken Myer  <br/> |7/7/2015 09:22  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 09:31  <br/> |
   
Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Ceci illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.
  
En plus de connaître le nombre d’connexions uniques, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Skype Entreprise Server. Cette valeur peut être récupérée en ouvrant l’Skype Entreprise Server Management Shell et en exécutant la commande Windows PowerShell suivante :
  
```PowerShell
(Get-CsUser).Count
```

Si la commande précédente renvoie une valeur de 1 236 et que la mesure Utilisateurs uniques par ouverture de session renvoie une valeur moyenne de 667, cela suggère qu’un peu plus de la moitié de vos utilisateurs activent la Skype Entreprise se connectent réellement au système chaque jour (autrement dit, 667 divisés par 1 236, soit environ 54 %).
  
> [!CAUTION]
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Cela signifie que près de 1 000 utilisateurs se sont connectés à Skype Entreprise Server, ce qui signifie que près de 80 % de vos utilisateurs ont ouvert une session. 
  
Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La mesure Utilisateurs actifs uniques vous indique le nombre d’utilisateurs uniques qui ont réellement utilisé des Skype Entreprise Server : ils ont effectué un appel téléphonique, rejoint une réunion Skype Entreprise Server ou ont participé à une session de messagerie instantanée. Il s’agit d’informations utiles, Skype Entreprise Server peuvent être configurées pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows. Pour cette raison, vous pouvez avoir un grand nombre d’utilisateurs qui se connectent automatiquement à Skype Entreprise lorsqu’ils se connectent à Windows chaque jour, mais n’utilisent jamais réellement Skype Entreprise Server pendant cette période.
  
La mesure Utilisateurs actifs uniques fournit également des données plus significatives dans une organisation où les utilisateurs ne se déconnectent généralement Windows à la fin de la journée. Au lieu de cela, ils verrouillent simplement leurs ordinateurs et laissent Windows et Skype Entreprise en cours d’exécution. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. Toutefois, les utilisateurs actifs uniques vous indiquent si les utilisateurs utilisent activement Skype Entreprise ou un autre Skype Entreprise Server client.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’enregistrement de l’utilisateur vous permet d’afficher les données de tous vos serveurs d’inscriptions et serveurs Edge ou d’afficher les données d’un pool individuel. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les inscriptions sont regroupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’enregistrement de l’utilisateur.
  
**Filtres du rapport d’enregistrement de l’utilisateur**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur **[Tous]** pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données. <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’enregistrement de l’utilisateur. 
  
**Mesures du rapport d’enregistrement de l’utilisateur**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Tous les jours** <br/> **Toutes les semaines** <br/> **Mensuelle** <br/> |Non  <br/> |Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, vous voyez une répartition horaire de l’activité d’inscription de l’utilisateur pour cette date.  <br/> |
|**Nombre total d’ouvertures de sessions** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions réussies.  <br/> |
|**Ouvertures de sessions internes** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions dans le réseau interne.  <br/> |
|**Ouvertures de sessions externes** <br/> |Non  <br/> |Nombre total d’ouvertures de sessions de l’extérieur du réseau interne, à l’aide du serveur Edge.  <br/> |
|**Utilisateurs uniques par ouverture de session** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont ouvert au moins une session. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.  <br/> |
|**Utilisateurs actifs uniques** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont été impliqués dans une session d’égal à égal ou de conférence. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.  <br/> |
   

