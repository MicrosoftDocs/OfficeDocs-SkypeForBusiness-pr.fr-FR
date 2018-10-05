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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="a0eac-105">Conservation des fichiers volumineux attachés à un Skype pour la réunion d’entreprise</span><span class="sxs-lookup"><span data-stu-id="a0eac-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="a0eac-106">Vous pouvez joindre des fichiers à un Skype pour une réunion d’affaires, les participants peuvent ensuite ouvrir et téléchargent.</span><span class="sxs-lookup"><span data-stu-id="a0eac-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="a0eac-107">Fichiers joints à Skype pour les réunions d’entreprise sont conservés dans les boîtes aux lettres de n’importe quel participant de boîte aux lettres est mis en attente pour litige, qui a une stratégie de rétention Office 365 ou est placé sur une suspension associée à un cas de découverte électronique de sécurité Office 365 &amp; Centre de conformité.</span><span class="sxs-lookup"><span data-stu-id="a0eac-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="a0eac-108">Ce contenu est enregistré dans les dossiers **d’Éléments récupérables** des participants dans leurs boîtes aux lettres.</span><span class="sxs-lookup"><span data-stu-id="a0eac-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="a0eac-109">Fichiers qui sont conservés dans les boîtes aux lettres en attente sont indexées et par conséquent, peuvent être recherchés lors de l’exécution d’une recherche de contenu dans la sécurité &amp; centre de conformité lors de la recherche de boîte aux lettres d’un participant.</span><span class="sxs-lookup"><span data-stu-id="a0eac-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="a0eac-110">Toutefois, des fichiers joints sont supérieures à 30 Mo sont divisée en deux ou plusieurs fichiers plus petits et enregistrement en tant que fichiers compressé (.zip).</span><span class="sxs-lookup"><span data-stu-id="a0eac-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="a0eac-111">Le *contenu* de ces fichiers plus petits n’est pas indexé pour la recherche et ne peut-être pas être retournées dans une recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="a0eac-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="a0eac-112">Toutefois, les *métadonnées* de ces fichiers (tels que le nom de fichier et l’auteur) sont indexé pour la recherche et peuvent être renvoyée dans une recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="a0eac-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0eac-113">Si la boîte aux lettres est plein ou l’administrateur du client a configuré MaxSendSize est inférieure à 30 Mo, les données du fichier téléchargé ne seront pas conservées tout.</span><span class="sxs-lookup"><span data-stu-id="a0eac-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 30 MB, the uploaded file data will not be retained at all.</span></span> <span data-ttu-id="a0eac-114">La valeur par défaut MaxSendSize est de 150 Mo, mais les administrateurs de clients peuvent configurer MaxSendSize pour être aussi faible que 1 Mo.</span><span class="sxs-lookup"><span data-stu-id="a0eac-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="a0eac-115">Boîtes aux lettres qui ne sont pas en attente n’auront pas toutes les données réunion enregistrées.</span><span class="sxs-lookup"><span data-stu-id="a0eac-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="a0eac-116">Par exemple, dans une réunion de trois personnes dans, dont les boîtes aux lettres de deux participants sont marqués pour la conservation des données de la réunion sont enregistrées dans les boîtes aux lettres de ces deux participants, mais pas la boîte aux lettres du troisième participant, boîte aux lettres n’est pas sur Maintenez.</span><span class="sxs-lookup"><span data-stu-id="a0eac-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a0eac-117">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a0eac-117">Related topics</span></span>
[<span data-ttu-id="a0eac-118">Créer des stratégies d'accès externe personnalisées</span><span class="sxs-lookup"><span data-stu-id="a0eac-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="a0eac-119">Bloquer les transferts de fichiers de point à point</span><span class="sxs-lookup"><span data-stu-id="a0eac-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="a0eac-120">Configurer les stratégies client pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a0eac-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="a0eac-121">Configurer des stratégies de conférence dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="a0eac-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 