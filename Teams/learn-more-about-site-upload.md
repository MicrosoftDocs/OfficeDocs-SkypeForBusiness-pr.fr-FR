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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment télécharger vers un site.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9274952d74c3bf55943ed6b028fd630ab2078e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921281"
---
<a name="adding-and-updating-locations-data"></a>Ajout et mise à jour des données d’emplacements
============================

Emplacements sont utilisés dans votre organisation pour indiquer l’emplacement physique des bureaux, bâtiments ou des sites d’organisation. La page emplacements permet d’administrateurs de fournir un fichier texte (.csv ou .tsv) contenant une liste des emplacements physiques et les sous-réseaux associés. Ce fichier est utilisé par Analytique d’appel et appel du tableau de bord qualité pour la génération de rapports. Lorsque les clients téléchargement leur mappage de sous-réseau, les rapports fournis par ces services contient ainsi que les noms des emplacements facilitant les rapports à comprendre et à utiliser pour corriger les éventuels problèmes.

Les données des emplacements que vous fournissez sont une structure de données unique : il n’existe actuellement aucune interface disponible pour apporter des modifications spécifiques à des données d’emplacement. 

**Pour modifier la table de sous-réseaux et emplacements**

1. Cliquez sur **Remplacer les données d’emplacements**.
2. Dans le volet de **Remplacer les données d’emplacement** , cliquez sur **Sélectionner un fichier**et puis accédez à télécharger des .tsv fichier .csv modifié. 
3. Cliquez sur **Télécharger**. 


Vous pouvez télécharger un exemple de modèle [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Vous pouvez utiliser l’exemple suivant permet de créer votre fichier de données. 

> [!IMPORTANT]
> Votre fichier de données ne doit pas contenir les en-têtes de colonne (par exemple réseau, nom de réseau, etc.). Ils sont utilisés ici à titre informatif uniquement. </br>

|Réseau|Nom de réseau|Plage réseau|Nom de création|Type de propriété|Type de construction|Type de construction Office|Ville|Code postal|Pays|État|Région|Intérieur Corp|Itinéraire Express|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Connexion en bail Contoso RE&F|Bureau|RE&F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Connexion en bail Contoso RE&F|Bureau|RE&F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Connexion en bail Contoso RE&F|Bureau|RE&F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Connexion en bail Contoso RE&F|Bureau|RE&F|Mountain View|94043|NOUS|CA|NOUS|1|1|


Pour plus d’informations sur la mise en forme de votre fichier de données, voir [format et la structure de fichier de données de création de fichiers de données client](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure).


## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels](set-up-call-analytics.md)
