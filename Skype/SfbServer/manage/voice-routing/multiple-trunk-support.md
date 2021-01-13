---
title: Prise en charge de plusieurs branches dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La fonctionnalité Skype Entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826224"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="a673e-105">Prise en charge de plusieurs branches dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a673e-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="a673e-106">La fonctionnalité Skype Entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="a673e-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="a673e-107">Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a673e-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="a673e-108">Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).</span><span class="sxs-lookup"><span data-stu-id="a673e-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="a673e-109">Pour affecter ou supprimer une trunk dans Skype Entreprise Server, vous devez d’abord définir une trunk dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a673e-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="a673e-110">Une trunk se compose de l’association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="a673e-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="a673e-111">Pour configurer plusieurs trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a673e-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="a673e-112">Cela offre une résilience supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="a673e-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="a673e-113">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="a673e-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="a673e-114">Pour associer une liaison à un itinéraire, vous définissez un nom simple pour la liaison dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="a673e-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="a673e-115">Ce nom simple est utilisé comme nom de la trunk dans le Panneau de contrôle Skype Entreprise Server, où les liaisons peuvent être associées à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="a673e-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="a673e-116">Le nom de la simple passerelle est utilisé comme nom de passerelle à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a673e-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="a673e-117">L’administrateur doit sélectionner une trunk par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a673e-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="a673e-118">Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="a673e-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="a673e-119">Spécifiez la passerelle par défaut pour le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a673e-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="a673e-120">Le diagramme suivant illustre les multiples branches définies pour chaque serveur de médiation et passerelle.</span><span class="sxs-lookup"><span data-stu-id="a673e-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Affectations de plusieurs branches](../../media/multiple-trunk-assignments.jpg)
