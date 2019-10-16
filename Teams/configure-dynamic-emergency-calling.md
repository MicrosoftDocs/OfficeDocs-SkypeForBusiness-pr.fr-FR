---
title: Configurer les appels d’urgence dynamiques
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurer les appels d’urgence dynamiques
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516931"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="8b262-103">Planifier et configurer les appels d’urgence dynamiques pour les offres d’appels</span><span class="sxs-lookup"><span data-stu-id="8b262-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="8b262-104">Les appels d’urgence dynamiques pour les plans d’appel Microsoft offrent la possibilité de configurer et d’acheminer les appels d’urgence en fonction de l’emplacement actuel du client Teams.</span><span class="sxs-lookup"><span data-stu-id="8b262-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="8b262-105">La possibilité de procéder au routage automatique vers le point d’accès à la sécurité publique approprié (PSAPI) ou de notifier le personnel de votre support technique dépend du pays d’utilisation de l’utilisateur de teams.</span><span class="sxs-lookup"><span data-stu-id="8b262-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="8b262-106">Les appels d’urgence dynamiques ne sont actuellement disponibles qu’aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="8b262-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="8b262-107">La notification du support technique est toutefois prise en charge entre les pays.</span><span class="sxs-lookup"><span data-stu-id="8b262-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="8b262-108">**Aux États-Unis**, vous pouvez configurer le routage des appels d’urgence dynamiques comme suit :</span><span class="sxs-lookup"><span data-stu-id="8b262-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="8b262-109">Si un client teams se trouve dans un emplacement d’urgence dynamique défini par un client, les appels d’urgence de ce client sont automatiquement routés vers le PSAPI qui dessert cet emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="8b262-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="8b262-110">Si un client Teams ne se trouve pas dans un emplacement d’urgence dynamique défini par le client, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAPI qui dessert cet emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="8b262-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="8b262-111">Vous pouvez configurer les notifications de bureau de sécurité comme suit :</span><span class="sxs-lookup"><span data-stu-id="8b262-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="8b262-112">Si un client teams se trouve sur un site réseau défini par un client, les membres du groupe de sécurité configurés pour ce site en seront avertis.</span><span class="sxs-lookup"><span data-stu-id="8b262-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="8b262-113">Si un client Teams ne se trouve pas sur un site réseau défini par un client, les membres du groupe de sécurité configurés pour l’utilisateur en seront avertis.</span><span class="sxs-lookup"><span data-stu-id="8b262-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="8b262-114">**Hors des États-Unis**, les appels d’urgence sont routés vers le PSAPI qui est mappé au numéro de téléphone attribué à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b262-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="8b262-115">Certains pays, tels que la Grande-Bretagne et le Canada, envoient les appels nationaux avant de transférer l’appelant vers le PSAPI approprié, tandis que d’autres sont routés directement au PSAPI, quel que soit l’endroit où l’utilisateur se trouve actuellement.</span><span class="sxs-lookup"><span data-stu-id="8b262-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="8b262-116">Notez que vous pouvez configurer la notification du support technique dynamique pour tous les utilisateurs du plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="8b262-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="8b262-117">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="8b262-117">Supported clients</span></span>

<span data-ttu-id="8b262-118">Les clients suivants sont actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8b262-118">The following clients are currently supported.</span></span>  <span data-ttu-id="8b262-119">Consultez régulièrement les mises à jour de cette liste.</span><span class="sxs-lookup"><span data-stu-id="8b262-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="8b262-120">Client de bureau teams pour Windows</span><span class="sxs-lookup"><span data-stu-id="8b262-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="8b262-121">Client de bureau teams pour Mac</span><span class="sxs-lookup"><span data-stu-id="8b262-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="8b262-122">Configurer les appels d’urgence dynamiques</span><span class="sxs-lookup"><span data-stu-id="8b262-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="8b262-123">Pour configurer les appels d’urgence dynamiques, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b262-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="8b262-124">Configurer des adresses d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="8b262-125">Configurer les paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="8b262-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="8b262-126">Configurer le service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="8b262-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="8b262-127">Configurer des stratégies d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="8b262-128">Activer les utilisateurs et les sites</span><span class="sxs-lookup"><span data-stu-id="8b262-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="8b262-129">Tester les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="8b262-130">Configurer des adresses d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-130">Configure emergency addresses</span></span>

