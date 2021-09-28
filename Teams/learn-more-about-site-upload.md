---
title: Ajouter et mettre à jour les étiquettes de rapport
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment ajouter et mettre à jour des étiquettes de rapports en chargeant un fichier texte contenant la liste des emplacements physiques et des sous-réseaux associés.
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
ms.openlocfilehash: 189b821e7238911190c4c72c07b863fc961f3074
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984609"
---
# <a name="add-and-update-reporting-labels"></a>Ajouter et mettre à jour les étiquettes de rapport

Les étiquettes de rapports sont utilisées dans votre organisation pour indiquer les emplacements physiques des bureaux, bâtiments ou sites organisationnels. La page Étiquettes de rapports du Centre d’administration Microsoft Teams vous permet de fournir un fichier texte (.csv ou .tsv) contenant la liste des emplacements physiques et les sous-réseaux réseau associés. Ce fichier est utilisé par Call Analytics pour générer des rapports. Lorsque vous chargez votre mappage de sous-réseau, les rapports fournis par ces services contiennent également le nom des emplacements, ce qui facilite la compréhension et l’utilisation des rapports afin de corriger les problèmes potentiels.

> [!IMPORTANT]
> Les étiquettes de rapports que vous téléchargez sont traitées comme données de *support* dans le cadre de votre contrat concernant Office 365, y compris les informations qui seraient autrement considérées comme des données client ou *des données personnelles.*  N’incluez pas de données que vous ne souhaitez pas fournir à Microsoft en tant que données de *support,* car ces informations seront visibles par les ingénieurs Microsoft à des fins de support.

Les étiquettes et les données de localisation des rapports que vous fournissez sont une structure de données unique ; il n’existe actuellement aucune interface disponible pour apporter des modifications individuelles aux données.

**Pour modifier le tableau des sous-réseaux et des emplacements**

1. Dans le navigation gauche du Centre Microsoft Teams d’administration, cliquez sur **Analyse & étiquettes**  >  **de rapports de rapports.**
2. Cliquez **Télécharger données.**
3. Dans le **Télécharger données,** cliquez sur Sélectionner un **fichier,** puis recherchez et chargez votre fichier .csv ou .tsv.
4. Cliquez **Télécharger**.

Vous pouvez télécharger un exemple de modèle [ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Utilisez l’exemple suivant pour créer votre fichier de données.

> [!IMPORTANT]
> Votre fichier de données ne doit pas contenir d’en-têtes de colonne (par exemple, Réseau, Nom du réseau, etc.). Ceux-ci sont utilisés ici uniquement à des fins d’information. <br>

|Réseau|Nom du réseau|Plage réseau|Nom du bâtiment|Type de propriété|Type de bâtiment|Type Office création|Ville|Code postal|Pays|État|Région|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|États-Unis|CA|États-Unis|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|États-Unis|CA|États-Unis|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|États-Unis|CA|États-Unis|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|États-Unis|CA|États-Unis|1|1|

Pour plus d’informations sur la mise en forme de votre fichier de données, voir Format de fichier de données client et [Structure du fichier de données du bâtiment.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser les données d’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)
