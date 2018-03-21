---
title: "En conservant les fichiers volumineux attachés à un Skype pour une réunion d’affaires"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargement. Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de tout participant à une boîte aux lettres est placée sur Litigation Hold, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas d’e-Discovery dans la sécurité pour Microsoft Office 365 &amp; Centre de conformité. Ce contenu est enregistré dans les dossiers des éléments récupérables participants dans leurs boîtes aux lettres."
ms.openlocfilehash: 59e1470d36aac988b1e0ff6ee40ebc1fb61967ed
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>En conservant les fichiers volumineux attachés à un Skype pour une réunion d’affaires

Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargement. Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de tout participant à une boîte aux lettres est placée sur Litigation Hold, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas d’e-Discovery dans la sécurité pour Microsoft Office 365 &amp; Centre de conformité. Ce contenu est enregistré dans les dossiers des **Éléments récupérables** participants dans leurs boîtes aux lettres.
  
Les fichiers qui sont conservés dans des boîtes aux lettres en attente sont indexés et peuvent par conséquent être recherchés lors de l’exécution d’une recherche de contenu de sécurité &amp; centre de conformité lors de la recherche de boîte aux lettres d’un participant. Toutefois, les fichiers joints de plus de 39 Mo sont fractionnées en plusieurs fichiers plus petits et enregistrement comme des fichiers compressés (.zip). Le *contenu* de ces petits fichiers n’est pas indexée pour la recherche et ne peut pas être retourné dans une recherche de contenu. Toutefois, les *métadonnées* de ces fichiers (par exemple, le nom de fichier et l’auteur) sont indexés pour la recherche et peuvent être retournés dans une recherche de contenu.
  
> [!NOTE]
> Si la boîte aux lettres est pleine ou l’administration des clients a configuré MaxSendSize inférieure à 39 Mo, téléchargé le fichier de données ne sont pas conservées à tout. MaxSendSize par défaut est de 150 Mo, mais les administrateurs de clients peuvent configurer MaxSendSize pour être aussi petits que 1 Mo. 
  
Boîtes aux lettres qui ne sont pas en attente n’aura pas de données de réunion enregistrées. Par exemple, lors d’une réunion de trois personnes dans dont les boîtes aux lettres de deux participants sont marqués pour la rétention, les données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas à la boîte aux lettres du participant tiers, boîte aux lettres n’est pas sur Maintenez.
  
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Définir des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
  