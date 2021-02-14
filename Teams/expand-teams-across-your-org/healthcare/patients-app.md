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
description: Découvrez comment intégrer des enregistrements médicaux électroniques dans l’application Patients de Microsoft Teams à l’aide d’API FEMBA.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803542"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="628d9-103">Intégration des dossiers médicaux électroniques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="628d9-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="628d9-104">À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’application [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="628d9-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="628d9-105">Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui constitue le fond de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="628d9-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="628d9-106">Toutes les données associées à l’application Patients sont conservées dans ce groupe, mais ne peuvent plus être accessibles via l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="628d9-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="628d9-107">Les utilisateurs peuvent re-créer leurs listes à l’aide de [l’application Listes.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="628d9-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="628d9-108">Avec les listes, les équipes de soins de votre organisation de soins de santé peuvent créer des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients.</span><span class="sxs-lookup"><span data-stu-id="628d9-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="628d9-109">Consultez le modèle Patients dans Listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="628d9-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="628d9-110">Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, voir [l’application Gérer les listes.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="628d9-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="628d9-111">Cet article est destiné à un développeur informatique de santé général intéressé par l’utilisation d’API F AP API sur un système d’informations médicales pour se connecter à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="628d9-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="628d9-112">Cela permettra des scénarios de coordination des soins qui correspondent aux besoins d’une organisation de soins de santé.</span><span class="sxs-lookup"><span data-stu-id="628d9-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="628d9-113">Les articles liés documentent les spécifications de l’interface FEMBA pour l’application Patients de Microsoft Teams, et les sections suivantes expliquent ce qui est nécessaire pour la configuration d’un serveur FEMBA et la connexion à l’application Patients dans votre environnement de développement ou client.</span><span class="sxs-lookup"><span data-stu-id="628d9-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="628d9-114">Vous devez également être familiarisé avec la documentation du serveur F INF que vous avez choisi, laquelle doit être l’une des options prise en charge :</span><span class="sxs-lookup"><span data-stu-id="628d9-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="628d9-115">Datica (via son [offre CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="628d9-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="628d9-116">Infor Premierrleaf (via le [pont Infor FEMBA)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="628d9-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="628d9-117">Red mail (via le [serveur R^FEMBA)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="628d9-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="628d9-118">Microsoft (par le biais [de Corolar sur FEMBA)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="628d9-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="628d9-119">Ce processus n’inclut pas les étapes qui utilisent le Centre d’administration Microsoft Teams ou les cmdlets PowerShell pour activer les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="628d9-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="628d9-120">La configuration est entièrement effectuée sur le côté serveur/service FEMBA et dans le client de l’application Patients.</span><span class="sxs-lookup"><span data-stu-id="628d9-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="628d9-121">Voici l’architecture de l’application Patients illustrée ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="628d9-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramme de l’architecture de l’application Patients](../../media/patients-app-architecture.png)

<span data-ttu-id="628d9-123">Les sections suivantes expliquent les conditions requises de la couche d’accès aux données uniquement pour l’application Patients qu’un serveur FEMBA (ou API F HEP) doit respecter pour s’intégrer à l’application Patients, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="628d9-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="628d9-124">Attentes en matière d’authentification des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="628d9-124">Expectations around user authentication</span></span>
- <span data-ttu-id="628d9-125">Exigences fonctionnelles et techniques de l’interface d’intégration</span><span class="sxs-lookup"><span data-stu-id="628d9-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="628d9-126">Attentes en matière de performances et de fiabilité</span><span class="sxs-lookup"><span data-stu-id="628d9-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="628d9-127">Attentes autour des ressources FEMBA à prendre en charge pour l’application Patients</span><span class="sxs-lookup"><span data-stu-id="628d9-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="628d9-128">Processus d’intégration et modèle d’engagement attendu</span><span class="sxs-lookup"><span data-stu-id="628d9-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="628d9-129">Mise en place de la FEMBA et problèmes courants rencontrés avec l’application Patients</span><span class="sxs-lookup"><span data-stu-id="628d9-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="628d9-130">Conditions requises pour la prochaine itération de l’application Patients</span><span class="sxs-lookup"><span data-stu-id="628d9-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="628d9-131">Dans les sections suivantes, le terme « partenaire » ou « partenaire Interop » est utilisé pour faire référence à n’importe quelle organisation tierce qui autorise l’intégration aux systèmes EHR pour l’application Patients via FEMBA et implémente un serveur FEMBA pour qu’il corresponde aux spécifications répertoriées.</span><span class="sxs-lookup"><span data-stu-id="628d9-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="628d9-132">Exigences fonctionnelles et techniques</span><span class="sxs-lookup"><span data-stu-id="628d9-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="628d9-133">Authentification</span><span class="sxs-lookup"><span data-stu-id="628d9-133">Authentication</span></span>  

<span data-ttu-id="628d9-134">L’autorisation  au niveau de l’application sans prise en charge de l’autorisation au niveau utilisateur est le moyen le plus souvent pris en charge pour effectuer des transformations de données et exposer les connexions aux données d’un réseau d’entreprise via FEMBA, même si le système EHR peut implémenter l’autorisation au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="628d9-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="628d9-135">Le partenaire Interop Service obtient un accès élevé aux données EHR et, lorsqu’ils exposent les mêmes données que les ressources FEMBA appropriées, aucun contexte d’autorisation n’est transmis à la clientèle de services Interop (l’application Patients) intégrée au service ou à la plateforme Interop.</span><span class="sxs-lookup"><span data-stu-id="628d9-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="628d9-136">L’application Patients ne pourra pas appliquer l’autorisation au niveau utilisateur, mais prend en charge l’authentification des applications pour l’authentification des applications entre l’application Patients et le service du partenaire Interop.</span><span class="sxs-lookup"><span data-stu-id="628d9-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="628d9-137">Le modèle d’authentification d’application à application est décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="628d9-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="628d9-138">L’authentification de service à service doit être effectuée via le flux d’informations d’identification du [client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="628d9-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="628d9-139">Le service partenaire doit fournir les services suivants :</span><span class="sxs-lookup"><span data-stu-id="628d9-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="628d9-140">Le service partenaire permet à l’application Patients de créer un compte avec le partenaire, ce qui permet à l’application Patients de générer et de posséder des client_secret et client_id, gérés via un portail d’inscription d’authentification sur le serveur d’authentification du partenaire.</span><span class="sxs-lookup"><span data-stu-id="628d9-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="628d9-141">Le service partenaire est propriétaire du système d’authentification/autorisation, qui accepte et vérifie (authentifier) les informations d’identification client fournies et donne un jeton d’accès avec l’indication du client dans l’étendue, comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="628d9-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="628d9-142">Pour des raisons de sécurité ou en cas de violation secrète, l’application Patients peut générer à nouveau l’information secrète et invalider ou supprimer l’ancien secret (des exemples identiques sont disponibles dans le portail Azure - Inscription d’application AAD).</span><span class="sxs-lookup"><span data-stu-id="628d9-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="628d9-143">Le point de terminaison de métadonnées hébergeant l’instruction de conformité doit être non authentifié, il doit être accessible sans jeton d’authentification.</span><span class="sxs-lookup"><span data-stu-id="628d9-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="628d9-144">Le service partenaire fournit le point de terminaison de jeton pour l’application Patients afin de demander un jeton d’accès à l’aide d’un flux d’informations d’identification client.</span><span class="sxs-lookup"><span data-stu-id="628d9-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="628d9-145">L’URL de jeton conformément au serveur d’autorisation doit faire partie de l’instruction de conformité (fonctionnalité) FEMBA récupérée à partir des métadonnées sur le serveur F INF, comme dans l’exemple ci-après :</span><span class="sxs-lookup"><span data-stu-id="628d9-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="628d9-146">Une demande de jeton d’accès se compose des paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="628d9-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="628d9-147">Le service partenaire fournit les client_id et client_secret Patients, gérées via un portail d’inscription d’erth du côté du partenaire.</span><span class="sxs-lookup"><span data-stu-id="628d9-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="628d9-148">Le service partenaire fournit le point de terminaison pour demander un jeton d’accès à l’aide d’un flux d’informations d’identification client.</span><span class="sxs-lookup"><span data-stu-id="628d9-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="628d9-149">Une réponse réussie doit inclure les paramètres token_type, access_token et expires_in réponses.</span><span class="sxs-lookup"><span data-stu-id="628d9-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="628d9-150">Routage : mappage du client AAD au point de terminaison fournisseur</span><span class="sxs-lookup"><span data-stu-id="628d9-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="628d9-151">L’application Patients se connecte à un service partenaire via un seul point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="628d9-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="628d9-152">Le service partenaire est le propriétaire et le maintien d’un mécanisme permettant d’associer chaque client Microsoft (ID de locataire AAD) à un fournisseur de soins de santé (FEMBA) approprié avec qui le service partenaire travaille.</span><span class="sxs-lookup"><span data-stu-id="628d9-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="628d9-153">Le mappage du client AAD à un point de terminaison de fournisseur utilise l’ID de locataire AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="628d9-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="628d9-154">L’application Patients transmet l’ID de locataire dans l’étendue, lors de la demande d’un jeton d’accès pour chaque demande.</span><span class="sxs-lookup"><span data-stu-id="628d9-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="628d9-155">Le service partenaire conserve le mappage de l’ID de locataire avec le point de terminaison du fournisseur et redirige les demandes vers un point de terminaison de fournisseur sur la base de l’ID de locataire.</span><span class="sxs-lookup"><span data-stu-id="628d9-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="628d9-156">Pour ce faire, le partenaire prend en charge la configuration de son côté (manuellement ou via un portail dans le cadre de l’intégration des organisations du fournisseur à leur plateforme Interop).</span><span class="sxs-lookup"><span data-stu-id="628d9-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="628d9-157">Le flux de travail d’authentification et de routage s’affiche ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="628d9-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagramme du flux de travail d’authentification et de routage](../../media/Patient-app-6.png)

1. <span data-ttu-id="628d9-159">Demandez le jeton d’accès à l’application en envoyant :</span><span class="sxs-lookup"><span data-stu-id="628d9-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="628d9-160">Répondre avec un jeton d’application :</span><span class="sxs-lookup"><span data-stu-id="628d9-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="628d9-161">Demander des données protégées avec un jeton Access.</span><span class="sxs-lookup"><span data-stu-id="628d9-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="628d9-162">Message d’autorisation : sélectionnez le serveur FEMBA approprié vers qui router à partir de l’ID de client dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="628d9-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="628d9-163">Envoie les données protégées par l’application à partir du serveur FEMBA autorisé après l’authentification avec le jeton d’application.</span><span class="sxs-lookup"><span data-stu-id="628d9-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="628d9-164">Interfaces</span><span class="sxs-lookup"><span data-stu-id="628d9-164">Interfaces</span></span>

<span data-ttu-id="628d9-165">Des appels et des champs spécifiques utilisés par l’application Patients sont documentés dans les articles suivants.</span><span class="sxs-lookup"><span data-stu-id="628d9-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="628d9-166">Sélectionnez l’interface applicable à votre serveur FEMBA/API FEMBA.</span><span class="sxs-lookup"><span data-stu-id="628d9-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="628d9-167">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="628d9-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="628d9-168">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="628d9-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="628d9-169">Performances et fiabilité</span><span class="sxs-lookup"><span data-stu-id="628d9-169">Performance and Reliability</span></span>

<span data-ttu-id="628d9-170">Si l’application Patients est en prévisualisation privée, il n’y a aucune garantie pour les performances de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="628d9-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="628d9-171">Les facteurs de performances comprennent les latencies relatives de tous les sauts impliqués dans le flux de travail, à partir de l’ehr dans l’environnement du système d’santé, au partenaire Interop et à son infrastructure, y compris le serveur FEMBA, puis à l’écosystème d’Office 365 et l’application Patients.</span><span class="sxs-lookup"><span data-stu-id="628d9-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Illustration des performances des partenaires Interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="628d9-173">Commencer à travailler avec FEMBA</span><span class="sxs-lookup"><span data-stu-id="628d9-173">Get started with FHIR</span></span>  

<span data-ttu-id="628d9-174">Si vous débutez avec FEMBA et avez besoin d’un accès facile à un serveur FEMBA que vous pouvez exposer à l’interface d’intégration EHR de Microsoft Teams, Microsoft dispose d’un serveur FEMBA open source disponible pour tous les développeurs.</span><span class="sxs-lookup"><span data-stu-id="628d9-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="628d9-175">Consultez [l’article](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) Qu’est-ce que FEMBA Server pour Azure ? Pour en savoir plus sur le serveur open source FEMBA disponible auprès de Microsoft et le déployer pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="628d9-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="628d9-176">Vous pouvez également utiliser l’environnement EHR de bac à sable ouvert HSPC pour créer un ehr qui prend également en charge un serveur FPV ouvert et l’utiliser pour jouer avec l’application Patients.</span><span class="sxs-lookup"><span data-stu-id="628d9-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="628d9-177">Nous vous recommandons de lire la documentation en bac à sable [HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="628d9-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="628d9-178">Non seulement le bac à sable fournit-il un moyen simple, orienté IU et convivial de créer, d’ajouter et de modifier Patients, mais également de vous fournir plusieurs exemples pour commencer.</span><span class="sxs-lookup"><span data-stu-id="628d9-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
