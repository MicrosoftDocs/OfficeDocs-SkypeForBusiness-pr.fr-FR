---
title: Mener une recherche eDiscovery de contenu dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
search.appverid: MET150
description: Découvrez les actions à entreprendre et le moment opportun pour mener une recherche eDiscovery, par exemple lorsque vous devez soumettre toutes les informations stockées électroniquement dans le cadre d'une procédure juridique.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5d5da1ea0fc098a951e65cbb31acd5c7a54974c
ms.sourcegitcommit: 6a2466a3bf4cc2390a9be40dea0736174ef180e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "23957165"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="f1afa-103">Mener une recherche eDiscovery de contenu dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1afa-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="f1afa-104">Grandes entreprises sont souvent exposés aux poursuites judiciaires pénalité considérable qui exigent l’envoi de tous les électroniquement stockées informations (ESI).</span><span class="sxs-lookup"><span data-stu-id="f1afa-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="f1afa-p101">Toutes les équipes 1:1 ou les salles de conversation de groupe sont journalisés via aux boîtes aux lettres des utilisateurs respectifs, et tous les messages de canal sont journalisés par le biais de la boîte aux lettres de groupe représentant l’équipe. Fichiers téléchargés sont couverts par la fonctionnalité eDiscovery pour SharePoint Online et OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="f1afa-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="f1afa-107">Pour effectuer une enquête eDiscovery avec un contenu Teams Microsoft, consultez l’étape 1 de [ce](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) lien.</span><span class="sxs-lookup"><span data-stu-id="f1afa-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="f1afa-108">Données Microsoft Teams apparaît sous forme de messagerie instantanée ou sortie d’exportation de Conversations dans la découverte électronique Excel, et vous pouvez monter le. Exportation de publication PST dans Outlook pour afficher ces messages.</span><span class="sxs-lookup"><span data-stu-id="f1afa-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="f1afa-109">Lorsque vous montez la. PST de l’équipe, notez que toutes les conversations sont conservées dans le dossier de l’équipe conversation sous l’historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="f1afa-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="f1afa-110">Le titre du message s’aligne à l’équipe et de canal.</span><span class="sxs-lookup"><span data-stu-id="f1afa-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="f1afa-111">De la révision de l’image ci-dessous, vous pouvez voir ce message de Bob qui sollicités le canal 7 du projet de l’équipe de spécifications de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f1afa-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Capture d’écran d’un dossier de conversation de l’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="f1afa-113">Pour afficher les conversations privées dans la boîte aux lettres d'un utilisateur, accédez au dossier Conversation de l'équipe sous l'historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="f1afa-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="f1afa-114">Découverte des conversations d’invité à invité</span><span class="sxs-lookup"><span data-stu-id="f1afa-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="f1afa-115">Sans une boîte aux lettres, conversations invité-invité (conversations 1xN dans laquelle il n’existe aucun utilisateur client personnel) ne doit pas être indexées et ne serait par conséquent, pas être incluses dans la découverte électronique.</span><span class="sxs-lookup"><span data-stu-id="f1afa-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="f1afa-116">Pour faciliter la découverte électronique pour une conversation invité-invité, une boîte aux lettres en nuage (ou fantôme) est créé pour stocker les données 1xN.</span><span class="sxs-lookup"><span data-stu-id="f1afa-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="f1afa-117">Une fois que les données de conversation d’équipes sont stockées dans la boîte aux lettres en nuage, il est indexé pour la recherche de contenu eDiscovery et de conformité.</span><span class="sxs-lookup"><span data-stu-id="f1afa-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="f1afa-118">L’illustration suivante montre le fonctionne de découverte électronique pour les conversations invité-invité dans laquelle il n’existe pas une boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="f1afa-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![guest-to-guest-chats-with-no-Mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
