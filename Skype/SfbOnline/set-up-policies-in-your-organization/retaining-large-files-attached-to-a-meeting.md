---
title: Conservation de fichiers volumineux attachés à une réunion Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Vous pouvez joindre des fichiers à une réunion Skype Entreprise, que les participants peuvent ensuite ouvrir et télécharger. Les fichiers joints à Skype Entreprise réunions sont conservés dans les boîtes aux lettres de tout participant dont la boîte aux lettres est placée en attente de litige, dont une stratégie de rétention Microsoft 365 ou Office 365 est appliquée, ou est placée dans une conservation associée à un cas eDiscovery dans le portail de conformité Microsoft Purview. Ce contenu est enregistré dans les dossiers Éléments récupérables des participants dans leurs boîtes aux lettres.
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031869"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservation de fichiers volumineux attachés à une réunion Skype Entreprise

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Vous pouvez joindre des fichiers à une réunion Skype Entreprise, que les participants peuvent ensuite ouvrir et télécharger. Les fichiers joints à Skype Entreprise réunions sont conservés dans les boîtes aux lettres de tout participant dont la boîte aux lettres est placée en attente de litige, dont une stratégie de rétention Microsoft 365 ou Office 365 est appliquée, ou est placée dans une conservation associée à un cas eDiscovery dans le portail de conformité Microsoft Purview. Ce contenu est enregistré dans les dossiers **Éléments récupérables** des participants dans leurs boîtes aux lettres.
  
Les fichiers conservés dans les boîtes aux lettres en attente sont indexés et peuvent donc être recherchés lors de l’exécution d’une recherche de contenu dans le Centre de conformité de sécurité &amp; lors de la recherche dans la boîte aux lettres d’un participant. Toutefois, les fichiers attachés de plus de 30 Mo sont divisés en deux ou plusieurs fichiers plus petits et enregistrés en tant que fichiers compressés (.zip). Le  *contenu*  de ces fichiers plus petits n’est pas indexé pour la recherche et peut ne pas être retourné dans une recherche de contenu. Toutefois, les *métadonnées*  de ces fichiers (telles que le nom et l’auteur du fichier) sont indexées pour la recherche et peuvent être retournées dans une recherche de contenu.
  
> [!IMPORTANT]
> Les paramètres MaxReceiveSize et MaxSendSize d’une boîte aux lettres Exchange Online peuvent affecter la possibilité de conserver des fichiers volumineux à partir de Skype Entreprise réunions. Les paramètres par défaut pour MaxReceiveSize et MaxSendSize sont respectivement de 36 Mo et 35 Mo. Toutefois, ces paramètres par défaut sont trop petits pour conserver un fichier d’une réunion Skype Entreprise supérieure à 30 Mo. Cela est dû au fait que Exchange Online utilise l’encodage en base64 des pièces jointes de message et d’autres données binaires. Lorsqu’un message est encodé, sa taille est augmentée d’environ 33 %. Par conséquent, pour vous assurer que les fichiers volumineux des réunions Skype Entreprise sont conservés, nous vous recommandons d’augmenter la valeur de MaxReceiveSize et MaxSendSize à 39 Mo (soit environ 33 % de plus que la limite de taille de 30 Mo expliquée précédemment) pour les utilisateurs placés en attente. Sinon, il se peut qu’un fichier volumineux attaché à une réunion Skype Entreprise ne soit pas conservé. Pour plus d’informations sur l’utilisation des commandes **Set-Mailbox -MaxReceiveSize** et **Set-Mailbox -MaxSendSize** dans Exchange Online PowerShell, consultez [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Les boîtes aux lettres qui ne sont pas en attente n’auront pas de données de réunion enregistrées. Par exemple, dans une réunion à trois personnes dans laquelle les boîtes aux lettres de deux participants sont marquées pour conservation, les données de réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas dans la boîte aux lettres du troisième participant, dont la boîte aux lettres n’est pas en attente.
  
## <a name="related-topics"></a>Sujets associés
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
