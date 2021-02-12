---
title: Expérience Teams dans un environnement Multi-Geo-enabled Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Cet article présente l’utilisation de Teams dans un environnement Microsoft 365 multigéogé.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122244"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="d090e-103">Expérience Teams dans un client Microsoft 365 Multi-Geo-enabled</span><span class="sxs-lookup"><span data-stu-id="d090e-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="d090e-104">Microsoft Teams est un logiciel de conversation de groupe, qui est le hub pour le travail d’équipe dans Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="d090e-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="d090e-105">Il est optimisé par le service Groupes Microsoft 365 ainsi que par SharePoint Online et OneDrive Entreprise pour son expérience des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d090e-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="d090e-106">Dans un client OneDrive Entreprise/SharePoint Online multigéogé, dans lequel le client est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’expérience des fichiers sous-jacents est géographiquement multiple, de sorte que l’expérience Teams avec la collaboration de fichiers est également géographiquement multiple.</span><span class="sxs-lookup"><span data-stu-id="d090e-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="d090e-107">Cette fonctionnalité est une fonctionnalité de pointe pour Teams pour surface des fichiers hébergés dans plusieurs régions géographiques dans son expérience de fichiers natifs.</span><span class="sxs-lookup"><span data-stu-id="d090e-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="d090e-108">Cela inclut également les fichiers OneNote et Wiki.</span><span class="sxs-lookup"><span data-stu-id="d090e-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="d090e-109">Par exemple, dans un client Contoso dont l’Europe est une région géographique satellite et l’Amérique  du Nord comme région centrale, un utilisateur satellitaire européen verra ses fichiers OneDrive sous l’onglet Fichiers dans le volet gauche, bien que les fichiers soient hébergés à l’emplacement de données d’Europe et que les États-Unis soient l’emplacement central du locataire.</span><span class="sxs-lookup"><span data-stu-id="d090e-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="d090e-110">L’utilisateur peut également accéder aux derniers fichiers utilisés sous le lame **d’affichage** Récent.</span><span class="sxs-lookup"><span data-stu-id="d090e-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="d090e-111">Les fichiers récents peuvent inclure des fichiers partagés par des utilisateurs à d’autres emplacements géographiques.</span><span class="sxs-lookup"><span data-stu-id="d090e-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="d090e-112">Le site SharePoint d’une équipe donnée est également géographiquement géographique.</span><span class="sxs-lookup"><span data-stu-id="d090e-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="d090e-113">Autrement dit, si un utilisateur satellitaire européen crée une équipe, le site SharePoint correspondant est créé en Europe.</span><span class="sxs-lookup"><span data-stu-id="d090e-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="d090e-114">Les fichiers associés à cette équipe sont conservés au repos à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="d090e-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="d090e-115">Les expériences suivantes, telles que le téléchargement d’un nouveau fichier ou sa modification, seront stockées dans cet emplacement européen, ce qui conserve la promesse de résidence de données pour ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="d090e-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="d090e-116">Étant donné qu’un client multigé géographique est un client global unique, durant la mention @, les utilisateurs satellitaires pourront voir leurs collègues du monde entier, où qu’ils se trouveront.</span><span class="sxs-lookup"><span data-stu-id="d090e-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="d090e-117">Les conversations dans les conversations, les messages de canaux et les notes/conversations de réunion par messagerie instantanée au sein de l’expérience Teams ne sont pas géographiquement multiples et sont toutes conservées uniquement dans l’emplacement central du client.</span><span class="sxs-lookup"><span data-stu-id="d090e-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="d090e-118">En règle générale, les conversations de conversation ne s’appliquent pas aux besoins de résidence de données.</span><span class="sxs-lookup"><span data-stu-id="d090e-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="d090e-119">Pour plus d’informations, [voir Localisation des données dans Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d090e-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="d090e-120">Pour plus d’informations sur Multi-Geo, consultez la [page Microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="d090e-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
