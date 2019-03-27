---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Vous définissez un nouveau serveur de périphérie ou un pool de serveurs Edge et sont présentées avec la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Les options que vous pouvez choisir sont les suivants :'
ms.openlocfilehash: 57c3916b1a43812c1f647f425fc9df65f99cff35
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897457"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="89eae-104">Ajouter des options de serveur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="89eae-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="89eae-105">Vous définissez un nouveau serveur de périphérie ou un pool de serveurs Edge et sont présentées avec la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool.</span><span class="sxs-lookup"><span data-stu-id="89eae-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="89eae-106">Les options que vous pouvez choisir sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="89eae-106">The options that you can choose are:</span></span>

- <span data-ttu-id="89eae-107">**Utiliser une seule adresse IP et le nom de domaine complet**: activez la case à cocher Utiliser un seul IPv4 ou IPv6 (si vous choisissez d’utiliser à la fois IPv4 et IPv6, vous devez en définir une option de chaque type d’adresse IP) adresse et le nom de domaine complet (FQDN) pour l’externe Edge interfaces.</span><span class="sxs-lookup"><span data-stu-id="89eae-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="89eae-108">Si vous choisissez cette option, vous allez utiliser qu’une seule adresse IP, ou une adresse IPv4 et une adresse IPv6, mais vous devez affecter des numéros de port différents à chaque interface Edge.</span><span class="sxs-lookup"><span data-stu-id="89eae-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="89eae-109">**Activer la fédération (port 5061)**: Activez cette case à cocher si vous l’intention de fédérer avec d’autres offres hébergées utilisant le protocole d’ouverture de session (SIP), fournisseurs ou fédérations SIP.</span><span class="sxs-lookup"><span data-stu-id="89eae-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="89eae-110">**L’adresse IP externe de ce pool Edge est traduit par NAT**: Activez cette case à cocher si vous utilisez des adresses IP privées pour les interfaces externes Edge et fournissez un périphérique network address translation (NAT) pour placer le serveur Edge ou pool Edge logiquement derrière.</span><span class="sxs-lookup"><span data-stu-id="89eae-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="89eae-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89eae-111">See also</span></span>

[<span data-ttu-id="89eae-112">Planification de l’accès utilisateur externe</span><span class="sxs-lookup"><span data-stu-id="89eae-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="89eae-113">Déploiement de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="89eae-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
