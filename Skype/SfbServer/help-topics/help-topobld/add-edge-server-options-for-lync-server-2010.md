---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Vous définissez un nouveau serveur Edge ou une nouvelle grappe de périphériques et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Les options disponibles sont les suivantes :'
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820986"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="a9d3f-104">Ajouter des options de serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9d3f-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="a9d3f-105">Vous définissez un nouveau serveur Edge ou une nouvelle grappe de périphériques et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="a9d3f-106">Les options disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9d3f-106">The options that you can choose are:</span></span>

- <span data-ttu-id="a9d3f-107">**Utiliser un nom de domaine complet et une adresse IP uniques**: activez la case à cocher pour utiliser un seul protocole IPv4 ou IPv6 (si vous choisissez d’utiliser IPv4 et IPv6, vous devez définir une de chaque adresse IP type) et un nom de domaine complet (FQDN) pour les interfaces Edge externes.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a9d3f-108">Si vous choisissez cette option, vous n’utiliserez qu’une seule adresse IP, une seule IPv4 et une autre, mais vous devez attribuer des numéros de port différents à chaque interface latérale.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="a9d3f-109">**Activer la Fédération (port 5061)**: activez cette case à cocher si vous êtes fédérer avec d’autres fédérations SIP, fournisseurs ou produits hébergés utilisant le protocole SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="a9d3f-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="a9d3f-110">**L’adresse IP externe de ce pool Edge est traduite par tar**: activez cette case à cocher si vous utilisez des adresses IP privées pour les interfaces externes latérales et que vous fournissez un périphérique de traduction d’adresses réseau (NAT) pour placer le serveur de périphérie ou le pool de périphérie de manière logique.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9d3f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9d3f-111">See also</span></span>

[<span data-ttu-id="a9d3f-112">Planification de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="a9d3f-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="a9d3f-113">Déploiement de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="a9d3f-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
