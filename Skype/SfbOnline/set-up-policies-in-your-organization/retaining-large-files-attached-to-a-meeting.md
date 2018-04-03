---
title: En conservant les fichiers volumineux attachés à un Skype pour une réunion d’affaires
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
description: Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargement. Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de tout participant à une boîte aux lettres est placée sur Litigation Hold, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas d’e-Discovery dans la sécurité pour Microsoft Office 365 &amp; Centre de conformité. Ce contenu est enregistré dans les dossiers des éléments récupérables participants dans leurs boîtes aux lettres.
ms.openlocfilehash: c2f032a34cc5de604bb5437554add885c29645a0
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="02f4d-105">En conservant les fichiers volumineux attachés à un Skype pour une réunion d’affaires</span><span class="sxs-lookup"><span data-stu-id="02f4d-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="02f4d-106">Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargement.</span><span class="sxs-lookup"><span data-stu-id="02f4d-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="02f4d-107">Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de tout participant à une boîte aux lettres est placée sur Litigation Hold, comporte une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas d’e-Discovery dans la sécurité pour Microsoft Office 365 &amp; Centre de conformité.</span><span class="sxs-lookup"><span data-stu-id="02f4d-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="02f4d-108">Ce contenu est enregistré dans les dossiers des **Éléments récupérables** participants dans leurs boîtes aux lettres.</span><span class="sxs-lookup"><span data-stu-id="02f4d-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="02f4d-109">Les fichiers qui sont conservés dans des boîtes aux lettres en attente sont indexés et peuvent par conséquent être recherchés lors de l’exécution d’une recherche de contenu de sécurité &amp; centre de conformité lors de la recherche de boîte aux lettres d’un participant.</span><span class="sxs-lookup"><span data-stu-id="02f4d-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="02f4d-110">Toutefois, les fichiers joints de plus de 39 Mo sont fractionnées en plusieurs fichiers plus petits et enregistrement comme des fichiers compressés (.zip).</span><span class="sxs-lookup"><span data-stu-id="02f4d-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="02f4d-111">Le *contenu* de ces petits fichiers n’est pas indexée pour la recherche et ne peut pas être retourné dans une recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="02f4d-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="02f4d-112">Toutefois, les *métadonnées* de ces fichiers (par exemple, le nom de fichier et l’auteur) sont indexés pour la recherche et peuvent être retournés dans une recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="02f4d-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02f4d-113">Si la boîte aux lettres est pleine ou l’administration des clients a configuré MaxSendSize inférieure à 39 Mo, téléchargé le fichier de données ne sont pas conservées à tout.</span><span class="sxs-lookup"><span data-stu-id="02f4d-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="02f4d-114">MaxSendSize par défaut est de 150 Mo, mais les administrateurs de clients peuvent configurer MaxSendSize pour être aussi petits que 1 Mo.</span><span class="sxs-lookup"><span data-stu-id="02f4d-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="02f4d-115">Boîtes aux lettres qui ne sont pas en attente n’aura pas de données de réunion enregistrées.</span><span class="sxs-lookup"><span data-stu-id="02f4d-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="02f4d-116">Par exemple, lors d’une réunion de trois personnes dans dont les boîtes aux lettres de deux participants sont marqués pour la rétention, les données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas à la boîte aux lettres du participant tiers, boîte aux lettres n’est pas sur Maintenez.</span><span class="sxs-lookup"><span data-stu-id="02f4d-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="02f4d-117">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="02f4d-117">Related topics</span></span>
[<span data-ttu-id="02f4d-118">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="02f4d-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="02f4d-119">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="02f4d-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="02f4d-120">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="02f4d-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="02f4d-121">Définir des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="02f4d-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 