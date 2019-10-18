---
title: Mener une recherche eDiscovery de contenu dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Découvrez les actions à entreprendre et le moment opportun pour mener une recherche eDiscovery, par exemple lorsque vous devez soumettre toutes les informations stockées électroniquement dans le cadre d'une procédure juridique.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564031"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="276bf-103">Mener une recherche eDiscovery de contenu dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="276bf-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="276bf-104">Les grandes entreprises sont souvent exposées à des actions juridiques à forte pénalité qui demandent la soumission de toutes les informations stockées électroniquement (ESI).</span><span class="sxs-lookup"><span data-stu-id="276bf-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="276bf-p101">Toutes les équipes 1:1 ou les discussions de groupe sont journalisées dans les boîtes aux lettres des utilisateurs correspondants, et tous les messages des canaux sont journalisés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés sont décrits dans la fonctionnalité eDiscovery pour SharePoint Online et OneDrive entreprise.</span><span class="sxs-lookup"><span data-stu-id="276bf-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="276bf-107">Pour effectuer une analyse eDiscovery avec le contenu Microsoft Teams, reportez-vous à l’étape 1 de [ce](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) lien.</span><span class="sxs-lookup"><span data-stu-id="276bf-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="276bf-108">Les données de Microsoft teams s’affichent sous forme de messages instantanés ou de conversations dans la sortie d’exportation eDiscovery d’Excel et vous pouvez les monter. PST dans Outlook pour afficher ces messages après l’exportation.</span><span class="sxs-lookup"><span data-stu-id="276bf-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="276bf-p102">Lors du montage du. PST pour l’équipe, Notez que toutes les conversations sont conservées dans le dossier de discussion d’équipe sous historique des conversations. Le titre du message s’aligne sur l’équipe et le canal. À partir de la consultation de l’image ci-dessous, vous pouvez voir ce message de Bob qui a affiché le canal Project 7 de l’équipe des spécifications de fabrication.</span><span class="sxs-lookup"><span data-stu-id="276bf-p102">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History. The title of the message aligns to Team and Channel. From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Capture d’écran d’un dossier de discussion d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="276bf-113">Pour afficher les conversations privées dans la boîte aux lettres d'un utilisateur, accédez au dossier Conversation de l'équipe sous l'historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="276bf-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="276bf-114">Découverte électronique des discussions entre invités</span><span class="sxs-lookup"><span data-stu-id="276bf-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="276bf-115">Sans boîte aux lettres, les discussions invitées invitées (1xNs dans lesquelles il n’y a pas d’utilisateurs privés) ne sont pas indexées et ne sont pas incluses dans eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="276bf-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="276bf-116">Pour faciliter l’eDiscovery pour les discussions invitées, une boîte aux lettres Cloud (ou une boîte aux lettres fantôme) est créée pour le stockage des données 1xN.</span><span class="sxs-lookup"><span data-stu-id="276bf-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="276bf-117">Une fois que les données de chat de l’équipe sont stockées dans la boîte aux lettres dans le Cloud, celles-ci sont indexées pour la découverte électronique et la recherche de contenu de conformité.</span><span class="sxs-lookup"><span data-stu-id="276bf-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="276bf-118">L’illustration suivante décrit le fonctionnement de eDiscovery pour les discussions invitées dans lesquelles il n’y a pas de boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="276bf-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![invité-à-invité-discussions-avec non-boîte aux lettres](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
