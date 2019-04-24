---
title: Rapport d’utilisation de Response Group dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3248b320-a552-400a-8485-6891af4eb0f3
description: 'Résumé : Découvrez l’application Response Group dans Skype pour Business Server.'
ms.openlocfilehash: c0126a483b97a1ede28e6fea450668a6921f4ffc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197883"
---
# <a name="response-group-usage-report-in-skype-for-business-server"></a>Rapport d’utilisation de Response Group dans Skype pour Business Server

**Résumé :** Découvrez l’application Response Group dans Skype pour Business Server.

L’application Response Group offre un moyen de Skype pour Business Server répondre et acheminer les appels téléphoniques basé sur le numéro qui a été composé et, le cas échéant, les réponses de l’appelant à une série de questions. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone pour votre support technique, Skype pour Business Server peut acheminer automatiquement appel au premier agent de bureau d’aide disponibles. Vous pouvez également Skype pour Business Server peut demander une série de questions (« appuyez sur 1 si vous rencontrez des problèmes de matériel. Appuyez sur 2 pour des problèmes logiciels. Appuyez sur 3 Si vous rencontrez des problèmes réseau. »), puis d’acheminer l’appel vers l’agent d’assistance aide plus approprié en fonction de la réponse à ces questions.

Le rapport d’utilisation de Response Group donne une vision détaillée du nombre d’appels téléphoniques reçus par tous vos flux de travail Response Group, puis répartit ces appels en catégories plus précises telles qu’Appels offerts, Appels ayant obtenu une réponse et Appels abandonnés.

La meilleure façon de tirer parti du rapport d’utilisation de Response Group est de comprendre la différence entre les types d’appel signalés :

- **Appels reçus**. Nombre total d’appels reçus par toutes les instances de l’application Response Group.

- **Appels réussis**. Nombre total d’appels auxquels l’application Response Group a répondu.

- **Appels offerts**. Nombre total d’appels transférés à un agent Response Group.

- **Appels ayant obtenu une réponse**. Nombre total d’appels auxquels un agent Response Group a effectivement répondu.

- **Pourcentage d’appels abandonnés**. Pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez reçu dix appels et sept avec réponse, vous soustrayez sept de dix et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par dix, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.

- **Appels transférés**. Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.

Si vous examinez le rapport d’utilisation de Response Group et que vous ne vous souvenez pas de la définition des types d’appels indiqués, il suffit de pointer le curseur de la souris sur l’étiquette du type d’appel concerné et une info-bulle s’affiche contenant une brève description du type de l’appel.

Le rapport d’utilisation de Response Group vous permet de filtrer sur un URI de flux de travail (l’adresse SIP associée à ce flux de travail). Cependant, les URI de flux de travail ne s’affichent pas réellement dans le rapport. Si vous cherchez à identifier les flux de travail qui répondent le plus aux appels ou ceux qui reçoivent le plus d’appels transférés, cliquez sur la mesure appropriée pour ouvrir le rapport des listes d’appels Response Group pour la période donnée. Ce rapport, en revanche, indique les URI de flux de travail.

## <a name="accessing-the-response-group-usage-report"></a>Accéder au rapport d’utilisation de Response Group

Le rapport d’utilisation de Response Group est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder à la [Réponse groupe Call List Report dans Skype pour Business Server](call-list-report.md) en cliquant sur une des mesures suivantes :

- Appels reçus

- Appels réussis

- Appels offerts

- Appels ayant obtenu une réponse

- Appels transférés

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Tirer le meilleur parti du rapport d’utilisation de Response Group

L’utilisation la plus intéressante de ce rapport n’est peut-être pas la plus évidente : il s’agit de sa capacité à recueillir des informations d’utilisation pour un seul flux de travail Response Group.

