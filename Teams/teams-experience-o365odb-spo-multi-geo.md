---
title: Expertise dans un environnement multi-géographiques Microsoft 365
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
description: Dans cet article, vous allez découvrir comment utiliser teams dans un environnement multi-géographiques Microsoft 365.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757749"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="c698f-103">Découverte d’équipes dans une location Microsoft 365 avec plusieurs géo-géographiques</span><span class="sxs-lookup"><span data-stu-id="c698f-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="c698f-104">Microsoft teams est un logiciel de discussion de groupe, concentrateur pour le travail en équipe dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c698f-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="c698f-105">Ce service est fourni par le service groupes Microsoft 365 avec SharePoint et OneDrive pour son utilisation des fichiers.</span><span class="sxs-lookup"><span data-stu-id="c698f-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="c698f-106">Dans une organisation à plusieurs zones géographiques dans laquelle le locataire est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’interface de fichiers sous-jacente est compatible avec la géolocalisation, de sorte que l’interface de partage de fichiers est également compatible avec plusieurs géo.</span><span class="sxs-lookup"><span data-stu-id="c698f-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="c698f-107">Cela permet aux équipes de surfacer les fichiers hébergés sur plusieurs emplacements géographiques dans leur interface de fichiers natives.</span><span class="sxs-lookup"><span data-stu-id="c698f-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="c698f-108">Par exemple, dans le cadre d’une location de contoso avec l’Europe comme un satellite de géo et d’Amérique du Nord au sein de la région centrale, un utilisateur de satellite européen verra ses fichiers OneDrive dans le volet gauche, même si les fichiers sont hébergés dans l’emplacement des données Europe et si les États-Unis sont l’emplacement central du client.</span><span class="sxs-lookup"><span data-stu-id="c698f-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c698f-109">Par ailleurs, l’utilisateur peut accéder aux derniers fichiers utilisés dans la Blade d’affichage récente.</span><span class="sxs-lookup"><span data-stu-id="c698f-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="c698f-110">Les fichiers récents peuvent inclure des fichiers partagés à partir des utilisateurs situés dans d’autres emplacements géographiques.</span><span class="sxs-lookup"><span data-stu-id="c698f-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="c698f-111">Le site SharePoint d’une équipe donnée prend également en charge la géolocalisation.</span><span class="sxs-lookup"><span data-stu-id="c698f-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="c698f-112">Autrement dit, si un utilisateur de satellite européen crée une équipe, le site SharePoint correspondant sera créé dans l’emplacement européen et les fichiers associés à cette équipe seront conservés à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="c698f-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="c698f-113">Toute expérience ultérieure, telle que le téléchargement d’un nouveau fichier ou la modification du fichier, sera stockée dans cet emplacement européen, afin de garantir la conservation des données pour ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="c698f-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="c698f-114">Remarque : les conversations dans les conversations et les notes de messagerie instantanée de réunion au sein de l’interface de Teams ne sont pas sensibilisées au sein de l’équipe et ne sont pas tenues uniquement à l’intérieur de l’emplacement central de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c698f-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="c698f-115">Pour plus d’informations sur la fonction de géolocalisation, voir [fonctionnalités de Microsoft multi-géo](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="c698f-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
