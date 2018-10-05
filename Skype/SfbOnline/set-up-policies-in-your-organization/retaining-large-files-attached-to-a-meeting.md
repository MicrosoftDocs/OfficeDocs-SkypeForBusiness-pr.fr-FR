---
title: Conservation des fichiers volumineux attachés à un Skype pour la réunion d’entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargent. Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de n’importe quel participant de boîte aux lettres est mis en attente pour litige, qui a une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas de découverte électronique de sécurité Office 365 &amp; Centre de conformité. Ce contenu est enregistré dans les dossiers d’éléments récupérables des participants dans leurs boîtes aux lettres.
ms.openlocfilehash: 103fa8b9602c4db1c5399a97a94613ac8e7b8621
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429380"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservation des fichiers volumineux attachés à un Skype pour la réunion d’entreprise

Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargent. Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de n’importe quel participant de boîte aux lettres est mis en attente pour litige, qui a une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas de découverte électronique de sécurité Office 365 &amp; Centre de conformité. Ce contenu est enregistré dans les dossiers **d’Éléments récupérables** des participants dans leurs boîtes aux lettres.
  
Fichiers qui sont conservés dans les boîtes aux lettres en attente sont indexées et par conséquent, peuvent être recherchés lors de l’exécution d’une recherche de contenu dans la sécurité &amp; centre de conformité lors de la recherche de boîte aux lettres d’un participant. Toutefois, des fichiers joints sont supérieures à 30 Mo sont divisée en deux ou plusieurs fichiers plus petits et enregistrement en tant que fichiers compressé (.zip). Le *contenu* de ces fichiers plus petits n’est pas indexé pour la recherche et ne peut-être pas être retournées dans une recherche de contenu. Toutefois, les *métadonnées* de ces fichiers (tels que le nom de fichier et l’auteur) sont indexé pour la recherche et peuvent être renvoyée dans une recherche de contenu.
  
> [!NOTE]
> Si la boîte aux lettres est plein ou l’administrateur du client a configuré MaxSendSize est inférieure à 30 Mo, les données du fichier téléchargé ne seront pas conservées tout. La valeur par défaut MaxSendSize est de 150 Mo, mais les administrateurs de clients peuvent configurer MaxSendSize pour être aussi faible que 1 Mo. 
  
Boîtes aux lettres qui ne sont pas en attente n’auront pas toutes les données réunion enregistrées. Par exemple, dans une réunion de trois personnes dans, dont les boîtes aux lettres de deux participants sont marqués pour la conservation des données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas la boîte aux lettres du troisième participant, boîte aux lettres n’est pas sur Maintenez.
  
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
 