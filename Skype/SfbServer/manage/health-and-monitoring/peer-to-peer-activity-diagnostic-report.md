---
title: Rapport de diagnostic d’activité d’égal à égal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Résumé: en savoir plus sur le rapport de diagnostic des activités d’égal à égal dans Skype entreprise Server.'
ms.openlocfilehash: 37773edc939787eff034d8dd6d001e3529c0db91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279898"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Rapport de diagnostic d’activité d’égal à égal dans Skype entreprise Server
 
**Résumé:** En savoir plus sur le rapport de diagnostics d’activité d’égal à égal dans Skype entreprise Server.
  
Le rapport de diagnostic des activités P2P fournit des informations sur la réussite ou l’échec des sessions de communication P2P. Notez que Skype entreprise Server distingue différentes sortes d’échecs:
  
- **échec attendu**. Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel. Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec. En revanche, il s’agissait d’un échec attendu: Skype entreprise Server ne vous attend pas à répondre au téléphone si vous n’êtes pas disponible pour répondre au téléphone. De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.
    
- **Échec inattendu**. Un échec inattendu constitue exactement ce que son nom indique : une erreur à laquelle on ne s’attend pas, compte tenu des circonstances. Par exemple, supposons que vous appelez une personne et qu’elle soit disponible pour répondre à un appel. en revanche, lorsque Skype entreprise Server tente d’acheminer votre appel vers la messagerie vocale, l’appel échoue car la connectivité à la messagerie unifiée Exchange a été perdue. Il s’agit d’une erreur inattendue : car vous vous attendiez à ce que les appels soient toujours dirigés vers la messagerie vocale. En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.
    
Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :
  
|**Réussites**|**Échecs attendus**|**Échecs inattendus**|**Nombre total de sessions**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |Seiz  <br/> |2521  <br/> |
   
Si vous additionnez 2 024 + 469 + 16, vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs. Ce peut arriver parfois quand un produit tiers introduit un nouveau code de diagnostic inhabituel dans Skype entreprise Server. Lorsque cela arrive, les appels effectués à l’aide de ce produit et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accès au rapport de diagnostic des activités P2P

Le rapport de diagnostic des activités P2P est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au [rapport de distribution des échecs dans Skype entreprise Server](failure-distribution-report.md) en cliquant sur l’une des mesures suivantes:
  
- Nombre d’échecs inattendus
    
- Nombre d’échecs attendus
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Utilisation optimale du rapport de diagnostic des activités P2P

Il existe plusieurs manières de filtrer le rapport de diagnostic des activités P2P mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic des activités P2P vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités P2P.
  
**Filtres du rapport de diagnostic des activités P2P**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Modalité** <br/> | Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Messagerie instantanée <br/>  Transfert de fichiers <br/>  Partage d’application <br/>  Audio <br/>  Vidéo <br/> |
   
## <a name="metrics-per-modality"></a>Mesures (par modalité)

Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de diagnostic des activités P2P pour chaque modalité.
  
**Mesures (par modalité)**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre de réussites** <br/> |Non  <br/> |Nombre total des sessions P2P réussies.  <br/> |
|**Pourcentage de réussite** <br/> |Non  <br/> |Pourcentage des sessions P2P qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.  <br/> |
|**Nombre d’échecs attendus** <br/> |Non  <br/> |Nombre total de sessions lors desquelles un « échec attendu » s’est produit.  <br/> Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.  <br/> |
|**Pourcentage d’échec attendu** <br/> |Non  <br/> |Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Nombre d’échecs inattendus** <br/> |Non  <br/> |Nombre total de sessions où un « échec inattendu » s’est produit.  <br/> Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.  <br/> |
|**Pourcentage d’échec inattendu** <br/> |Non  <br/> |Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.  <br/> |
   

