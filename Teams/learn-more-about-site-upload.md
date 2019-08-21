---
title: Ajout et mise à jour des données d’emplacements
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Apprenez à télécharger sur un site.
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: bed4487a944bafb8092f63fb4582b165375a1e83
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484025"
---
<a name="adding-and-updating-locations-data"></a>Ajout et mise à jour des données d’emplacements
============================

Les emplacements sont utilisés au sein de votre organisation pour indiquer l’emplacement physique des bureaux, des bâtiments ou des sites d’organisation. La page emplacements fournit aux administrateurs la possibilité de fournir un fichier texte (. csv ou. TSV) contenant une liste des emplacements physiques et leurs sous-réseaux de réseaux associés. Ce fichier est utilisé par le tableau de bord d’analyse des appels et de qualité des appels pour générer des rapports. Lorsque le client charge son mappage de sous-réseau, les rapports fournis par ces services contiennent également les noms d’emplacements, ce qui facilite la compréhension et l’utilisation des rapports pour la correction des problèmes potentiels.

Les données d’emplacement fournies constituent une seule structure de données: aucune interface n’est actuellement disponible pour apporter des modifications individuelles aux données d’emplacement. 

**Pour modifier le tableau des sous-réseaux et des emplacements**

1. Cliquez sur **remplacer les données d’emplacements**.
2. Dans le volet **remplacer les données** de l’emplacement, cliquez sur **Sélectionner un fichier**, puis recherchez et chargez votre fichier. csv ou. TSV modifié. 
3. Cliquez sur **Télécharger**. 


Vous pouvez télécharger un exemple de modèle [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Pour créer votre fichier de données, vous pouvez utiliser l’exemple suivant. 

> [!IMPORTANT]
> Votre fichier de données ne doit pas contenir d’en-têtes de colonne (par exemple, réseau, nom du réseau, etc.). Celles-ci sont utilisées ici à des fins d’information uniquement. </br>

|Réseau|Nom du réseau|Plage de réseaux|Nom du bâtiment|Type de propriété|Type de bâtiment|Créer un type de bureau|Ville|Code postal|Pays|État|Région|Dans l’entreprise|Itinéraire rapide|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso bail RE&F|Bureau|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso bail RE&F|Bureau|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso bail RE&F|Bureau|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso bail RE&F|Bureau|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|


Pour plus d’informations sur la mise en forme de votre fichier de données, voir [format de fichier de données client et structure du fichier de données](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).


## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels](set-up-call-analytics.md)
