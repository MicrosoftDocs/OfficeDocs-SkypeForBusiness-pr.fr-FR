---
title: Configurer un contrôleur de Session en périphérie pour plusieurs locataires
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Découvrez comment configurer un contrôleur de Session bordure (SBC) pour prendre en charge plusieurs clients.
ms.openlocfilehash: 292a3e675455d112fdade04018e670b9a5f9c38f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295743"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="e27af-103">Configurer un contrôleur de Session en périphérie pour plusieurs locataires</span><span class="sxs-lookup"><span data-stu-id="e27af-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="e27af-104">Routage direct prend en charge la configuration une bordure contrôleur Session (SBC) pour prendre en charge plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="e27af-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="e27af-105">Ce scénario est conçu pour les partenaires Microsoft et/ou des opérateurs PSTN, appelés opérateurs plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="e27af-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="e27af-106">Un opérateur vend remis à Microsoft Teams à leurs clients des services de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="e27af-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="e27af-107">Un opérateur :</span><span class="sxs-lookup"><span data-stu-id="e27af-107">A carrier:</span></span>
- <span data-ttu-id="e27af-108">Déploie et gère un contrôleur SBC dans leur centre de données (clients n’avez pas besoin d’implémenter un contrôleur SBC, et ils reçoivent des services de téléphonie de l’opérateur dans le client équipes).</span><span class="sxs-lookup"><span data-stu-id="e27af-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="e27af-109">Relie le contrôleur SBC à plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="e27af-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="e27af-110">Fournit des services PSTN pour les clients.</span><span class="sxs-lookup"><span data-stu-id="e27af-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="e27af-111">Gère la qualité des appels bout en bout.</span><span class="sxs-lookup"><span data-stu-id="e27af-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="e27af-112">Frais séparément de services PSTN.</span><span class="sxs-lookup"><span data-stu-id="e27af-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="e27af-113">Microsoft ne gère pas les opérateurs.</span><span class="sxs-lookup"><span data-stu-id="e27af-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="e27af-114">Microsoft offre un système PBX (système téléphonique de Microsoft) et un client équipes, atteste de téléphones et atteste SBCs qui peuvent être utilisés avec le système téléphonique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e27af-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="e27af-115">Avant de choisir un opérateur, assurez-vous que votre choix a une SBC certifié et peut gérer la qualité de voix bout en bout.</span><span class="sxs-lookup"><span data-stu-id="e27af-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="e27af-116">Voici les étapes de mise en œuvre technique pour configurer le scénario.</span><span class="sxs-lookup"><span data-stu-id="e27af-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="e27af-117">**Opérateur :**</span><span class="sxs-lookup"><span data-stu-id="e27af-117">**Carrier only:**</span></span>
1. <span data-ttu-id="e27af-118">Déployer le contrôleur SBC et le configurer pour le scénario d’hébergement conformément aux [instructions des fournisseurs SBC certifiés](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="e27af-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="e27af-119">Enregistrer un nom de domaine de base dans le client de l’opérateur et demander un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="e27af-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="e27af-120">Inscrire un sous-domaine pour chaque client qui fait partie du domaine de base.</span><span class="sxs-lookup"><span data-stu-id="e27af-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="e27af-121">**Support administrateur Global client :**</span><span class="sxs-lookup"><span data-stu-id="e27af-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="e27af-122">Ajouter le nom du sous-domaine au client client.</span><span class="sxs-lookup"><span data-stu-id="e27af-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="e27af-123">Activer le nom du sous-domaine.</span><span class="sxs-lookup"><span data-stu-id="e27af-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="e27af-124">Configurer la jonction de l’opérateur pour les utilisateurs de client et de mise en service du client.</span><span class="sxs-lookup"><span data-stu-id="e27af-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="e27af-125">*Assurez-vous que vous comprenez les concepts de base DNS et comment le nom de domaine est géré dans Office 365. Avant de continuer, consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="e27af-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="e27af-126">Déployer et configurer le contrôleur SBC</span><span class="sxs-lookup"><span data-stu-id="e27af-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="e27af-127">Pour obtenir les étapes détaillées sur la façon de déployer et configurer SBC pour un scénario d’hébergement SBC, reportez-vous à la documentation de SBC.</span><span class="sxs-lookup"><span data-stu-id="e27af-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="e27af-128">**AudioCodes :** [Notes de Configuration de routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuration de la SBC hébergeant le scénario décrit dans « Connexion AudioCodes SBC à Microsoft Teams Direct routage hébergement modèle Configuration Note ».</span><span class="sxs-lookup"><span data-stu-id="e27af-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="e27af-129">**Communications de ruban :**  Reportez-vous au [Guide de Configuration du ruban Communications SBC principaux Microsoft équipes](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) pour la documentation sur la configuration du ruban principal série SBCs et à cette page [ruban meilleures conseillée - opérateurs de configuration pour le routage Direct des équipes Microsoft SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="e27af-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="e27af-130">Prêtez attention à la configuration de l’en-tête « Contacts ».</span><span class="sxs-lookup"><span data-stu-id="e27af-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="e27af-131">L’en-tête de Contact est utilisé pour trouver le client du client sur le message invite entrant.</span><span class="sxs-lookup"><span data-stu-id="e27af-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="e27af-132">Inscrire un domaine de base et les sous-domaines</span><span class="sxs-lookup"><span data-stu-id="e27af-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="e27af-133">Pour le scénario d’hébergement, vous devez créer :</span><span class="sxs-lookup"><span data-stu-id="e27af-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="e27af-134">Un nom de domaine de base détenu par l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="e27af-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="e27af-135">Un sous-domaine qui fait partie du nom de domaine de base dans chaque client du client.</span><span class="sxs-lookup"><span data-stu-id="e27af-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="e27af-136">Dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e27af-136">In the following example:</span></span>
- <span data-ttu-id="e27af-137">Adatum est un opérateur qui sert de plusieurs clients en fournissant des services Internet et de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="e27af-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="e27af-138">Woodgrove Bank, Contoso et Adventure Works les trois clients qui ont des domaines d’Office 365, mais les services de téléphonie des Adatum.</span><span class="sxs-lookup"><span data-stu-id="e27af-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="e27af-139">Sous-domaines **doit** correspondent au nom de nom de domaine complet de la jonction qui vont être configuré pour le client et le nom de domaine complet dans l’en-tête de Contact lors de l’envoi de l’invitation à Office 365.</span><span class="sxs-lookup"><span data-stu-id="e27af-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="e27af-140">Lorsqu’un appel arrive à l’interface de routage Direct Office 365, l’interface utilise l’en-tête de Contact pour trouver le client où l’utilisateur doit être recherché.</span><span class="sxs-lookup"><span data-stu-id="e27af-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="e27af-141">Routage direct n’utilise pas recherche de numéros de téléphone dans l’invitation, comme certains clients peut-être non-avez-vous numéros peuvent se chevaucher dans plusieurs clients.</span><span class="sxs-lookup"><span data-stu-id="e27af-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="e27af-142">Par conséquent, le nom de domaine complet dans l’en-tête de Contact est requis pour identifier le client exact pour rechercher l’utilisateur par le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="e27af-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="e27af-143">*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur la création des noms de domaine dans les clients Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e27af-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="e27af-144">Le diagramme suivant résume la configuration requise pour l’en-tête de Contact, sous-domaines et le domaine de base.</span><span class="sxs-lookup"><span data-stu-id="e27af-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Conditions requises pour l’en-tête de Contact, sous-domaines et le domaine de base](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="e27af-146">Le contrôleur SBC nécessite un certificat pour authentifier les connexions.</span><span class="sxs-lookup"><span data-stu-id="e27af-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="e27af-147">Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec SAN \* \*.base_domain (par exemple, \*customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="e27af-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="e27af-148">Ce certificat peut être utilisé pour authentifier des connexions à plusieurs locataires traitées à partir d’un contrôleur SBC unique.</span><span class="sxs-lookup"><span data-stu-id="e27af-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="e27af-149">Le tableau suivant est un exemple d’une configuration.</span><span class="sxs-lookup"><span data-stu-id="e27af-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="e27af-150">Nouveau nom de domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-150">New domain name</span></span> |<span data-ttu-id="e27af-151">Type</span><span class="sxs-lookup"><span data-stu-id="e27af-151">Type</span></span>|<span data-ttu-id="e27af-152">Inscrit</span><span class="sxs-lookup"><span data-stu-id="e27af-152">Registered</span></span>  |<span data-ttu-id="e27af-153">Certificat SAN pour SBC</span><span class="sxs-lookup"><span data-stu-id="e27af-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="e27af-154">Domaine par défaut de client dans l’exemple</span><span class="sxs-lookup"><span data-stu-id="e27af-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="e27af-155">Nom de domaine complet SBC doit présenter dans l’en-tête de Contact lors de l’envoi des appels aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e27af-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="e27af-156">Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-156">customers.adatum.biz</span></span>|    <span data-ttu-id="e27af-157">Base de</span><span class="sxs-lookup"><span data-stu-id="e27af-157">Base</span></span>     |     <span data-ttu-id="e27af-158">Dans le client de l’opérateur</span><span class="sxs-lookup"><span data-stu-id="e27af-158">In carrier tenant</span></span>  |    <span data-ttu-id="e27af-159">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="e27af-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-160">adatum.biz</span></span>      |<span data-ttu-id="e27af-161">NA, il s’agit d’un client de service, pas d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e27af-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="e27af-162">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="e27af-163">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-163">Subdomain</span></span>  |    <span data-ttu-id="e27af-164">Dans un client de client</span><span class="sxs-lookup"><span data-stu-id="e27af-164">In a customer tenant</span></span>  |    <span data-ttu-id="e27af-165">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="e27af-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="e27af-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="e27af-167">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="e27af-168">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="e27af-169">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-169">Subdomain</span></span> | <span data-ttu-id="e27af-170">Dans un client de client</span><span class="sxs-lookup"><span data-stu-id="e27af-170">In a customer tenant</span></span>   |   <span data-ttu-id="e27af-171">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="e27af-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e27af-172">contoso.com</span></span>   |<span data-ttu-id="e27af-173">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="e27af-174">SBC3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="e27af-175">Sous-domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-175">Subdomain</span></span> | <span data-ttu-id="e27af-176">Dans un client de client</span><span class="sxs-lookup"><span data-stu-id="e27af-176">In a customer tenant</span></span> |   <span data-ttu-id="e27af-177">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="e27af-178">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="e27af-178">adventureworks.com</span></span> | <span data-ttu-id="e27af-179">SBC3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="e27af-180">Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e27af-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="e27af-181">Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine d’un seul client (sbc1.customers.adatum.biz dans client Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="e27af-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="e27af-182">Enregistrer un nom de domaine de base dans le client de l’opérateur</span><span class="sxs-lookup"><span data-stu-id="e27af-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="e27af-183">**Ces actions sont effectuées dans le client de l’opérateur.**</span><span class="sxs-lookup"><span data-stu-id="e27af-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="e27af-184">Vérifiez que vous disposez des droits appropriés dans le client de l’opérateur</span><span class="sxs-lookup"><span data-stu-id="e27af-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="e27af-185">Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes le centre d’administration Office 365 en tant qu’administrateur Global.</span><span class="sxs-lookup"><span data-stu-id="e27af-185">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="e27af-186">Pour valider le rôle que vous avez, connectez-vous au centre d’administration Microsoft 365 (https://portal.office.com), accédez aux **utilisateurs** > **Utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général.</span><span class="sxs-lookup"><span data-stu-id="e27af-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="e27af-187">Pour plus d’informations sur les rôles d’administrateur et comment affecter un rôle dans Office 365, voir [rôles d’administrateur sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="e27af-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="e27af-188">Ajouter un domaine de base au client et vérifiez qu’il</span><span class="sxs-lookup"><span data-stu-id="e27af-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="e27af-189">Dans le centre d’administration Microsoft 365, accédez à **configuration** > **domaines** > **Ajouter domaine**.</span><span class="sxs-lookup"><span data-stu-id="e27af-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="e27af-190">Dans la zone **Entrez un domaine que vous êtes propriétaire** , tapez le nom de domaine complet du domaine de base.</span><span class="sxs-lookup"><span data-stu-id="e27af-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="e27af-191">Dans l’exemple suivant, le domaine de base est *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="e27af-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Ajout d’un domaine de base](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="e27af-193">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e27af-193">Click **Next**.</span></span>
4. <span data-ttu-id="e27af-194">Dans l’exemple, le client a déjà adatum.biz sous un nom de domaine vérifié.</span><span class="sxs-lookup"><span data-stu-id="e27af-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="e27af-195">L’Assistant vous demandera pas une vérification supplémentaire, car customers.adatum.biz est un sous-domaine du nom déjà enregistrée.</span><span class="sxs-lookup"><span data-stu-id="e27af-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="e27af-196">Toutefois, si vous ajoutez un nom de domaine qui n’a pas été vérifié, vous devez suivre le processus de vérification.</span><span class="sxs-lookup"><span data-stu-id="e27af-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="e27af-197">Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="e27af-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="e27af-199">Cliquez sur **suivant**et dans la page **Paramètres de mise à jour DNS** , sélectionnez **je vais ajouter les enregistrements DNS moi-même** et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e27af-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="e27af-200">Dans la page suivante, désactivez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint ou équipes/Skype pour les entreprises), cliquez sur **suivant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e27af-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="e27af-201">Assurez-vous que votre nouveau domaine se trouve dans l’état complet du programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="e27af-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domaines indiquant l’état d’installation complète](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="e27af-203">Activer le nom de domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-203">Activate the domain name</span></span>

<span data-ttu-id="e27af-204">Une fois que vous avez enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et attribuer une adresse SIP avec la partie nom de domaine complet de l’adresse SIP correspondant à ce domaine de base créé.</span><span class="sxs-lookup"><span data-stu-id="e27af-204">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="e27af-205">*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e27af-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="e27af-206">Par exemple : test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-206">For example: test@customers.adatum.biz</span></span>

![Page d’activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="e27af-208">Inscrire un nom de sous-domaine dans un client de client</span><span class="sxs-lookup"><span data-stu-id="e27af-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="e27af-209">Vous devez créer un nom de sous-domaine unique pour chaque client.</span><span class="sxs-lookup"><span data-stu-id="e27af-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="e27af-210">Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un client avec le woodgrovebank.us de nom de domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="e27af-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="e27af-211">**Toutes les actions ci-dessous sont dans le client du client.**</span><span class="sxs-lookup"><span data-stu-id="e27af-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="e27af-212">Vérifiez que vous disposez des droits appropriés dans le client du client</span><span class="sxs-lookup"><span data-stu-id="e27af-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="e27af-213">Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes le centre d’administration Office 365 en tant qu’administrateur Global.</span><span class="sxs-lookup"><span data-stu-id="e27af-213">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="e27af-214">Pour valider le rôle que vous avez, connectez-vous au centre d’administration Microsoft 365 (https://portal.office.com), accédez aux **utilisateurs** > **Utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général.</span><span class="sxs-lookup"><span data-stu-id="e27af-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="e27af-215">Pour plus d’informations sur les rôles d’administrateur et comment affecter un rôle dans Office 365, voir [rôles d’administrateur sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="e27af-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="e27af-216">Ajouter un sous-domaine au client client et vérifiez qu’il</span><span class="sxs-lookup"><span data-stu-id="e27af-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="e27af-217">Dans le centre d’administration Microsoft 365, accédez à **configuration** > **domaines** > **Ajouter domaine**.</span><span class="sxs-lookup"><span data-stu-id="e27af-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="e27af-218">Dans la zone **Entrez un domaine que vous êtes propriétaire** , tapez le nom de domaine complet du sous-domaine pour ce client.</span><span class="sxs-lookup"><span data-stu-id="e27af-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="e27af-219">Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="e27af-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Ajout d’un sous-domaine du client](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="e27af-221">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e27af-221">Click **Next**.</span></span>
4. <span data-ttu-id="e27af-222">Le nom de domaine complet n’a jamais été enregistré dans le client.</span><span class="sxs-lookup"><span data-stu-id="e27af-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="e27af-223">Dans l’étape suivante, vous devez vérifier le domaine.</span><span class="sxs-lookup"><span data-stu-id="e27af-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="e27af-224">Sélectionnez **Ajouter un enregistrement TXT à la place**.</span><span class="sxs-lookup"><span data-stu-id="e27af-224">Select **Add a TXT record instead**.</span></span> 

    ![Options de la page vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="e27af-226">Cliquez sur **suivant**et notez la valeur TXT générée pour vérifier le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="e27af-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Enregistrements de texte sur la page vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="e27af-228">Créer l’enregistrement TXT avec la valeur de l’étape précédente dans le fournisseur d’hébergement DNS de l’opérateur mobile.</span><span class="sxs-lookup"><span data-stu-id="e27af-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Création de l’enregistrement TXT dans le fournisseur d’hébergement DNS de l’opérateur](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="e27af-230">Pour plus d’informations, reportez-vous à [créer des enregistrements DNS à n’importe quel fournisseur d’hébergement DNS pour Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="e27af-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="e27af-231">Revenez au centre d’administration de Microsoft 365 du client et cliquez sur **Vérifier**.</span><span class="sxs-lookup"><span data-stu-id="e27af-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="e27af-232">Dans la page suivante, sélectionnez **je vais ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e27af-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Options de la page Paramètres de mise à jour DNS](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="e27af-234">Dans la page **Choisir vos services en ligne** , désactivez toutes les options, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e27af-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![La choisir votre page services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="e27af-236">Dans la page **paramètres de mise à jour DNS** , cliquez sur **Terminer** .</span><span class="sxs-lookup"><span data-stu-id="e27af-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![La page Paramètres de mise à jour DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="e27af-238">Assurez-vous que l’état est **de terminer l’installation**.</span><span class="sxs-lookup"><span data-stu-id="e27af-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Page indiquant l’état du programme d’installation complète](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="e27af-240">Activer le nom du sous-domaine</span><span class="sxs-lookup"><span data-stu-id="e27af-240">Activate the subdomain name</span></span>

<span data-ttu-id="e27af-241">Après avoir inscrit un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et attribuer une adresse SIP avec la partie nom de domaine complet de l’adresse SIP correspondant le sous-domaine créé dans le client du client.</span><span class="sxs-lookup"><span data-stu-id="e27af-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="e27af-242">*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e27af-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="e27af-243">Par exemple : test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e27af-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Activation de la page sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="e27af-245">Créer une jonction et la mise en service des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e27af-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="e27af-246">En fonction des commentaires reçus dans le programme d’Adoption technique, Microsoft peut changer le processus de création de jonctions dans les clients de client pour simplifier le processus.</span><span class="sxs-lookup"><span data-stu-id="e27af-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="e27af-247">Veuillez regarder les mises à jour de la documentation sur cette page et suivez les blogs de la Communauté technique Microsoft pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="e27af-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="e27af-248">Créer une jonction dans le domaine de client à l’aide de la commande New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="e27af-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="e27af-249">La jonction de nom de domaine complet **doit** correspondre le sous-domaine créé pour le client.</span><span class="sxs-lookup"><span data-stu-id="e27af-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="e27af-250">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e27af-250">For example:</span></span>

<span data-ttu-id="e27af-251">*Nouvelle-CSOnlinePSTNGateway – nom de domaine complet sbc1.customers.adatum.biz - SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="e27af-251">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="e27af-252">Configurer les utilisateurs avec les numéros de téléphone et configurer le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="e27af-252">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="e27af-253">Pour plus d’informations sur le nouveau-CSOnlinePSTNGateway, mise en service des utilisateurs et la configuration de routage des communications vocales, reportez-vous à [Configurer le routage Direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e27af-253">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="e27af-254">Consultez les [instructions du fournisseur SBC](#deploy-and-configure-the-sbc) sur la configuration de l’envoi du nom de domaine complet des sous-domaines dans l’en-tête du Contact.</span><span class="sxs-lookup"><span data-stu-id="e27af-254">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

