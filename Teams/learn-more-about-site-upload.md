---
title: Ajouter et mettre à jour les étiquettes de rapport
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
- M365-collaboration
description: Découvrez comment ajouter et mettre à jour des étiquettes de création de rapports en chargeant un fichier texte qui contient la liste des emplacements physiques et des sous-réseaux associés.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bace73e411970ee1b907890b08a5e501daf90e50
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539641"
---
<a name="add-and-update-reporting-labels"></a>Ajouter et mettre à jour les étiquettes de rapport
============================

Les étiquettes de rapport sont utilisées dans votre organisation pour indiquer l’emplacement physique des bureaux, des bâtiments ou des sites d’organisation. La page étiquettes de rapport dans le centre d’administration de Microsoft teams vous permet de fournir un fichier texte (. csv ou. TSV) contenant une liste des emplacements physiques et leurs sous-réseaux associés. Ce fichier est utilisé par le tableau de bord d’analyse des appels et de qualité des appels pour générer des rapports. Lorsque vous chargez le mappage de votre sous-réseau, les rapports fournis par ces services contiennent également les noms d’emplacements, ce qui facilite la compréhension et l’utilisation des rapports pour la correction des problèmes potentiels.

Les étiquettes de rapport et les données d’emplacement fournies constituent une seule structure de données : aucune interface n’est actuellement disponible pour apporter des modifications individuelles aux données.

**Pour modifier le tableau des sous-réseaux et des emplacements**

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **emplacements**  >  **rapports**.
2. Cliquez sur **remplacer les données d’emplacements**.
3. Dans le volet **remplacer les données d’emplacement** , cliquez sur **Sélectionner un fichier**, puis recherchez et chargez le fichier. csv ou. TSV modifié.
4. Cliquez sur **Télécharger**.

Vous pouvez télécharger un exemple de modèle [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Utilisez l’exemple suivant pour créer votre fichier de données.

> [!IMPORTANT]
> Votre fichier de données ne doit pas contenir d’en-têtes de colonne (par exemple, réseau, nom du réseau, etc.). Celles-ci sont utilisées ici à des fins d’information uniquement. <br>

|Réseau|Nom du réseau|Plage de réseaux|Nom du bâtiment|Type de propriété|Type de bâtiment|Créer un type de bureau|Ville|Code postal|Pays|État|Région|Dans l’entreprise|Itinéraire rapide|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso bail RE&F|Office|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso bail RE&F|Office|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso bail RE&F|Office|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso bail RE&F|Office|RE&F|Affichage de montagne|94043|Nous|CA|Nous|1|1|

Pour plus d’informations sur la mise en forme de votre fichier de données, voir [format de fichier de données client et structure du fichier de données](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).

## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels](set-up-call-analytics.md)
