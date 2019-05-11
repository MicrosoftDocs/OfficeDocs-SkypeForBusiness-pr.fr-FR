---
title: Rapport d’enregistrement utilisateur dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Résumé : Découvrez l’état de l’enregistrement d’utilisateur dans Skype pour Business Server.'
ms.openlocfilehash: d9bc8e458e56e4a313866e9bca99eef2e4c104cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897974"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Rapport d’enregistrement utilisateur dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur l’état de l’enregistrement d’utilisateur dans Skype pour Business Server.
  
Le rapport d’enregistrement utilisateur fournit une vue d’ensemble de l’activité d’ouverture de session utilisateur, les plus particulièrement les informations sur le nombre d’utilisateurs ayant ouvert une session sur Skype pour Business Server durant une période spécifiée (toutes les heures, tous les jours, toutes les semaines, tous les mois). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas qui a ouvert une session. Rapports de surveillance ne fournissent pas d’informations sur les utilisateurs spécifiques qui sont à l’aide de Skype pour Business Server (et ceux qui n’est pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.
  
Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Ouvertures de sessions externes représentent des utilisateurs connectés à partir de l’extérieur du pare-feu via un serveur Edge (par exemple, un utilisateur connecté à partir du compte d’ouverture de session externe pour un café Internet). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.
  
En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs actifs qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une conversation instantanée, de messagerie instantanée a participé à un Skype pour Business Server réunion, apportées a reçu un appel téléphonique ou sinon utilisé Skype pour Business Server pendant ce laps de temps. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.
  
## <a name="accessing-the-user-registration-report"></a>Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilisation optimale du rapport d’enregistrement de l’utilisateur

Une fois que vous avez déployé Skype pour Business Server une fréquentes question s’agit-il : comment savoir si les utilisateurs sont réellement à l’aide de cette nouvelle technologie ? Même s’il est quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour déterminer si les utilisateurs utilisent Skype pour Business Server, vous devez effectuer deux opérations. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique combien de personnes distincts ouvert une session sur Skype pour Business Server.
  
Comparativement, la mesure nombre Total de connexions indique combien de fois total tout le monde ouvert une session sur Skype pour Business Server. Par exemple, supposons que Ken Myer ouvert une session sur Skype pour Business Server cinq à différents moments dans une journée. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, un utilisateur peut se connecter à l’aide de son ordinateur de bureau, son ordinateur portable, et elle peut avoir un téléphone IP qui se connecte automatiquement à Skype pour Business Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.
  
Pour mieux expliquer la différence entre le nombre total d’ouvertures de session et les utilisateurs uniques par ouverture de session, examinez les ouvertures de session pour une période donnée dans le tableau suivant.
  
|**User**|**Date/heure d’ouverture de session**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 08:45  <br/> |
|Ken Myer  <br/> |07/07/2015 08:46  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 09:17  <br/> |
|Ken Myer  <br/> |07/07/2015 09:22  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 09:31  <br/> |
   
Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Cela illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.
  
En plus de connaître le nombre d’ouvertures de session unique, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Skype pour Business Server. Cette valeur peut être récupérée en ouvrant le Skype pour Business Server Management Shell et en exécutant la commande Windows PowerShell suivante :
  
```
(Get-CsUser).Count
```

Si la commande précédente renvoie la valeur 1,236 et de mesure des utilisateurs d’ouverture de session Unique renvoie une valeur moyenne de 667, qui indique qu’un peu plus la moitié de vos utilisateurs activer pour Skype pour les entreprises sont réellement se connecter au système chaque jour (qui est 667 divisé par 1,236, qui est d’environ 54 %).
  
> [!CAUTION]
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Que signifie que vous avez réellement près de 1 000 utilisateurs connectés à Skype pour Business Server, ce qui signifie que rapprocher à 80 % de vos utilisateurs ont ouvert une session. 
  
Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La mesure utilisateurs actifs uniques indique le nombre d’utilisateurs unique utilisés réellement Skype pour Business Server : ils apportées à un appel téléphonique, ils joint un Skype pour Business Server réunion ou qu’ils ont participé dans une conversation par messagerie instantanée. Il s’agit des informations utiles, étant donné que Skype pour Business Server peut être configuré pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows. Par conséquent, vous devrez peut-être un grand nombre d’utilisateurs de se connecter automatiquement à Skype pour les entreprises lorsqu’elles se connectent à Windows chaque jour, mais jamais réellement utilisent Skype pour Business Server pendant la période.
  
La mesure d’utilisateurs actifs Unique fournit également des données plus explicites dans une organisation où les utilisateurs généralement ne se connectent pas désactiver Windows à la fin de la journée. Elles simplement verrouillent leur ordinateur et laissez Windows et Skype pour les entreprises en cours d’exécution. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. Toutefois, des utilisateurs actifs Unique vous indique si les utilisateurs utilisent activement Skype pour un autre Skype pour client Business Server ou de l’entreprise.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’enregistrement utilisateur permet de vous permet d’afficher des données pour votre pool de serveurs d’inscriptions et les serveurs de périphérie ou pour afficher les données pour un pool spécifique. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.
  
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
   

