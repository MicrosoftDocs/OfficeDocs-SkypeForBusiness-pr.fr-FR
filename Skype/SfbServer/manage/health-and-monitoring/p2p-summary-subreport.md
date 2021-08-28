---
title: Sous-rapport de résumé P2P dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Résumé : Découvrez le sous-rapport de synthèse P2P dans Skype Entreprise Server.'
ms.openlocfilehash: 8304399106e17654ad350bc0a2e5eff1ecc90ace
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622326"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Sous-rapport de résumé P2P dans Skype Entreprise Server
 
**Résumé :** Découvrez le sous-rapport de synthèse P2P dans Skype Entreprise Server.
  
Le sous-rapport de résumé P2P offre un aperçu général de vos sessions de communication pair au pair ayant échoué.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de résumé P2P.
  
**Filtres de sous-rapport de résumé P2P**

|**Nom**|**Description**|
|:-----|:-----|
|**From** <br/> |Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.<br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le sous-rapport de résumé P2P.
  
**Mesures de sous-rapport de résumé P2P**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.  <br/> |
|**Taux d’échec** <br/> |Non  <br/> |Pourcentage de sessions d’égal à égal ayant échoué.  <br/> |
|**Sessions par modalité** <br/> |Non  <br/> |Nombre total de sessions groupées par modalité (par exemple, messagerie instantanée).  <br/> |
|**Taux d’échec par modalité** <br/> |Non  <br/> |Nombre total de sessions ayant échoué groupées par modalité (par exemple, messagerie instantanée).  <br/> |
   

