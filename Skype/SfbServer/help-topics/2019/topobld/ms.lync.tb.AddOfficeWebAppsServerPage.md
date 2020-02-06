---
title: Ajouter Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'L’Assistant définir un nouveau serveur Office Web Apps définit un nouveau serveur Office Web Apps dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: 9ca5be070d4a79a2cb011a1e91bd0613f21e8700
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798451"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="82b76-104">Ajouter Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="82b76-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="82b76-105">L’Assistant **définir un nouveau serveur Office Web Apps** définit un nouveau serveur Office Web Apps dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="82b76-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="82b76-106">Vous devez fournir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="82b76-106">You fill in the following information:</span></span>

 <span data-ttu-id="82b76-107">Nom de domaine **complet (FQDN) Office Web Apps Server**: tapez le nom de domaine complet du serveur qui héberge le serveur Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="82b76-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="82b76-108">**URL de découverte d’Office Web Apps Server**: taper l’URL (Uniform Resource Locator) complète du serveur Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="82b76-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="82b76-109">Le comportement par défaut de l' **URL de découverte d’Office Web Apps Server** consiste à créer l’URL en fonction du nom de domaine complet (FQDN) du `https://<FQDN of the Office Web Apps Server/hosting/discovery` serveur Office Web Apps au format :.</span><span class="sxs-lookup"><span data-stu-id="82b76-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="82b76-110">Dans la plupart des cas, vous ne devrez pas modifier le format par défaut.</span><span class="sxs-lookup"><span data-stu-id="82b76-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="82b76-111">Il est possible que vous deviez modifier le format par défaut dans l’éventualité où Office Web Apps Server et l’URL de découverte du serveur Office Web Apps doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="82b76-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="82b76-112">Par exemple, votre serveur Office Web Apps est placé dans le réseau de périmètre et possède une autre URL en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="82b76-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="82b76-113">**Office Web Apps Server est déployé sur un réseau externe (par exemple, périmètre/Internet)**: activez la case à cocher si votre serveur Office Web Apps est placé à l’extérieur de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou une autre zone réseau qui n’est pas identique à votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="82b76-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="82b76-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82b76-114">See also</span></span>

[<span data-ttu-id="82b76-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="82b76-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
