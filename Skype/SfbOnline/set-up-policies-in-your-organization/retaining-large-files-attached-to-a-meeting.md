---
title: Conserver les fichiers de grande taille joints à Skype Entreprise réunion
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
description: Vous pouvez joindre des fichiers à Skype Entreprise réunion, que les participants peuvent ensuite ouvrir et télécharger. Les fichiers joints aux réunions Skype Entreprise sont conservés dans les boîtes aux lettres des participants dont la boîte aux lettres est placée en conservation pour litige, à laquelle une stratégie de rétention Microsoft 365 ou Office 365 est appliquée ou qui est placée sur une conservation associée à un cas de découverte électronique dans le Centre de conformité Microsoft 365. Ce contenu est enregistré dans les dossiers Éléments récupérables des participants dans leur boîte aux lettres.
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240106"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conserver les fichiers de grande taille joints à Skype Entreprise réunion

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Vous pouvez joindre des fichiers à Skype Entreprise réunion, que les participants peuvent ensuite ouvrir et télécharger. Les fichiers joints aux réunions Skype Entreprise sont conservés dans les boîtes aux lettres des participants dont la boîte aux lettres est placée en conservation pour litige, à laquelle une stratégie de rétention Microsoft 365 ou Office 365 est appliquée ou qui est placée sur une conservation associée à un cas de découverte électronique dans le Centre de conformité Microsoft 365. Ce contenu est enregistré dans les dossiers Éléments **récupérables** des participants dans leur boîte aux lettres.
  
Les fichiers conservés dans des boîtes aux lettres en attente sont indexés et peuvent donc faire l’être lors de l’exécution d’une recherche de contenu dans le Centre de conformité de la sécurité lors de la recherche dans la boîte aux lettres &amp; d’un participant. Toutefois, les fichiers joints d’une taille supérieure à 30 Mo sont fractionés en deux ou plus fichiers plus petits et enregistrés en tant que fichiers compressés (.zip). Le  *contenu*  de ces fichiers de plus petite taille n’est pas indexé pour la recherche et peut ne pas être renvoyé dans une recherche de contenu. Toutefois, les *métadonnées*  de ces fichiers (par exemple, le nom du fichier et l’auteur) sont indexées pour la recherche et peuvent être renvoyées dans une recherche de contenu.
  
> [!IMPORTANT]
> Les paramètres MaxReceiveSize et MaxSendSize pour une boîte aux lettres Exchange Online peuvent affecter la possibilité de conserver des fichiers de grande taille Skype Entreprise réunions. Les paramètres par défaut pour MaxReceiveSize et MaxSendSize sont respectivement de 36 Mo et 35 Mo. Toutefois, ces paramètres par défaut sont trop petits pour conserver un fichier d’Skype Entreprise réunion d’une taille supérieure à 30 Mo. Cela est dû au Exchange Online codage Base64 des pièces jointes de message et d’autres données binaires. Lorsqu’un message est codé, sa taille augmente d’environ 33 %. Par conséquent, pour vous assurer que les fichiers volumineux des réunions Skype Entreprise sont conservés, nous vous recommandons d’augmenter la valeur pour MaxReceiveSize et MaxSendSize à 39 Mo (soit environ 33 % de plus que la limite de taille 30 Mo qui a été expliquée précédemment) pour les utilisateurs placés en attente. Sinon, un fichier de grande taille joint à Skype Entreprise réunion peut ne pas être conservé. Pour plus d’informations sur l’utilisation des commandes **Set-Mailbox -MaxReceiveSize** et **Set-Mailbox -MaxSendSize** dans Exchange Online PowerShell, voir [Set-Mailbox.](/powershell/module/exchange/mailboxes/Set-Mailbox)
  
Les boîtes aux lettres qui ne sont pas en attente ne seront pas enregistrées. Par exemple, dans une réunion à trois personnes dans laquelle les boîtes aux lettres de deux participants sont marquées pour rétention, les données de réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas dans la boîte aux lettres du troisième participant, dont la boîte aux lettres n’est pas en attente.
  
## <a name="related-topics"></a>Sujets associés
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
