---
title: Prise en charge de plusieurs Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816944"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="03b2c-105">Prise en charge de plusieurs Trunks dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="03b2c-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="03b2c-106">La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="03b2c-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="03b2c-107">Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="03b2c-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="03b2c-108">Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).</span><span class="sxs-lookup"><span data-stu-id="03b2c-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="03b2c-109">Pour attribuer ou supprimer un Trunk dans Skype entreprise Server, vous devez commencer par définir un Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="03b2c-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="03b2c-110">Un Trunk est composé de l’Association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="03b2c-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="03b2c-111">Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="03b2c-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="03b2c-112">Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="03b2c-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="03b2c-113">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="03b2c-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="03b2c-114">Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="03b2c-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="03b2c-115">Ce nom simple sert de nom de Trunk dans le panneau de configuration Skype entreprise Server, où les Trunks peuvent être associés à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="03b2c-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="03b2c-116">Le nom simple de Trunk est utilisé comme nom de la passerelle de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03b2c-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="03b2c-117">L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="03b2c-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="03b2c-118">Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="03b2c-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="03b2c-119">Spécifiez la passerelle par défaut du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="03b2c-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="03b2c-120">Le diagramme suivant illustre les différentes liaisons définies pour chaque serveur et passerelle de médiation.</span><span class="sxs-lookup"><span data-stu-id="03b2c-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Attributions de plusieurs lignes](../../media/multiple-trunk-assignments.jpg)
