---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Vous définissez un nouveau serveur Edge ou pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Vous pouvez choisir parmi les options suivantes :'
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835514"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="16df4-104">Ajouter des options de serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="16df4-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="16df4-105">Vous définissez un nouveau serveur Edge ou pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="16df4-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="16df4-106">Vous pouvez choisir parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="16df4-106">The options that you can choose are:</span></span>

- <span data-ttu-id="16df4-107">**Utiliser un seul nom de domaine complet (FQDN) et une seule adresse IP** : activez cette case à cocher afin d’utiliser une seule adresse IPv4 ou IPv6 (si vous choisissez d’utiliser IPv4 et IPv6, vous devrez définir chacun des types d’adresse IP) et le nom de domaine complet (FQDN) des interfaces Edge externes.</span><span class="sxs-lookup"><span data-stu-id="16df4-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="16df4-108">Si vous choisissez cette option, vous n’utiliserez qu’une adresse IP, ou une adresse IPv4 et une adresse IPv6, mais vous devez attribuer des numéros de port différents à chaque interface Edge.</span><span class="sxs-lookup"><span data-stu-id="16df4-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="16df4-109">**Activer la fédération pour ce pool Edge (port 5061)**  : activez cette case à cocher si vous avez l’intention de fédérer avec d’autres fournisseurs, fédérations SIP ou offres hébergées utilisant le protocole SIP.</span><span class="sxs-lookup"><span data-stu-id="16df4-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="16df4-110">L’adresse IP externe de ce **pool edge** est traduite par NAT : cochez cette case si vous utilisez des adresses IP privées pour les interfaces externes Edge et fournissez un périphérique de traduction d’adresses réseau (NAT) pour placer le serveur Edge ou le pool edge logiquement derrière.</span><span class="sxs-lookup"><span data-stu-id="16df4-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="16df4-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16df4-111">See also</span></span>

[<span data-ttu-id="16df4-112">Planification de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="16df4-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="16df4-113">Déploiement de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="16df4-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
