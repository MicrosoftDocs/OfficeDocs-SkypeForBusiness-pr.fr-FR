---
title: Accès aux équipes dans une 365 ou Office 365 OneDrive et SharePoint Online avec une location autonome multigéo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Dans cet article, vous allez découvrir comment utiliser teams dans une location Microsoft 365 ou Office 365 OneDrive et SharePoint Online multi-géo-géo.
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
ms.openlocfilehash: 4e754177de6f08476c9160254f2334f6f3ac18d3
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903139"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="c6b32-103">Accès aux équipes dans une 365 ou Office 365 OneDrive et SharePoint Online avec une location autonome multigéo</span><span class="sxs-lookup"><span data-stu-id="c6b32-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="c6b32-104">Microsoft teams est un logiciel de discussion de groupe, concentrateur pour le travail en équipe dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6b32-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="c6b32-105">Ce service est fourni par le service groupes Microsoft 365 avec SharePoint Online et OneDrive entreprise pour son utilisation des fichiers.</span><span class="sxs-lookup"><span data-stu-id="c6b32-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="c6b32-106">Dans un espace de travail de type My-géo de OneDrive entreprise/SharePoint Online, dans lequel le locataire est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’interface de fichiers sous-jacente est compatible avec plusieurs géo</span><span class="sxs-lookup"><span data-stu-id="c6b32-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="c6b32-107">Il s’agit d’une fonctionnalité de pointe clé pour les équipes de fichiers en surface hébergées sur plusieurs GEOS dans l’interface des fichiers natifs.</span><span class="sxs-lookup"><span data-stu-id="c6b32-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="c6b32-108">Par exemple, dans le cadre d’une location de contoso avec l’Europe comme un satellite de géo et d’Amérique du Nord au sein de la région centrale, un utilisateur de satellite européen verra ses fichiers OneDrive dans le volet gauche, même si les fichiers sont hébergés dans l’emplacement des données Europe et si les États-Unis sont l’emplacement central du client.</span><span class="sxs-lookup"><span data-stu-id="c6b32-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c6b32-109">Par ailleurs, l’utilisateur peut accéder aux derniers fichiers utilisés dans la Blade d’affichage récente.</span><span class="sxs-lookup"><span data-stu-id="c6b32-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="c6b32-110">Les fichiers récents peuvent inclure des fichiers partagés avec l’utilisateur d’autres utilisateurs dans d’autres GEOS et peuvent être masterisés dans d’autres emplacements géographiques dans lesquels le locataire est étendu.</span><span class="sxs-lookup"><span data-stu-id="c6b32-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="c6b32-111">Le site de groupe d’une équipe donné est également compatible avec plusieurs géo.</span><span class="sxs-lookup"><span data-stu-id="c6b32-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="c6b32-112">Autrement dit, si un utilisateur de satellite européen crée une équipe, le site des groupes correspondant est créé dans l’emplacement européen et les fichiers associés à ce groupe d’équipe seront conservés à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="c6b32-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="c6b32-113">Toute expérience subséquente, telle que le téléchargement d’un nouveau fichier ou la modification du fichier, sera ciblée vers cet emplacement européen, afin de garantir la conservation des données pour ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="c6b32-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="c6b32-114">C’est tout ce qu’il est possible de faire en sorte que les groupes Microsoft 365 de la Fondation sous-jacente deviennent compatibles avec plusieurs géo.</span><span class="sxs-lookup"><span data-stu-id="c6b32-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="c6b32-115">Dans la mesure où une location multipoint est un client global unique, au cours des @ mentions, les utilisateurs satellites pourront voir leurs collègues du monde entier, quel que soit l’endroit où ils se trouvent.</span><span class="sxs-lookup"><span data-stu-id="c6b32-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="c6b32-116">Remarque : les conversations dans les conversations et les notes de messagerie instantanée de réunion au sein de l’interface de Teams ne prennent pas en charge la géolocalisation et ne se trouvent qu’à l’intérieur de l’emplacement central du client.</span><span class="sxs-lookup"><span data-stu-id="c6b32-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="c6b32-117">En règle générale, les conversations par messagerie instantanée ne sont pas appliquées aux besoins de résidence des données.</span><span class="sxs-lookup"><span data-stu-id="c6b32-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="c6b32-118">Pour plus d’informations sur Office 365 multi-géo, voir la [page de capacités de Microsoft multi-géo](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="c6b32-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>