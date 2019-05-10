---
title: Emplacement des données dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/09/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Découvrez où les données sont stockées dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 369351b818506525cf750d7e5d767b3bdbf97906
ms.sourcegitcommit: ca7a22da082ac5336f31ffd76f3d4aef6c76285b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868839"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="4ea26-103">Emplacement des données dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ea26-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="4ea26-104">Les données dans Teams résident dans la région géographique associée à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ea26-104">Data in Teams resides in the geographic region associated with your Office 365 tenant.</span></span> <span data-ttu-id="4ea26-105">Actuellement, les équipes prend en charge les régions Australie, Canada, France, Inde, au Japon, Royaume-Uni, Amérique, APAC et EMEA.</span><span class="sxs-lookup"><span data-stu-id="4ea26-105">Currently, Teams supports the Australia, Canada, France, India, Japan, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4ea26-106">Équipes offre actuellement de délégation des données en Australie, Canada, France, Inde, au Japon et au Royaume-Uni pour les nouveaux clients uniquement.</span><span class="sxs-lookup"><span data-stu-id="4ea26-106">Teams currently offers data residency in Australia, Canada, France, India, Japan, and the United Kingdom for new tenants only.</span></span> <span data-ttu-id="4ea26-107">Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client.</span><span class="sxs-lookup"><span data-stu-id="4ea26-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="4ea26-108">Clients existants d’Australie, Inde et Japon continuera à leurs données équipes stocké dans la région APAC.</span><span class="sxs-lookup"><span data-stu-id="4ea26-108">Existing tenants from Australia, India, and Japan will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="4ea26-109">Clients existants au Canada continuera à leurs données stockées en Amérique.</span><span class="sxs-lookup"><span data-stu-id="4ea26-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="4ea26-110">France et Royaume-Uni auront leurs données stockées dans la région EMEA.</span><span class="sxs-lookup"><span data-stu-id="4ea26-110">France and the United Kingdom will have their data stored in the EMEA region.</span></span>

<span data-ttu-id="4ea26-111">Pour en savoir plus sur le lancement de la délégation de données Inde et Royaume-Uni pour les équipes, lisez le billet de blog de Ansuman Acharya, [que les équipes Microsoft lance la délégation données Inde, autres zones géographiques bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827).</span><span class="sxs-lookup"><span data-stu-id="4ea26-111">To learn more about the launch of India and United Kingdom data residency for Teams, read Ansuman Acharya's blog post, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827).</span></span> 

<span data-ttu-id="4ea26-112">Pour plus d’informations sur la délégation des données Canada pour les équipes, lisez le billet de blog de Varun Sagar [équipes Microsoft lance la délégation données Canada, Australie et Japon bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178).</span><span class="sxs-lookup"><span data-stu-id="4ea26-112">For more information on Canada data residency for Teams, read Varun Sagar's blog post, [Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178).</span></span> 

<span data-ttu-id="4ea26-113">Pour en savoir plus sur le lancement de la délégation de données Australie et Japon pour les équipes, lisez le billet de blog de Varun Sagar [Microsoft équipes lance Australie et Japon données délégation](https://go.microsoft.com/fwlink/?linkid=867773).</span><span class="sxs-lookup"><span data-stu-id="4ea26-113">To learn more about the launch of Australia and Japan data residency for Teams, read Varun Sagar's blog post, [Microsoft Teams Launches Australia and Japan Data Residency](https://go.microsoft.com/fwlink/?linkid=867773).</span></span> 

<span data-ttu-id="4ea26-114">Pour en savoir plus sur le lancement de la délégation de données France pour les équipes, lisez le billet de blog de Varun Sagar, [Les équipes Microsoft lance la délégation données France](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).</span><span class="sxs-lookup"><span data-stu-id="4ea26-114">To learn more about the launch of France data residency for Teams, read Varun Sagar's blog post, [Microsoft Teams Launches France Data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).</span></span> 

<span data-ttu-id="4ea26-115">Pour afficher la zone contient des données pour votre client, accédez au [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home) > **paramètres** > **profil d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="4ea26-115">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="4ea26-116">Défilez jusqu’à la section **Emplacement des données**.</span><span class="sxs-lookup"><span data-stu-id="4ea26-116">Scroll down to **Data location**.</span></span> 

![Capture d’écran de la table de magasin de données, y compris les équipes, dans le centre d’administration d’Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

