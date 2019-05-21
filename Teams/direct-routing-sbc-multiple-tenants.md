---
title: Configurer un contrôleur de frontière de session pour plusieurs clients
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez à configurer un contrôleur de bordure de session (SBC) pour servir plusieurs clients.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290468"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="55b6b-103">Configurer un contrôleur de frontière de session pour plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="55b6b-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="55b6b-104">Le routage direct prend en charge la configuration d’un contrôleur de bordure de session (SBC) pour servir plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="55b6b-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="55b6b-105">Ce scénario est destiné aux partenaires Microsoft et/ou aux opérateurs RTC, désignés sous le nom de opérateurs plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="55b6b-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="55b6b-106">Un opérateur vend aux utilisateurs de services de téléphonie remis à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55b6b-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="55b6b-107">Opérateur:</span><span class="sxs-lookup"><span data-stu-id="55b6b-107">A carrier:</span></span>
- <span data-ttu-id="55b6b-108">Déploie et gère une SBC sur son centre de donnes (les clients n’ont pas besoin d’implémenter de SBC et ils reçoivent les services de téléphonie de l’opérateur dans le client Teams).</span><span class="sxs-lookup"><span data-stu-id="55b6b-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="55b6b-109">Interconnecte l’SBC à plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="55b6b-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="55b6b-110">Fournit des services RTC aux clients.</span><span class="sxs-lookup"><span data-stu-id="55b6b-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="55b6b-111">Gère la fin de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="55b6b-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="55b6b-112">Frais pour les services RTC séparément.</span><span class="sxs-lookup"><span data-stu-id="55b6b-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="55b6b-113">Microsoft ne gère pas les opérateurs.</span><span class="sxs-lookup"><span data-stu-id="55b6b-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="55b6b-114">Microsoft propose un système PBX (Microsoft Phone System) et un client Teams, certifie les téléphones et certifie SBCs qui peut être utilisé avec le système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="55b6b-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="55b6b-115">Avant de choisir un opérateur, assurez-vous que votre choix dispose d’une SBC certifié et peut gérer la fin de la qualité de la voix.</span><span class="sxs-lookup"><span data-stu-id="55b6b-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="55b6b-116">Vous trouverez ci-après les étapes d’implémentation techniques de la configuration du scénario.</span><span class="sxs-lookup"><span data-stu-id="55b6b-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="55b6b-117">**Opérateur uniquement:**</span><span class="sxs-lookup"><span data-stu-id="55b6b-117">**Carrier only:**</span></span>
1. <span data-ttu-id="55b6b-118">Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux [instructions des fournisseurs de SBC certifiés](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="55b6b-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="55b6b-119">Enregistrez un nom de domaine de base dans le client de l’opérateur et demandez un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="55b6b-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="55b6b-120">Enregistrez un sous-domaine pour chaque client, qui fait partie du domaine de base.</span><span class="sxs-lookup"><span data-stu-id="55b6b-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="55b6b-121">**Opérateur avec un administrateur global du client:**</span><span class="sxs-lookup"><span data-stu-id="55b6b-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="55b6b-122">Ajoutez le nom de sous-domaine au locataire du client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="55b6b-123">Activez le nom de sous-domaine.</span><span class="sxs-lookup"><span data-stu-id="55b6b-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="55b6b-124">Configurez le Trunk du transporteur sur le locataire du client et approvisionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55b6b-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="55b6b-125">*Veuillez vous assurer que vous comprenez les concepts de base de l’utilisation de la gestion des enregistrements DNS et comment le nom de domaine est géré dans Office 365. Consultez [obtenir de l’aide sur les domaines Office 365 avant de](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) continuer.*</span><span class="sxs-lookup"><span data-stu-id="55b6b-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="55b6b-126">Déploiement et configuration de l’SBC</span><span class="sxs-lookup"><span data-stu-id="55b6b-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="55b6b-127">Pour plus d’informations sur le déploiement et la configuration de SBCs pour un scénario d’hébergement SBC, consultez la documentation du fournisseur de SBC.</span><span class="sxs-lookup"><span data-stu-id="55b6b-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="55b6b-128">**AudioCodes:** [Remarques sur la configuration du routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuration du scénario d’hébergement SBC décrit dans «connexion de AudioCodes SBC à la configuration de modèle d’hébergement de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="55b6b-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="55b6b-129">**Communications du ruban:**  Reportez-vous au [Guide de configuration de Microsoft teams SBC principal du ruban](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) pour obtenir une documentation sur la configuration de la série de cœurs du ruban SBCS et sur cette page. [ Bordure](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="55b6b-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="55b6b-130">Veuillez nous concentrer sur la configuration de l’en-tête «contact».</span><span class="sxs-lookup"><span data-stu-id="55b6b-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="55b6b-131">L’en-tête contact permet de rechercher le locataire du client dans le message d’invitation entrant.</span><span class="sxs-lookup"><span data-stu-id="55b6b-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="55b6b-132">Inscrire un domaine de base et des sous-domaines</span><span class="sxs-lookup"><span data-stu-id="55b6b-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="55b6b-133">Pour le scénario d’hébergement, vous devez créer:</span><span class="sxs-lookup"><span data-stu-id="55b6b-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="55b6b-134">Un nom de domaine de base possédé par l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="55b6b-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="55b6b-135">Sous-domaine qui fait partie du nom de domaine de base dans chaque client de client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="55b6b-136">Dans l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="55b6b-136">In the following example:</span></span>
- <span data-ttu-id="55b6b-137">Adatum est un opérateur qui dessert plusieurs clients en fournissant des services Internet et de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="55b6b-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="55b6b-138">Woodgrove Bank, contoso et Adventure Works sont trois clients possédant des domaines Office 365, mais ils reçoivent les services de téléphonie de adatum.</span><span class="sxs-lookup"><span data-stu-id="55b6b-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="55b6b-139">Les sous-domaines **doivent** correspondre au nom de domaine complet (FQDN) du Trunk qui sera configuré pour le client et du nom de domaine complet (FQDN) dans l’en-tête de contact lors de l’envoi de l’invitation à Office 365.</span><span class="sxs-lookup"><span data-stu-id="55b6b-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="55b6b-140">Lorsqu’un appel arrive sur l’interface de routage directe d’Office 365, l’interface utilise l’en-tête de contact pour trouver le client à l’endroit où l’utilisateur doit être recherché.</span><span class="sxs-lookup"><span data-stu-id="55b6b-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="55b6b-141">Le routage direct n’utilise pas la recherche de numéros de téléphone dans l’invitation, car certains clients peuvent avoir des numéros qui peuvent se chevaucher dans plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="55b6b-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="55b6b-142">Par conséquent, le nom de domaine complet dans l’en-tête de contact est requis pour identifier le client exact pour trouver le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="55b6b-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="55b6b-143">*Pour plus d’informations sur la création de noms de domaine dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="55b6b-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="55b6b-144">Le diagramme suivant récapitule les exigences relatives aux domaines de base, sous-domaines et en-tête de contact.</span><span class="sxs-lookup"><span data-stu-id="55b6b-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Exigences en matière de domaine de base, de sous-domaines et d’en-tête de contact](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="55b6b-146">L’SBC nécessite un certificat pour authentifier les connexions.</span><span class="sxs-lookup"><span data-stu-id="55b6b-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="55b6b-147">Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec San \* \*. base_domain (par exemple, \*Customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="55b6b-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="55b6b-148">Ce certificat peut être utilisé pour authentifier les connexions à plusieurs clients desservis à partir d’un SBC unique.</span><span class="sxs-lookup"><span data-stu-id="55b6b-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="55b6b-149">Le tableau suivant illustre une configuration.</span><span class="sxs-lookup"><span data-stu-id="55b6b-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="55b6b-150">Nouveau nom de domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-150">New domain name</span></span> |<span data-ttu-id="55b6b-151">Type</span><span class="sxs-lookup"><span data-stu-id="55b6b-151">Type</span></span>|<span data-ttu-id="55b6b-152">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="55b6b-152">Registered</span></span>  |<span data-ttu-id="55b6b-153">Certificat SAN pour SBC</span><span class="sxs-lookup"><span data-stu-id="55b6b-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="55b6b-154">Domaine par défaut du client dans l’exemple</span><span class="sxs-lookup"><span data-stu-id="55b6b-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="55b6b-155">Nom de domaine complet que SBC doit présenter dans l’en-tête de contact lors de l’envoi d’appels aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="55b6b-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="55b6b-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-156">customers.adatum.biz</span></span>|    <span data-ttu-id="55b6b-157">Assiette</span><span class="sxs-lookup"><span data-stu-id="55b6b-157">Base</span></span>     |     <span data-ttu-id="55b6b-158">Client du transporteur</span><span class="sxs-lookup"><span data-stu-id="55b6b-158">In carrier tenant</span></span>  |    <span data-ttu-id="55b6b-159">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="55b6b-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-160">adatum.biz</span></span>      |<span data-ttu-id="55b6b-161">NA, il s’agit d’un client de service, sans utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55b6b-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="55b6b-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="55b6b-163">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-163">Subdomain</span></span>  |    <span data-ttu-id="55b6b-164">Dans un client client</span><span class="sxs-lookup"><span data-stu-id="55b6b-164">In a customer tenant</span></span>  |    <span data-ttu-id="55b6b-165">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="55b6b-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="55b6b-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="55b6b-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="55b6b-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="55b6b-169">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-169">Subdomain</span></span> | <span data-ttu-id="55b6b-170">Dans un client client</span><span class="sxs-lookup"><span data-stu-id="55b6b-170">In a customer tenant</span></span>   |   <span data-ttu-id="55b6b-171">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="55b6b-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="55b6b-172">contoso.com</span></span>   |<span data-ttu-id="55b6b-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="55b6b-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="55b6b-175">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-175">Subdomain</span></span> | <span data-ttu-id="55b6b-176">Dans un client client</span><span class="sxs-lookup"><span data-stu-id="55b6b-176">In a customer tenant</span></span> |   <span data-ttu-id="55b6b-177">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="55b6b-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="55b6b-178">adventureworks.com</span></span> | <span data-ttu-id="55b6b-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="55b6b-180">Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="55b6b-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="55b6b-181">Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le client Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="55b6b-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="55b6b-182">Inscrire un nom de domaine de base dans le client de l’opérateur</span><span class="sxs-lookup"><span data-stu-id="55b6b-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="55b6b-183">**Ces actions sont exécutées dans le locataire du transporteur.**</span><span class="sxs-lookup"><span data-stu-id="55b6b-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="55b6b-184">Vérifiez que vous disposez des droits appropriés pour le locataire du transporteur</span><span class="sxs-lookup"><span data-stu-id="55b6b-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="55b6b-185">Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes connecté au centre d’administration Microsoft 365 en tant qu’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="55b6b-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="55b6b-186">Pour valider le rôle dont vous disposez, connectez-vous au centre d’administration 365 Microsofthttps://portal.office.com)(, accédez à **utilisateurs** > **actifs**, puis vérifiez que vous avez le rôle d’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="55b6b-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="55b6b-187">Pour plus d’informations sur les rôles d’administrateur et comment attribuer un rôle dans Office 365, voir [à propos des rôles d’administrateur office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="55b6b-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="55b6b-188">Ajouter un domaine de base au client et le vérifier</span><span class="sxs-lookup"><span data-stu-id="55b6b-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="55b6b-189">Dans le centre d’administration Microsoft 365, accédez à **configuration** > des**domaines** > **Ajouter un domaine**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="55b6b-190">Dans la zone **Entrez un domaine que vous possédez** , tapez le nom de domaine complet (FQDN) du domaine de base.</span><span class="sxs-lookup"><span data-stu-id="55b6b-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="55b6b-191">Dans l’exemple suivant, le domaine de base est *Customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="55b6b-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Ajout d’un domaine de base](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="55b6b-193">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-193">Click **Next**.</span></span>
4. <span data-ttu-id="55b6b-194">Dans l’exemple, le locataire a déjà adatum.biz comme nom de domaine vérifié.</span><span class="sxs-lookup"><span data-stu-id="55b6b-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="55b6b-195">L’Assistant ne demande pas de vérification supplémentaire, car customers.adatum.biz est un sous-domaine du nom déjà enregistré.</span><span class="sxs-lookup"><span data-stu-id="55b6b-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="55b6b-196">Toutefois, si vous ajoutez un nom de domaine complet (FQDN) qui n’a pas été vérifié auparavant, vous devez suivre le processus de vérification.</span><span class="sxs-lookup"><span data-stu-id="55b6b-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="55b6b-197">Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="55b6b-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="55b6b-199">Cliquez sur **suivant**, puis, dans la page **mettre à jour les paramètres DNS** , sélectionnez **Ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="55b6b-200">Sur la page suivante, effacez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint ou teams/Skype entreprise), cliquez sur **suivant**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="55b6b-201">Assurez-vous que votre nouveau domaine est dans l’État configuration terminée.</span><span class="sxs-lookup"><span data-stu-id="55b6b-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domaines affichant l’état d’achèvement de l’installation](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="55b6b-203">Activer le nom de domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-203">Activate the domain name</span></span>

<span data-ttu-id="55b6b-204">Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins une licence E1, E3 ou E5 et en attribuant une adresse SIP à la partie FQDN de l’adresse SIP correspondant au domaine de base créé.</span><span class="sxs-lookup"><span data-stu-id="55b6b-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="55b6b-205">*Pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="55b6b-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="55b6b-206">Par exemple: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-206">For example: test@customers.adatum.biz</span></span>

![Page activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="55b6b-208">Inscrire un nom de sous-domaine dans un client client</span><span class="sxs-lookup"><span data-stu-id="55b6b-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="55b6b-209">Vous devrez créer un nom de sous-domaine unique pour chaque client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="55b6b-210">Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un client avec le nom de domaine par défaut woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="55b6b-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="55b6b-211">**Toutes les actions ci-dessous se trouvent dans le locataire du client.**</span><span class="sxs-lookup"><span data-stu-id="55b6b-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="55b6b-212">Vérifiez que vous disposez des droits appropriés pour le locataire du client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="55b6b-213">Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes connecté au centre d’administration Microsoft 365 en tant qu’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="55b6b-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="55b6b-214">Pour valider le rôle dont vous disposez, connectez-vous au centre d’administration 365 Microsofthttps://portal.office.com)(, accédez à **utilisateurs** > **actifs**, puis vérifiez que vous avez le rôle d’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="55b6b-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="55b6b-215">Pour plus d’informations sur les rôles d’administrateur et comment attribuer un rôle dans Office 365, voir [à propos des rôles d’administrateur office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="55b6b-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="55b6b-216">Ajouter un sous-domaine au locataire du client et le vérifier</span><span class="sxs-lookup"><span data-stu-id="55b6b-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="55b6b-217">Dans le centre d’administration Microsoft 365, accédez à **configuration** > des**domaines** > **Ajouter un domaine**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="55b6b-218">Dans la zone **Entrez un domaine que vous possédez** , tapez le nom de domaine complet (FQDN) du sous-domaine de ce client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="55b6b-219">Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="55b6b-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Ajouter un sous-domaine de client](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="55b6b-221">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-221">Click **Next**.</span></span>
4. <span data-ttu-id="55b6b-222">Le nom de domaine complet ne s’est jamais inscrit dans le client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="55b6b-223">À l’étape suivante, vous devrez vérifier le domaine.</span><span class="sxs-lookup"><span data-stu-id="55b6b-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="55b6b-224">À **la place, sélectionnez Ajouter un enregistrement txt**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-224">Select **Add a TXT record instead**.</span></span> 

    ![Options de la page vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="55b6b-226">Cliquez sur **suivant**, puis notez la valeur txt générée pour vérifier le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="55b6b-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Enregistrements de texte dans la page vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="55b6b-228">Créez l’enregistrement TXT avec la valeur de l’étape précédente du fournisseur d’hébergement DNS de l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="55b6b-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Création de l’enregistrement TXT dans le fournisseur d’hébergement DNS de l’opérateur](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="55b6b-230">Pour plus d’informations, voir [créer des enregistrements DNS auprès d’un fournisseur d’hébergement DNS pour Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="55b6b-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="55b6b-231">Revenez au centre d’administration 365 Microsoft et cliquez sur **vérifier**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="55b6b-232">Sur la page suivante, sélectionnez **je vais ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Options de la page mettre à jour les paramètres DNS](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="55b6b-234">Dans la page **choisir vos services en ligne** , désactivez toutes les options, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![La page choisir vos services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="55b6b-236">Cliquez sur **Terminer** dans la page **mettre à jour les paramètres DNS** .</span><span class="sxs-lookup"><span data-stu-id="55b6b-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![Page mettre à jour les paramètres DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="55b6b-238">Assurez-vous que le paramètre statut est **terminé**.</span><span class="sxs-lookup"><span data-stu-id="55b6b-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Page indiquant l’état d’achèvement de l’installation](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="55b6b-240">Activer le nom de sous-domaine</span><span class="sxs-lookup"><span data-stu-id="55b6b-240">Activate the subdomain name</span></span>

<span data-ttu-id="55b6b-241">Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et en assignant une adresse SIP avec la partie FQDN de l’adresse SIP correspondant au sous-domaine créé dans le client client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="55b6b-242">*Pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="55b6b-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="55b6b-243">Par exemple: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="55b6b-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Activation de la page de sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="55b6b-245">Créer un Trunking et configurer les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="55b6b-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="55b6b-246">En fonction de votre avis que nous avons reçu dans le programme d’adoption technique, Microsoft peut changer le processus de création de Trunks dans les clients clients pour simplifier le processus.</span><span class="sxs-lookup"><span data-stu-id="55b6b-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="55b6b-247">Pour plus d’informations, consultez les mises à jour de la documentation sur cette page et suivez les blogs de la communauté technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55b6b-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="55b6b-248">Créez un Trunk dans le domaine du client à l’aide de la commande New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="55b6b-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="55b6b-249">Le nom de domaine complet du Trunk **doit** correspondre au sous-domaine créé pour le client.</span><span class="sxs-lookup"><span data-stu-id="55b6b-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="55b6b-250">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="55b6b-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="55b6b-251">Lors de la création du Trunk, vous pouvez recevoir le message d’erreur suivant:</span><span class="sxs-lookup"><span data-stu-id="55b6b-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="55b6b-252">Veuillez patienter pendant que l’inscription et l’activation du domaine sont répliquées, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="55b6b-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="55b6b-253">Approvisionner les utilisateurs avec les numéros de téléphone et configurer le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="55b6b-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="55b6b-254">Pour plus d’informations sur le nouveau-CSOnlinePSTNGateway, la mise en service des utilisateurs et la configuration du routage des communications vocales, consultez [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="55b6b-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="55b6b-255">Pour plus d’informations, reportez-vous à la rubrique [instructions du fournisseur SBC](#deploy-and-configure-the-sbc) sur la configuration de l’envoi du nom FQDN des sous-domaines dans l’en-tête contact.</span><span class="sxs-lookup"><span data-stu-id="55b6b-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

