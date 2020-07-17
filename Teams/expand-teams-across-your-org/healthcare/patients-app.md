---
title: Présentation de l’application Patients
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: En savoir plus sur l’intégration d’enregistrements de santé électronique dans l’application patients de Microsoft teams à l’aide des API FHIR.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f981b2fc68aa52f8ea5a48fab18977197ac813c8
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098422"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="28825-103">Intégration des dossiers médicaux électroniques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28825-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="28825-104">Cet article s’adresse aux développeurs de systèmes d’information aux soins généraux désireux d’utiliser des API FHIR sur un système d’informations médicales pour se connecter à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28825-104">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="28825-105">Cela permettrait aux scénarios de coordination de soins qui répondent aux besoins d’un organisme de santé.</span><span class="sxs-lookup"><span data-stu-id="28825-105">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="28825-106">Les Articles liés documentent les spécifications de l’interface FHIR pour l’application Microsoft teams patients et indiquent ce qui est requis pour la configuration d’un serveur FHIR et la connexion à l’application patients dans votre environnement de développement ou client.</span><span class="sxs-lookup"><span data-stu-id="28825-106">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="28825-107">Vous devrez également connaître la documentation du serveur FHIR que vous avez choisi, qui doit être l’une des options prises en charge :</span><span class="sxs-lookup"><span data-stu-id="28825-107">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="28825-108">Datica (par le biais de leur offre [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="28825-108">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="28825-109">Infor Cloverleaf (via [infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="28825-109">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="28825-110">Redox (par le biais du [serveur R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="28825-110">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="28825-111">DapaSoft (via [Corolar sur FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="28825-111">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="28825-112">Ce processus n’inclut pas les étapes qui utilisent le centre d’administration Microsoft teams ou les cmdlets PowerShell pour activer des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="28825-112">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="28825-113">La configuration est entièrement réalisée sur le côté du serveur/Service FHIR et dans le client de l’application patients.</span><span class="sxs-lookup"><span data-stu-id="28825-113">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="28825-114">Voici l’architecture de l’application patients :</span><span class="sxs-lookup"><span data-stu-id="28825-114">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramme de l’architecture de l’application patients](../../media/patients-app-architecture.png)

<span data-ttu-id="28825-116">Les sections suivantes décrivent les exigences de la couche d’accès aux données FHIR-only pour l’application patients qu’une API FHIR Server (ou DMI FHIR) doit respecter pour s’intégrer à l’application patients, comme suit :</span><span class="sxs-lookup"><span data-stu-id="28825-116">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="28825-117">Attentes concernant l’authentification des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="28825-117">Expectations around user authentication</span></span>
- <span data-ttu-id="28825-118">Exigences fonctionnelles et techniques de l’interface d’intégration</span><span class="sxs-lookup"><span data-stu-id="28825-118">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="28825-119">Attentes en matière de performances et de fiabilité</span><span class="sxs-lookup"><span data-stu-id="28825-119">Expectations around performance and reliability</span></span>
- <span data-ttu-id="28825-120">Attentes concernant les ressources FHIR devant être prises en charge pour l’application patients</span><span class="sxs-lookup"><span data-stu-id="28825-120">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="28825-121">Processus d’intégration et modèle d’engagement ATTENDU</span><span class="sxs-lookup"><span data-stu-id="28825-121">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="28825-122">Commencer à utiliser FHIR et résoudre certains problèmes courants rencontrés avec l’application patients</span><span class="sxs-lookup"><span data-stu-id="28825-122">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="28825-123">Exigences futures pour l’itération suivante de l’application patients</span><span class="sxs-lookup"><span data-stu-id="28825-123">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="28825-124">Dans les sections suivantes, le mot « partenaire » ou « partenaire d’interopérabilité » est utilisé pour faire référence à toute organisation tierce qui permet l’intégration aux systèmes DMI pour l’application patients via FHIR et implémente un serveur FHIR correspondant aux spécifications indiquées.</span><span class="sxs-lookup"><span data-stu-id="28825-124">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="28825-125">Exigences fonctionnelles et techniques</span><span class="sxs-lookup"><span data-stu-id="28825-125">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="28825-126">Authentification</span><span class="sxs-lookup"><span data-stu-id="28825-126">Authentication</span></span>  

<span data-ttu-id="28825-127">L’autorisation au niveau *de l’application sans support pour l’autorisation au niveau de l’utilisateur* est la façon la plus courante de procéder à des transformations de données et d’exposer les connexions aux données DMI via FHIR, même si le système DMI peut implémenter une autorisation au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28825-127">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="28825-128">Le service d’interopérabilité (partenaire) accède aux données DMI, et lorsqu’il expose les mêmes données que les ressources FHIR appropriées, il n’y a aucun contexte d’autorisation transmis au consommateur de services d’interopérabilité (l’application patients) intégré au service d’interopérabilité ou à la plate-forme.</span><span class="sxs-lookup"><span data-stu-id="28825-128">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="28825-129">L’application patients ne sera pas en mesure de mettre en œuvre l’autorisation de niveau utilisateur, mais elle prend en charge l’authentification des applications entre l’application patients et le service du partenaire d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="28825-129">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="28825-130">Le modèle d’authentification des applications est décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="28825-130">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="28825-131">L’authentification du service au service doit être réalisée par le biais du [flux d’informations d’identification du Client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)2,0 OAuth.</span><span class="sxs-lookup"><span data-stu-id="28825-131">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="28825-132">Le service partenaire doit fournir ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="28825-132">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="28825-133">Le service partenaire permet à l’application patients de créer un compte auprès du partenaire, qui permet à l’application patients de générer client_id et de client_secret, gérée par le biais d’un portail d’inscription d’auth sur le serveur d’authentification du partenaire.</span><span class="sxs-lookup"><span data-stu-id="28825-133">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="28825-134">Le service partenaire possède le système d’authentification/d’autorisation qui accepte et vérifie (authentifie) les informations d’identification du client fournies et renvoie un jeton d’accès avec l’indicateur de client dans l’étendue, comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="28825-134">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="28825-135">Pour des raisons de sécurité, ou en cas de violation secrète, l’application patients peut régénérer le secret et invalider ou supprimer l’ancien secret (par exemple, il est disponible dans Azure Portal-inscription des applications AAD).</span><span class="sxs-lookup"><span data-stu-id="28825-135">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="28825-136">Le point de terminaison de métadonnées qui héberge la déclaration de conformité doit être non authentifié, il doit être accessible sans jeton d’authentification.</span><span class="sxs-lookup"><span data-stu-id="28825-136">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="28825-137">Le service partenaire fournit le point de terminaison jeton de l’application patients pour demander un jeton d’accès à l’aide d’un flux d’informations d’identification du client.</span><span class="sxs-lookup"><span data-stu-id="28825-137">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="28825-138">L’URL du jeton en tant que serveur d’autorisation doit faire partie intégrante de l’instruction de compatibilité FHIR (Capability) récupérée à partir des métadonnées du serveur FHIR, comme dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="28825-138">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="28825-139">{"resourceType" : "CapabilityStatement",.</span><span class="sxs-lookup"><span data-stu-id="28825-139">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="28825-140">.</span><span class="sxs-lookup"><span data-stu-id="28825-140">.</span></span>
        <span data-ttu-id="28825-141">.</span><span class="sxs-lookup"><span data-stu-id="28825-141">.</span></span>
        <span data-ttu-id="28825-142">"Rest" : [{"mode" : "serveur", "sécurité" : {{"URL" : [{"extension" : [{"URL" : "Token", "valueUri" : ""}, {"URL" : ""} "," URL " :" "}])," https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris service " : [{" Coding " : [{" System " :" https://hl7.org/fhir/ValueSet/restful-security-service "," code " :" OAuth "})}]}</span><span class="sxs-lookup"><span data-stu-id="28825-142">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="28825-143">.</span><span class="sxs-lookup"><span data-stu-id="28825-143">.</span></span>
                <span data-ttu-id="28825-144">.</span><span class="sxs-lookup"><span data-stu-id="28825-144">.</span></span>
            <span data-ttu-id="28825-145">} ] }</span><span class="sxs-lookup"><span data-stu-id="28825-145">} ] }</span></span>

* * *

<span data-ttu-id="28825-146">Une demande de jeton d’accès comprend les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="28825-146">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="28825-147">BILLET/Token HTTP/1.1 : authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="28825-147">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="28825-148">Grant-type = client_credentials &client_id = XXXXXXXXXX &client_secret = XXXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="28825-148">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="28825-149">Le service partenaire fournit les client_id et les client_secret de l’application patients, gérés par le biais d’un portail d’inscription d’authentification du côté du partenaire.</span><span class="sxs-lookup"><span data-stu-id="28825-149">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="28825-150">Le service partenaire fournit le point de terminaison pour demander un jeton d’accès à l’aide d’un flux d’informations d’identification client.</span><span class="sxs-lookup"><span data-stu-id="28825-150">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="28825-151">Une réponse réussie doit inclure les paramètres token_type, access_token et expires_in.</span><span class="sxs-lookup"><span data-stu-id="28825-151">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="28825-152">Routage : mappage du client AAD au point de terminaison du fournisseur</span><span class="sxs-lookup"><span data-stu-id="28825-152">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="28825-153">L’application patients se connecte à un service partenaire via un point de terminaison unique.</span><span class="sxs-lookup"><span data-stu-id="28825-153">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="28825-154">Le service partenaire possède et gère un mécanisme pour mapper chaque client Microsoft (ID de client AAD) à un fournisseur de services de santé correspondant (serveur FHIR) sur lequel le service de partenariat travaille.</span><span class="sxs-lookup"><span data-stu-id="28825-154">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="28825-155">Le fait de mapper le client AAD à un point de terminaison fournisseur utilise l’ID de locataire AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="28825-155">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="28825-156">L’application patients transmet l’ID de locataire dans l’étendue, lors de la demande d’un jeton d’accès pour chaque demande.</span><span class="sxs-lookup"><span data-stu-id="28825-156">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="28825-157">Le service partenaire conserve le mappage de l’ID de locataire au point de terminaison fournisseur et redirige les demandes vers un point de terminaison fournisseur en fonction de l’ID de locataire.</span><span class="sxs-lookup"><span data-stu-id="28825-157">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="28825-158">Pour ce faire, le partenaire prend en charge la configuration à la fin (manuellement ou par le biais d’un portail dans le cadre de l’intégration d’organisations de fournisseur à sa plateforme d’interopérabilité).</span><span class="sxs-lookup"><span data-stu-id="28825-158">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="28825-159">Le flux de travail d’authentification et de routage est indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="28825-159">The Authentication and Routing workflow is shown below:</span></span>

![Diagramme du flux de travail d’authentification et de routage](../../media/Patient-app-6.png)

1. <span data-ttu-id="28825-161">Demande d’un jeton d’accès d’application en envoyant :</span><span class="sxs-lookup"><span data-stu-id="28825-161">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="28825-162">Répondez avec un jeton d’application :</span><span class="sxs-lookup"><span data-stu-id="28825-162">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="28825-163">Demander des données protégées avec un jeton d’accès.</span><span class="sxs-lookup"><span data-stu-id="28825-163">Request protected data with Access token.</span></span>
4. <span data-ttu-id="28825-164">Message d’autorisation : sélectionnez le serveur FHIR approprié pour le routage à partir de l’ID de locataire dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="28825-164">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="28825-165">Envoie les données protégées de l’application à partir du serveur FHIR autorisé après authentification auprès du jeton de l’application.</span><span class="sxs-lookup"><span data-stu-id="28825-165">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="28825-166">Implément</span><span class="sxs-lookup"><span data-stu-id="28825-166">Interfaces</span></span>

<span data-ttu-id="28825-167">Les appels et champs spécifiques utilisés par l’application patients sont décrits dans les articles suivants.</span><span class="sxs-lookup"><span data-stu-id="28825-167">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="28825-168">Sélectionnez l’interface applicable aux API Server/FHIR de votre FHIR.</span><span class="sxs-lookup"><span data-stu-id="28825-168">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="28825-169">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="28825-169">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="28825-170">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="28825-170">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="28825-171">Performances et fiabilité</span><span class="sxs-lookup"><span data-stu-id="28825-171">Performance and Reliability</span></span>

<span data-ttu-id="28825-172">Même si l’application patients est en préversion privée, il n’existe aucune garantie quant aux performances de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="28825-172">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="28825-173">Les facteurs de performance incluent les latences relatives de tous les tronçons impliqués dans le flux de travail, en partant du DMI dans l’environnement du système d’intégrité, vers le partenaire d’interopérabilité et leur infra, y compris le serveur FHIR et vers l’application Office 365 écosystème et patients.</span><span class="sxs-lookup"><span data-stu-id="28825-173">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Illustration des performances des partenaires d’interopérabilité](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="28825-175">Commencer à utiliser FHIR</span><span class="sxs-lookup"><span data-stu-id="28825-175">Get started with FHIR</span></span>  

<span data-ttu-id="28825-176">Si vous débutez sur FHIR et que vous avez besoin d’accéder facilement à un serveur FHIR que vous pouvez exposer à l’interface d’intégration DMI de Microsoft Teams, Microsoft dispose d’un serveur FHIR Open-source disponible pour tous les développeurs.</span><span class="sxs-lookup"><span data-stu-id="28825-176">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="28825-177">Reportez-vous à l’article [qu’est-ce que FHIR Server pour Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) pour en savoir plus sur le serveur Open source FHIR fourni par Microsoft et le déploiement pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="28825-177">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="28825-178">Vous pouvez également utiliser l’environnement de bac à sable (sandbox) HSPC ouvert pour créer un DMI qui prend également en charge un serveur Open FHIR</span><span class="sxs-lookup"><span data-stu-id="28825-178">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="28825-179">Nous vous recommandons de lire la [documentation de bac à sable (sandbox) hspc](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="28825-179">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="28825-180">Non seulement le bac à sable (sandbox) offre une méthode simple, orientée interface utilisateur et conviviale pour la création, l’ajout et la modification de patients.</span><span class="sxs-lookup"><span data-stu-id="28825-180">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 