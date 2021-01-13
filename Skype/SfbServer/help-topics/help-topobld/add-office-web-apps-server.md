---
title: Ajouter Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'L’Assistant Définir un nouveau serveur Office Web Apps Server définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828594"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="733a5-104">Ajouter Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="733a5-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="733a5-105">L’Assistant Définir **un nouveau serveur Office Web Apps Server** définit un nouveau serveur Office Web Apps Server dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="733a5-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="733a5-106">Vous devez fournir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="733a5-106">You fill in the following information:</span></span>

 <span data-ttu-id="733a5-107">Nom de domaine complet **d’Office Web Apps Server**: tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="733a5-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="733a5-108">URL de découverte **d’Office Web Apps Server**: tapez l’URL (uniform resource locator) complète du serveur Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="733a5-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="733a5-109">Le comportement par défaut de l’URL de découverte **d’Office Web Apps Server** consiste à créer l’URL en fonction du nom de domaine général (FQDN) du serveur Office Web Apps server au format `https://<FQDN of the Office Web Apps Server/hosting/discovery` :</span><span class="sxs-lookup"><span data-stu-id="733a5-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="733a5-110">Dans la plupart des cas, vous ne devrez pas modifier le format par défaut.</span><span class="sxs-lookup"><span data-stu-id="733a5-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="733a5-111">Vous devrez peut-être modifier le format par défaut si le serveur Office Web Apps Server et l’URL de découverte Office Web Apps Server doivent être différents.</span><span class="sxs-lookup"><span data-stu-id="733a5-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="733a5-112">Par exemple, votre serveur Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="733a5-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="733a5-113">Office Web Apps Server est déployé dans un réseau externe **(périmètre/Internet)**: cochez la case si votre serveur Office Web Apps Server est placé en dehors de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou toute autre zone réseau qui n’est pas la même que votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="733a5-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="733a5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="733a5-114">See also</span></span>

[<span data-ttu-id="733a5-115">Composants et topologies pour les conférences</span><span class="sxs-lookup"><span data-stu-id="733a5-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
