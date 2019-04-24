---
title: Sous-rapport de synthèse de conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Résumé : Découvrez le sous-rapport de synthèse de conférence dans Skype pour Business Server.'
ms.openlocfilehash: 4c4430c960ebcd296838ddca8d429d5d3ba73ca8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197512"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a>Sous-rapport de synthèse de conférence dans Skype pour Business Server
 
**Résumé :** Découvrez le sous-rapport de synthèse de conférence dans Skype pour Business Server.
  
Le sous-rapport de synthèse de conférence fournit une vision générale des sessions de conférence ayant échoué. Ces échecs de session sont répartis par type de session : sessions Focus et les sessions MCU.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de synthèse de conférence.
  
**Filtres du sous-rapport de synthèse de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
   
## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le sous-rapport de synthèse de conférence.
  
**Mesures du sous-rapport de synthèse de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences ayant eu lieu.  <br/> |
|**Nombre total de sessions de conférence** <br/> |Non  <br/> |Nombre total de sessions de conférence. Une seule conférence peut avoir plusieurs sessions : par exemple, elle peut inclure à la fois une session Focus et une session MCU.  <br/> |
|**Taux d’échec de session global** <br/> |Non  <br/> |Pourcentage de tous les échecs de conférence.  <br/> |
|**Sessions Focus** <br/> |Non  <br/> |Nombre total de sessions Focus.  <br/> |
|**Taux d’échec de focus** <br/> |Non  <br/> |Pourcentage d’échec des sessions Focus.  <br/> |
|Sessions MCU  <br/> |Non  <br/> |Nombre total de sessions MCU.  <br/> |
|**Taux d’échec MCU** <br/> |Non  <br/> |Pourcentage d’échec des sessions MCU.  <br/> |
|**Sessions MCU par modalité** <br/> |Non  <br/> |Nombre total de sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).  <br/> |
|**Taux d’échec par modalité** <br/> |Non  <br/> |Pourcentage d’échec des sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).  <br/> |
   

