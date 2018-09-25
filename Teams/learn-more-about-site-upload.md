---
title: Ajout et mise à jour des données d’emplacements
author: tonysmit
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
description: Découvrez comment télécharger vers un site.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9f9c093e7a80a7f4f3165f58cd6dc34f532ab7e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017414"
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
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso allouée RE & F|Bureau|RE & F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso allouée RE & F|Bureau|RE & F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso allouée RE & F|Bureau|RE & F|Mountain View|94043|NOUS|CA|NOUS|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso allouée RE & F|Bureau|RE & F|Mountain View|94043|NOUS|CA|NOUS|1|1|


Pour plus d’informations sur la mise en forme de votre fichier de données, voir [format et la structure de fichier de données de création de fichiers de données client](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure).


## <a name="related-topics"></a>Rubriques connexes

[Configurer Analytique d’appel](set-up-call-analytics.md)