> [!CAUTION]
> Un workflow Response Group est simplement un ensemble d’instructions qui détermine l’action Skype pour Business Server lorsqu’un utilisateur compose un numéro de téléphone donné. À cette fin, chaque flux de travail est associé à un numéro de téléphone unique. Lorsqu’une personne appelle ce numéro, le flux de travail détermine comment les appels seront gérés. Par exemple, le flux de travail peut entraîner l’appel à être acheminés vers une série de questions de réponse vocale interactive qui demande à l’appelant d’entrer des informations supplémentaires (« appuyez sur 1 pour la prise en charge matérielle. Appuyez sur 2 pour la prise en charge logicielle. »). Sinon, le flux de travail peut entraîner l’appel est placé dans une file d’attente, l’appelant mis en attente jusqu'à ce qu’un agent soit disponible pour répondre à l’appel. La disponibilité des agents pour répondre aux appels dépend également du flux de travail : flux de travail est utilisées pour configurer les heures ouvrées (les jours de la semaine) et les heures du jour quand les agents sont disponibles pour répondre aux appels et (lorsqu’aucun agents ne sont disponibles pour répondre à des jours de congés appels). Chaque fois que vous composez un numéro de téléphone qui appartient à l’application Response Group vous sont en appelant un workflow Response Group. 

Même si les URI de flux de travail ne s’affichent pas dans le rapport d’utilisation de Response Group, il est encore possible d’afficher les statistiques d’utilisation pour un seul flux de travail, ce qui est souvent très utile. Par exemple, supposons que vous avez récemment lancé une nouvelle campagne publicitaire et que vous souhaitez savoir si des personnes appellent pour en savoir plus sur le produit. Si vous avez associé un flux de travail Response Group au numéro de téléphone indiqué dans la campagne publicitaire, vous pouvez facilement consulter le nombre de personnes (s’il y en a) qui ont appelé ce numéro.

Vous pouvez aussi utiliser une approche similaire pour évaluer le nombre d’appels gérés par votre support technique interne ou votre service client.

Pour consulter les statistiques d’utilisation d’un flux de travail en particulier, entrez l’URI du flux de travail dans la zone correspondante. Comme indiqué auparavant, les URI de flux de travail (adresse SIP associée au flux de travail) ne s’affichent pas dans le rapport. Cela signifie que vous devez utiliser un autre moyen pour déterminer l’URI d’un flux de travail. Pour ce faire consiste à utiliser Windows PowerShell et le Skype pour Business Server Management Shell. Par exemple, cette commande renvoie les URI de tous vos flux de travail Response Group :

```
Get-CsRgsWorkflow | Select-Object Name, PrimaryUri
```

Des données semblables à ceci sont renvoyées :

<pre>
Name                            PrimaryUri
----                            ----------
Customer Support                sip:support@litwareinc.com
Help Desk                       sip:helpdesk@litwareinc.com
New Ad Campaign                 sip:newads@litwareinc.com
</pre>

Cette commande renvoie les informations relatives à un seul flux de travail, celui qui porte le nom « New Ad Campaign » :

```
Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri
```

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’utilisation de Response Group vous permet d’afficher les données de tous vos flux de travail Response Group ou d’un seul. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’utilisation de Response Group.

**Filtres du rapport d’utilisation de Response Group**


| **Nom**               | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/>                                                                                                                              |
| **À** <br/>           | Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/>                                                                                                                                     |
| **Intervalle** <br/>     | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
| **URI du flux de travail** <br/> | Vous permet de limiter les données renvoyées au flux de travail Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’utilisation de Response Group.

**Mesures du rapport d’utilisation de Response Group**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Jour** <br/> **Toutes les semaines** <br/> **Mois** <br/> |Non  <br/> |Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.  <br/> |
|**Appels reçus** <br/> |Non  <br/> |Nombre total d’appels reçus par toutes les instances de l’application Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.  <br/> |
|**Appels réussis** <br/> |Non  <br/> |Nombre total d’appels auxquels l’application Response Group a répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.  <br/> |
|**Appels offerts** <br/> |Non  <br/> |Nombre total d’appels qui ont été transférés à un agent Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.  <br/> |
|**Appels ayant obtenu une réponse** <br/> |Non  <br/> |Nombre total d’appels auxquels un agent Response Group a effectivement répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.  <br/> |
|**Pourcentage d’appels abandonnés** <br/> |Non  <br/> |Nombre total d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Ce chiffre est calculé en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez 10 appels reçus et sept avec réponse, vous soustrayez 7 de 10 et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.  <br/> |
|**Minutes d’appel moyennes par agent** <br/> |Non  <br/> |Temps moyen consacré par un agent Response Group à un appel.  <br/> |
|**Appels transférés** <br/> |Non  <br/> |Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.  <br/> |


