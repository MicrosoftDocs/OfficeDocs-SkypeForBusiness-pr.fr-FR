---
title: Conservation de fichiers volumineux joints à une réunion Skype entreprise
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Vous pouvez joindre des fichiers à une réunion Skype entreprise et permettre aux participants d’ouvrir et de télécharger des fichiers. Les fichiers joints à des réunions Skype entreprise sont conservés dans les boîtes aux lettres de tout participant dont la boîte aux lettres est en attente de litige, qu’une stratégie de rétention Microsoft 365 ou Office 365 est appliquée ou qu’elle est placée sur une conservation associée à un cas de découverte électronique dans le centre de conformité Microsoft 365. Ce contenu est enregistré dans les dossiers éléments récupérables des participants dans leurs boîtes aux lettres.
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164073"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservation de fichiers volumineux joints à une réunion Skype entreprise

Vous pouvez joindre des fichiers à une réunion Skype entreprise et permettre aux participants d’ouvrir et de télécharger des fichiers. Les fichiers joints à des réunions Skype entreprise sont conservés dans les boîtes aux lettres de tout participant dont la boîte aux lettres est en attente de litige, qu’une stratégie de rétention Microsoft 365 ou Office 365 est appliquée ou qu’elle est placée sur une conservation associée à un cas de découverte électronique dans le centre de conformité Microsoft 365. Ce contenu est enregistré dans les dossiers **éléments récupérables** des participants dans leurs boîtes aux lettres.
  
Les fichiers conservés dans les boîtes aux lettres en attente sont indexés et peuvent donc être recherchés lors de l’exécution d' &amp; une recherche de contenu dans le centre de conformité de la sécurité lors de la recherche dans la boîte aux lettres d’un participant. Toutefois, les fichiers joints de plus de 30 Mo sont fractionnés en deux fichiers plus petits et enregistrés sous forme de fichiers compressés (. zip). Le *contenu* de ces fichiers plus petits n’est pas indexé pour la recherche et n’est peut-être pas renvoyé dans une recherche de contenu. Toutefois, les *métadonnées* de ces fichiers (par exemple, nom de fichier et auteur) sont indexées pour la recherche et peuvent être renvoyées lors d’une recherche de contenu.
  
> [!IMPORTANT]
> Les paramètres MaxReceiveSize et MaxSendSize d’une boîte aux lettres Exchange Online peuvent affecter la possibilité de conserver les fichiers volumineux des réunions Skype entreprise. Les paramètres par défaut pour MaxReceiveSize et MaxSendSize sont respectivement de 36 Mo et 35 Mo. Toutefois, ces paramètres par défaut sont trop petits pour conserver les fichiers d’une réunion Skype entreprise de plus de 30 Mo. Cela est dû au fait qu’Exchange Online utilise le codage en base64 des pièces jointes et d’autres données binaires. Quand un message est encodé, sa taille augmente approximativement de 33%. Par conséquent, pour vous assurer que les fichiers volumineux des réunions Skype entreprise sont conservés, nous vous conseillons d’augmenter la valeur pour MaxReceiveSize et MaxSendSize à 39 Mo (approximativement 33% de taille supérieure à la limite de taille de 30 Mo décrite précédemment) pour les utilisateurs placés en attente. Dans le cas contraire, un fichier volumineux joint à une réunion Skype entreprise peut ne pas être conservé. Pour plus d’informations sur l’utilisation des commandes **Set-Mailbox-MaxReceiveSize** et **Set-Mailbox-MaxSendSize** dans Exchange Online PowerShell, voir [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Les données de réunion qui ne sont pas en attente ne seront pas enregistrées. Par exemple, dans le cas d’une réunion à trois personnes dans laquelle les boîtes aux lettres de deux participants sont marquées pour la rétention, les données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas dans la boîte aux lettres du tiers participant dont la boîte aux lettres n’est pas en attente.
  
## <a name="related-topics"></a>Voir aussi
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configuration des stratégies de conférence au sein de votre organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
 