<span data-ttu-id="8b262-131">Pour prendre en charge le routage automatisé à l’intérieur des États-Unis, vous devez configurer entièrement l’adresse postale qui fait partie des emplacements d’urgence attribués aux identifiants réseau, en incluant les codes géographiques associés.</span><span class="sxs-lookup"><span data-stu-id="8b262-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="8b262-132">(Les adresses d’urgence sans code géo ne peuvent pas être affectées aux identifiants réseau requis pour les emplacements dynamiques).</span><span class="sxs-lookup"><span data-stu-id="8b262-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="8b262-133">Si vous entrez une adresse d’urgence via le centre d’administration de Microsoft Teams, les codes géographiques sont automatiquement inclus si une correspondance est trouvée.</span><span class="sxs-lookup"><span data-stu-id="8b262-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="8b262-134">Si une correspondance est introuvable, vous pouvez créer manuellement une adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="8b262-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="8b262-135">Cela signifie que si une adresse d’urgence existante est configurée pour les appels d’urgence, la même adresse doit être recréée pour inclure les codes géographiques.</span><span class="sxs-lookup"><span data-stu-id="8b262-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="8b262-136">Pour faire la distinction entre les deux adresses, vous devez inclure une autre description.</span><span class="sxs-lookup"><span data-stu-id="8b262-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="8b262-137">La nouvelle adresse de secours peut être affectée aux utilisateurs disposant de l’ancienne adresse.</span><span class="sxs-lookup"><span data-stu-id="8b262-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="8b262-138">Lors de la migration complète, l’ancienne adresse peut être supprimée.</span><span class="sxs-lookup"><span data-stu-id="8b262-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="8b262-139">Pour plus d’informations sur la configuration des adresses d’urgence, voir [que sont les emplacements d’urgence, les lieux et le routage des appels ?](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="8b262-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="8b262-140">Configurer les paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="8b262-140">Configure network settings</span></span>

<span data-ttu-id="8b262-141">Pour le routage des appels d’urgence, vous devez configurer des paramètres réseau pour obtenir dynamiquement les appels d’urgence et, si vous le souhaitez, fournir une configuration dynamique des notifications du Bureau de sécurité.</span><span class="sxs-lookup"><span data-stu-id="8b262-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="8b262-142">L’appel d’urgence souhaité détermine les paramètres réseau qui doivent être configurés.</span><span class="sxs-lookup"><span data-stu-id="8b262-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="8b262-143">Gardez à l’esprit les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b262-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="8b262-144">Les adresses IP de confiance contiennent une collection d’adresses IP externes Internet du réseau d’entreprise, qui sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8b262-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="8b262-145">Les emplacements dynamiques ne sont activés que si l’adresse IP externe de l’utilisateur correspond à une adresse IP dans la collection IP approuvée.</span><span class="sxs-lookup"><span data-stu-id="8b262-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="8b262-146">Une correspondance peut être établie avec des adresses IP IPv4 ou IPv6 et dépend du format des paquets IP envoyés aux paramètres du réseau.</span><span class="sxs-lookup"><span data-stu-id="8b262-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="8b262-147">Une région réseau contient une collection de sites réseau.</span><span class="sxs-lookup"><span data-stu-id="8b262-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="8b262-148">Un site réseau correspond à un emplacement où votre organisation a une valeur physique, par exemple un bureau, un ensemble de bâtiments ou un campus.</span><span class="sxs-lookup"><span data-stu-id="8b262-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="8b262-149">Ces sites sont définis comme un ensemble de sous-réseaux IP.</span><span class="sxs-lookup"><span data-stu-id="8b262-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="8b262-150">Un sous-réseau doit être associé à un site réseau spécifique.</span><span class="sxs-lookup"><span data-stu-id="8b262-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="8b262-151">L’emplacement d’un client est déterminé en fonction du sous-réseau du réseau et du site du réseau associé.</span><span class="sxs-lookup"><span data-stu-id="8b262-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="8b262-152">Pour les utilisateurs de plan d’appel :</span><span class="sxs-lookup"><span data-stu-id="8b262-152">For Calling Plan users:</span></span>

- <span data-ttu-id="8b262-153">Si la configuration dynamique de la notification du support technique est requise, vous devez configurer les adresses IP et les sites réseau approuvés.</span><span class="sxs-lookup"><span data-stu-id="8b262-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="8b262-154">Si seuls les emplacements dynamiques sont requis, vous devez configurer uniquement les adresses IP autorisées.</span><span class="sxs-lookup"><span data-stu-id="8b262-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="8b262-155">Si ce n’est pas le cas, il n’est pas nécessaire de configurer les paramètres réseau.</span><span class="sxs-lookup"><span data-stu-id="8b262-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="8b262-156">Pour plus d’informations, voir [configurer les paramètres réseau pour le routage en fonction de l’emplacement](location-based-routing-configure-network-settings.md), qui décrit comment configurer les paramètres réseau.</span><span class="sxs-lookup"><span data-stu-id="8b262-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="8b262-157">(Les informations contenues dans cet article s’appliquent aux plans d’appel et au routage direct.)</span><span class="sxs-lookup"><span data-stu-id="8b262-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="8b262-158">Configurer le service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="8b262-158">Configure Location Information Service</span></span>

<span data-ttu-id="8b262-159">Un client d’équipes obtient les adresses d’urgence des emplacements d’urgence associés à différents identificateurs de réseau.</span><span class="sxs-lookup"><span data-stu-id="8b262-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="8b262-160">Les sous-réseaux et les points d’accès sans fil sont tous deux pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8b262-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="8b262-161">(La prise en charge du commutateur/port Ethernet est en attente.)</span><span class="sxs-lookup"><span data-stu-id="8b262-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="8b262-162">Pour configurer le service d’information d’emplacement (LIS) avec des identificateurs réseau et des emplacements d’urgence, utilisez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b262-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="8b262-163">Get, Set, Remove-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="8b262-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="8b262-164">Get, Set, Remove-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="8b262-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="8b262-165">Get, Set, Remove-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="8b262-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="8b262-166">Get, Set, Remove-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="8b262-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="8b262-167">Si des sous-réseaux sont utilisés dans le cadre de sites réseau, ils doivent être redéfinis dans le service d’information d’emplacement pour le rendu des emplacements dynamiques.</span><span class="sxs-lookup"><span data-stu-id="8b262-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="8b262-168">Configurer des stratégies d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-168">Configure emergency policies</span></span>

<span data-ttu-id="8b262-169">Les politiques d’urgence déterminent ce qui se produit quand un utilisateur de votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8b262-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="8b262-170">Vous pouvez définir la personne à notifier et la manière dont elle est avertie quand un utilisateur appelle des services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8b262-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="8b262-171">Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement l’assistance technique de votre organisation et leur permettre d’écouter les appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="8b262-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="8b262-172">Pour gérer les stratégies d’urgence, vous pouvez utiliser les applets de CsTeamsEmergencyCalling de stratégie nouveau, Set et Grant-.</span><span class="sxs-lookup"><span data-stu-id="8b262-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="8b262-173">Pour plus d’informations, consultez [gérer les stratégies d’appel d’urgence dans teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8b262-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="8b262-174">Activer les utilisateurs et les sites</span><span class="sxs-lookup"><span data-stu-id="8b262-174">Enable users and sites</span></span>

<span data-ttu-id="8b262-175">Lorsque les utilisateurs d’un plan d’appels sont automatiquement activés pour les appels d’urgence, vous devez activer les notifications d’appel d’urgence en configurant la politique d’appel d’urgence, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="8b262-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="8b262-176">Vous pouvez également affecter la politique d’appel d’urgence à un site réseau comme le montre l’exemple suivant, qui affecte une stratégie appelée « stratégie d’appel d’urgence contoso 1 » vers le site 1 :</span><span class="sxs-lookup"><span data-stu-id="8b262-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="8b262-177">Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b262-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="8b262-178">Tester les appels d’urgence</span><span class="sxs-lookup"><span data-stu-id="8b262-178">Test emergency calling</span></span>

<span data-ttu-id="8b262-179">Pour tester les appels d’urgence aux États-Unis, utilisez la 933 de test prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="8b262-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="8b262-180">Ce numéro est routé vers un bot, qui réagit ensuite du numéro de téléphone de l’appelant (ID de ligne d’appel), de l’adresse de secours ou de l’emplacement et de l’acheminement automatique de l’appel vers le champ PSAPI ou à l’écran.</span><span class="sxs-lookup"><span data-stu-id="8b262-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  