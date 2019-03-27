---
title: Rapport de liste d’appels Response Group dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Résumé : Découvrez l’application Response Group dans Skype pour Business Server.'
ms.openlocfilehash: 5fe2665a90d5a2122965dd89fdf58087d910de47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883258"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Rapport de liste d’appels Response Group dans Skype pour Business Server

**Résumé :** Découvrez l’application Response Group dans Skype pour Business Server.

L’application Response Group offre un moyen de Skype pour Business Server répondre et acheminer les appels téléphoniques basé sur le numéro qui a été composé et, le cas échéant, les réponses de l’appelant à une série de questions. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone pour votre support technique, Skype pour Business Server peut acheminer automatiquement appel au premier agent de bureau d’aide disponibles. Vous pouvez également Skype pour Business Server peut demander une série de questions (« appuyez sur 1 si vous rencontrez des problèmes de matériel. Appuyez sur 2 pour des problèmes logiciels. Appuyez sur 3 Si vous rencontrez des problèmes réseau. ») puis d’acheminer l’appel vers l’agent d’assistance aide plus approprié en fonction de la réponse à ces questions.

Le Rapport des listes d’appels Response Group représente une collection d’appels effectués pendant une période spécifiée et pour un type d’appel spécifié. Le Rapport d’utilisation de Response Group (qui doit être ouvert au préalable pour que vous puissiez ouvrir le Rapport des listes d’appels Response Group) reconnaît les types d’appels suivants :

- **Appels reçus**. Nombre total d’appels reçus par toutes les instances de l’application Response Group.

- **Appels réussis**. Nombre total d’appels auxquels l’application Response Group a répondu.

- **Appels offerts**. Nombre total d’appels transférés à un agent Response Group.

- **Appels ayant obtenu une réponse**. Nombre total d’appels auxquels un agent Response Group a effectivement répondu.

- **Pourcentage d’appels abandonnés.** Pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez reçu dix appels et sept avec réponse, vous soustrayez sept de dix et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par dix, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.

- **Appels transférés**. Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.

## <a name="accessing-the-response-group-call-list-report"></a>Accès au Rapport des listes d’appels Response Group

Le rapport de la liste des appels Response Group est uniquement accessible en cliquant sur une des mesures suivantes que qui se trouvés dans le [Rapport d’utilisation de Response Group dans Skype pour Business Server](response-group-usage-report.md):

- Appels reçus

- Appels réussis

- Appels offerts

- Appels ayant obtenu une réponse

- Appels transférés

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Utilisation optimale du Rapport des listes d’appels Response Group

Le Rapport des listes d’appels Response Group vous permet de limiter les données affichées aux appels impliquant un flux de travail Response Group particulier. Pour cela, vous devez entrer l’URI de flux de travail (l’adresse SIP du flux de travail) dans la zone URI du flux de travail. Avant cela, vous devez cependant être en mesure de voir cette zone URI du flux de travail. Pour afficher les options de filtrage du Rapport des listes d’appels Response Group, cliquez sur le bouton Afficher / Masquer les paramètres dans la partie supérieure gauche de la fenêtre de rapport.

Notez que le Rapport des listes d’appels Response Group n’affiche pas d’informations relatives au code de réponse ou à l’ID de diagnostic si vous maintenez le pointeur de la souris sur l’une de ces mesures. Si vous avez besoin de plus d’informations, vous pourrez Notez l’ID de Diagnostic et/ou le code de réponse, puis recherchez ces valeurs dans le [Rapport des principales défaillances dans Skype pour Business Server](top-failures-report.md).

Si vous souhaitez obtenir la réponse à une question telle que « Quel est le flux de travail ayant reçu le plus d’appels ? », vous pouvez procéder comme suit :

1. Dans le Rapport d’utilisation de Response Group, définissez la période souhaitée, puis cliquez sur la mesure Appels reçus pour ouvrir le Rapport des listes d’appels Response Group.

2. Exportez les données affichées dans le Rapport des listes d’appels Response Group. Par exemple, vous pourriez exporter les données au format Microsoft Excel, puis utiliser Excel pour convertir ces données en un fichier de valeurs séparées par des virgules.

3. Exécutez vos analyses à l’aide de Windows PowerShell.

Par exemple, si vous avez enregistré les données dans un fichier nommé C:\Data\Response_Group_Call_List_Report.csv, vous pouvez utiliser la commande suivante pour renvoyer le nombre total d’appels reçus pour chaque flux de travail mentionné dans le rapport :

```
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

Des informations analogues aux suivantes seront renvoyées :

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de liste des appels Response Group.

**Filtres de rapport de liste des appels Response Group**


| **Nom**               | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
| **À** <br/>           | Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/>        |
| **URI du flux de travail** <br/> | Vous permet de limiter les données renvoyées au flux de travail Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Appels** <br/>        | Vous pouvez sélectionner l’un des types d’appels suivants : <br/>  Appels reçus <br/>  Appels réussis <br/>  Appels offerts <br/>  Appels ayant obtenu une réponse <br/>  Appels transférés <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de liste des appels Response Group pour chaque appel reçu par l’application Response Group.

**Mesures du rapport de liste des appels Response Group**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Appelant** <br/> |Non  <br/> |Adresse SIP de l’appelant.  <br/> |
|**Flux de travail** <br/> |Non  <br/> |Adresse SIP du flux de travail Response Group.  <br/> |
|**Heure de début** <br/> |Non  <br/> |Date et heure de début de l’appel.  <br/> |
|**Heure de fin** <br/> |Non  <br/> |Date et heure de fin de l’appel.  <br/> |
|**Code de réponse** <br/> |Non  <br/> |Code de réponse SIP envoyé lors de l’échec de session.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.  <br/> |


