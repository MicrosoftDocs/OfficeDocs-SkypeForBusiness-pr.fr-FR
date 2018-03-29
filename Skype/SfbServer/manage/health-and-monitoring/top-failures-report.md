---
title: Rapport des principales défaillances dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Résumé : En savoir plus sur le rapport des échecs supérieur dans Skype pour Business Server 2015.'
ms.openlocfilehash: 3eb536fdeaa606c16c78954401bc43e91dd520d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="top-failures-report-in-skype-for-business-server-2015"></a>Rapport des principales défaillances dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le rapport des échecs supérieur dans Skype pour Business Server 2015.
  
Le rapport des principales défaillances expose les défaillances les plus fréquentes et leur évolution dans le temps. Les défaillances sont basées sur une combinaison des deux métriques suivantes :
  
- **ID de diagnostic**. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP. Les ID de diagnostic fournissent des informations utiles pour résoudre les problèmes liés aux appels.
    
- **Code de réponse**. Codes de réponse sont utilisés dans les sessions de communication SIP pour répondre aux demandes SIP. Par exemple, supposons que Ken envoie la demande d’invitation à Pilar Ackerman (autrement dit, supposons que Ken Myer appelle Pilar Ackerman). Si Pilar répond, son téléphone envoie le code de réponse 200 (OK), informer les téléphone de Ken que Pilar a répondu. Le rapport des échecs haut inclut uniquement les codes de réponse qui ont été envoyés en réponse à un échec d’appel ; Skype pour Business Server n’assure pas le suivi du tous les codes de réponse émises au cours d’un appel.
    
Les informations sont signalées pour le nombre total de sessions où une défaillance s’est produite, ainsi que pour le nombre total d’utilisateurs affectés par la panne.
  
## <a name="accessing-the-top-failures-report"></a>Accès au rapport des principales défaillances

Le rapport des principales défaillances est accessible à partir de la page d’accueil Rapports de surveillance. La métrique de sessions déclaré vous redirigera vers le [Rapport d’échecs de Distribution dans Skype pour Business Server 2015](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Optimisation de l’utilisation du rapport des principales défaillances

Le rapport des principales défaillances est particulier : il vous permet de filtrer jusqu’à 5 ID de diagnostic à la fois. (En général vous pouvez seulement filtrer sur un élément - comme adresse SIP d’un utilisateur - à la fois.) Pour filtrer sur plusieurs codes de diagnostics, saisissez simplement chaque code dans la zone ID de Diagnostic, en séparant les numéros par des virgules. (Si vous le souhaitez, vous pouvez laisser un espace après chaque virgule.) Par exemple :
  
1011, 2412, 1033, 52116, 1008
  
Procédez ainsi pour afficher uniquement les appels défaillants qui correspondent à l’un de ces cinq ID de diagnostic.
  
Si vous pointez le curseur de la souris sur un code de réponse, vous voyez s’afficher une info-bulle qui vous indique la signification de ce code de réponse. Par exemple, si vous pointez sur le code de réponse 486, vous voyez s’afficher le message suivant :
  
Occupé ici.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données renvoyées sur la base d’éléments tels que le type d’activité (session P2P ou session de conférence) ou le code de réponse SIP qui accompagnait la session en échec. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport des principales défaillances.
  
**Filtres de rapport de pannes supérieur**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Type d’activité** <br/> | Type d’activité. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Égal à égal <br/>  Conférence <br/> |
|**Modalité** <br/> |À ce stade, la seule option disponible est **[Tous]**.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Catégorie** <br/> | Type de défaillance rencontrée. Sélectionnez l’une des options suivantes : <br/>  Échecs attendus et inattendus <br/>  Échec inattendu <br/>  Un « échec attendu » est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent. Un « échec inattendu » est un échec qui se produit dans un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu. <br/> |
|**Code de réponse** <br/> |Code de réponse SIP envoyé lors de l’échec de la conférence. Entrez le code de réponse entier. Par exemple :  <br/> 400  <br/> |
|**ID de diagnostic** <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.  <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport des principales défaillances.
  
**Métrique de rapport de pannes supérieur**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Classement** <br/> |Oui  <br/> |Classement relatif sur la base du nombre de sessions signalées.  <br/> |
|**Sessions signalées** <br/> |Oui  <br/> |Nombre total de sessions en échec sur la base de l’ID de diagnostic et du code de réponse SIP.  <br/> |
|**Utilisateurs affectés** <br/> |Oui  <br/> |Nombre total d’utilisateurs affectés par l’échec de la session.  <br/> |
|**Informations sur l’échec** <br/> |Non  <br/> |Informations détaillées sur l’échec, notamment ID de diagnostic, code de réponse SIP et description de la cause de l’échec de la session.  <br/> |
|**Tendance dans le passé** <br/> |Non  <br/> |Propose un graphique des échecs de session dans le temps.  <br/> |
   

