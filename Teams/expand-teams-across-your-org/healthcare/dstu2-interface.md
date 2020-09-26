---
title: Application patients et interface DSTU2 d’intégration DMI
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
description: Apprenez-en davantage sur la spécification de l’interface DSTU2 dans Teams, notamment la configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fbbff4eda0eb1426bdf92068d95ccf00abe62a61
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277266"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="8d726-103">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="8d726-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d726-104">**En vigueur le 30 septembre 2020, l’application patients sera déconseillée et les utilisateurs ne pourront plus l’installer à partir de l’App Store d’Teams. Nous vous encourageons à commencer à utiliser l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans teams dès aujourd’hui.**</span><span class="sxs-lookup"><span data-stu-id="8d726-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="8d726-105">Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe.</span><span class="sxs-lookup"><span data-stu-id="8d726-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="8d726-106">Lorsque l’application patients est supprimée, toutes les données qui lui sont associées seront conservées dans ce groupe, mais ne seront plus accessibles par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d726-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="8d726-107">Les utilisateurs actuels peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="8d726-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="8d726-108">L' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) est préinstallée pour tous les utilisateurs d’teams et est disponible sous la forme d’une tabulation dans chaque équipe ou canal.</span><span class="sxs-lookup"><span data-stu-id="8d726-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="8d726-109">Les listes permettent aux équipes de soins de créer des listes de patients à l’aide du modèle de patients intégré, de zéro à partir de zéro ou d’importer des données dans Excel.</span><span class="sxs-lookup"><span data-stu-id="8d726-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="8d726-110">Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="8d726-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="8d726-111">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="8d726-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="8d726-112">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d726-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="8d726-113">Patient</span><span class="sxs-lookup"><span data-stu-id="8d726-113">Patient</span></span>](#patient)
- [<span data-ttu-id="8d726-114">Déterminée</span><span class="sxs-lookup"><span data-stu-id="8d726-114">Observation</span></span>](#observation)
- [<span data-ttu-id="8d726-115">Condition</span><span class="sxs-lookup"><span data-stu-id="8d726-115">Condition</span></span>](#condition)
- [<span data-ttu-id="8d726-116">Connaître</span><span class="sxs-lookup"><span data-stu-id="8d726-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="8d726-117">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="8d726-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="8d726-118">Articles</span><span class="sxs-lookup"><span data-stu-id="8d726-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="8d726-119">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="8d726-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="8d726-120">Emplacement</span><span class="sxs-lookup"><span data-stu-id="8d726-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="8d726-121">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout.</span><span class="sxs-lookup"><span data-stu-id="8d726-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="8d726-122">Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="8d726-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="8d726-123">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources ont une offre groupée (lot) de requêtes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="8d726-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="8d726-124">Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="8d726-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="8d726-125">Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="8d726-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="8d726-126">Toutes les ressources FHIR suivantes doivent être accessibles par référence directe aux ressources.</span><span class="sxs-lookup"><span data-stu-id="8d726-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="8d726-127">Jeu de champs requis de conformité</span><span class="sxs-lookup"><span data-stu-id="8d726-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="8d726-128">Le serveur FHIR doit mettre en œuvre la déclaration de conformité afin d’avoir une synthèse factuelle de ses capacités.</span><span class="sxs-lookup"><span data-stu-id="8d726-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="8d726-129">Nous attendons les paramètres ci-dessous dans un DSTU2 FHIR Server :</span><span class="sxs-lookup"><span data-stu-id="8d726-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="8d726-130">LAISSER</span><span class="sxs-lookup"><span data-stu-id="8d726-130">REST</span></span>
   1. <span data-ttu-id="8d726-131">Veille</span><span class="sxs-lookup"><span data-stu-id="8d726-131">Mode</span></span>
   2. <span data-ttu-id="8d726-132">Interaction</span><span class="sxs-lookup"><span data-stu-id="8d726-132">Interaction</span></span>
   3. <span data-ttu-id="8d726-133">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="8d726-133">Resource: Type</span></span>
   4. <span data-ttu-id="8d726-134">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="8d726-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="8d726-135">FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)</span><span class="sxs-lookup"><span data-stu-id="8d726-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="8d726-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="8d726-137">Patient</span><span class="sxs-lookup"><span data-stu-id="8d726-137">Patient</span></span>

<span data-ttu-id="8d726-138">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="8d726-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="8d726-139">Name. Family</span><span class="sxs-lookup"><span data-stu-id="8d726-139">Name.Family</span></span>
2. <span data-ttu-id="8d726-140">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="8d726-140">Name.Given</span></span>
3. <span data-ttu-id="8d726-141">Public</span><span class="sxs-lookup"><span data-stu-id="8d726-141">Gender</span></span>
4. <span data-ttu-id="8d726-142">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="8d726-142">BirthDate</span></span>
5. <span data-ttu-id="8d726-143">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="8d726-143">MRN (Identifier)</span></span>

<span data-ttu-id="8d726-144">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="8d726-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="8d726-145">Name.Use</span></span>
2. <span data-ttu-id="8d726-146">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="8d726-146">Name.Prefix</span></span>
3. <span data-ttu-id="8d726-147">CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="8d726-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="8d726-148">Demande : obtenez <fhir-Server>/patient/<patient-ID></span><span class="sxs-lookup"><span data-stu-id="8d726-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="8d726-149">Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>",.</span><span class="sxs-lookup"><span data-stu-id="8d726-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="8d726-150">.</span><span class="sxs-lookup"><span data-stu-id="8d726-150">.</span></span>
      <span data-ttu-id="8d726-151">.</span><span class="sxs-lookup"><span data-stu-id="8d726-151">.</span></span>
      <span data-ttu-id="8d726-152">"nom" : [{"utilisation" : "officiel", "préfixe" : ["Mr"], "famille" : ["Chau"], "en"; ";" ";" ";" ";" officiel "," tapez " : {" codage " : [{" système " :" https://hl7.org/fhir/v2/0203 "," code " :" 1234567 "}])," valeur " :" "}]," sexe "," careProvider "," DateNaissance " :" 1957-06-05 "," " : [{" Display " :" Jane Dupont "}],}</span><span class="sxs-lookup"><span data-stu-id="8d726-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="8d726-153">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="8d726-154">ID</span><span class="sxs-lookup"><span data-stu-id="8d726-154">id</span></span>
2. <span data-ttu-id="8d726-155">famille : contient = (recherche les patients dont le nom de famille contient la valeur.)</span><span class="sxs-lookup"><span data-stu-id="8d726-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="8d726-156">accordé =\<substring></span><span class="sxs-lookup"><span data-stu-id="8d726-156">given=\<substring></span></span>
4. <span data-ttu-id="8d726-157">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="8d726-157">name=\<substring></span></span>
5. <span data-ttu-id="8d726-158">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="8d726-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="8d726-159">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="8d726-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="8d726-160">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_ le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="8d726-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="8d726-161">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="8d726-161">identifier=\<mrn></span></span>

<span data-ttu-id="8d726-162">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="8d726-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="8d726-163">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="8d726-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="8d726-164">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="8d726-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="8d726-165">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR</span><span class="sxs-lookup"><span data-stu-id="8d726-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="8d726-166">Nom</span><span class="sxs-lookup"><span data-stu-id="8d726-166">Name</span></span>
- <span data-ttu-id="8d726-167">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="8d726-167">Birthdate</span></span>

<span data-ttu-id="8d726-168">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="8d726-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="8d726-169">Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="8d726-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="8d726-170">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>",.</span><span class="sxs-lookup"><span data-stu-id="8d726-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="8d726-171">.</span><span class="sxs-lookup"><span data-stu-id="8d726-171">.</span></span>
      <span data-ttu-id="8d726-172">.</span><span class="sxs-lookup"><span data-stu-id="8d726-172">.</span></span>
      <span data-ttu-id="8d726-173">"entrée" : [{"ressource" : {"resourceType" : "patient", "ID" : "ID patient-ID>", "nom" : [{"texte" : "Hugh Chau", "<famille" : [Chau "]," nom " : [" Hugh "]}]," sexe " :" mâle "," DateNaissance " :" 1957-06-05 "}," recherche " : {" mode " :" match "}})}</span><span class="sxs-lookup"><span data-stu-id="8d726-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="8d726-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="8d726-175">Déterminée</span><span class="sxs-lookup"><span data-stu-id="8d726-175">Observation</span></span>

<span data-ttu-id="8d726-176">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :</span><span class="sxs-lookup"><span data-stu-id="8d726-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="8d726-177">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="8d726-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="8d726-178">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="8d726-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="8d726-179">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="8d726-179">ValueQuantity.Value</span></span>

<span data-ttu-id="8d726-180">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="8d726-181">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="8d726-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="8d726-182">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="8d726-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="8d726-183">S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.</span><span class="sxs-lookup"><span data-stu-id="8d726-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="8d726-184">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-185">patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="8d726-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="8d726-186">Trier : DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="8d726-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="8d726-187">L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="8d726-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="8d726-188">Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&_sort :d Échap = date&catégorie = vitaux-signes</span><span class="sxs-lookup"><span data-stu-id="8d726-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="8d726-189">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "tapez" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-id de ressource", "category" : {"code" : {{code " :" "Pseudo"> = "" code " : {" codage " : [{" système " :" http://loinc.org "," code " :" 39156-5 "," Display " :" BMI "}),}," effectiveDateTime " :" 2009-12-01 "," valueQuantity " : {" value " : 34,4," Unit " :" kg/m2 "," système " :" http://unitsofmeasure.org "," code " :" kg/m2 "}},},.</span><span class="sxs-lookup"><span data-stu-id="8d726-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="8d726-190">.</span><span class="sxs-lookup"><span data-stu-id="8d726-190">.</span></span>
        <span data-ttu-id="8d726-191">.</span><span class="sxs-lookup"><span data-stu-id="8d726-191">.</span></span>
      <span data-ttu-id="8d726-192">] }</span><span class="sxs-lookup"><span data-stu-id="8d726-192">] }</span></span>

* * *

<span data-ttu-id="8d726-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="8d726-194">Condition</span><span class="sxs-lookup"><span data-stu-id="8d726-194">Condition</span></span>

<span data-ttu-id="8d726-195">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="8d726-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="8d726-196">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="8d726-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="8d726-197">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8d726-198">Date d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="8d726-198">Date Recorded</span></span>
2. <span data-ttu-id="8d726-199">Minimal</span><span class="sxs-lookup"><span data-stu-id="8d726-199">Severity</span></span>

<span data-ttu-id="8d726-200">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-201">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="8d726-201">patient=\<patient id></span></span>
2. <span data-ttu-id="8d726-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="8d726-202">_count=\<max results></span></span>

<span data-ttu-id="8d726-203">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="8d726-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="8d726-204">Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="8d726-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="8d726-205">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "condition", "ID" : "<-ID>", "code" : {"Coding" : [{"System" : " http://snomed.info/sct ", "code" : "386033004", "Display" : "neuropathie (dommage nerveux)"}]}, "dateRecorded" : "2018-09-17", "gravité" : {"codage" : [{"système" : " http://snomed.info/sct ", "code" : "24484000", "Display" : "sévère"}]}}})}</span><span class="sxs-lookup"><span data-stu-id="8d726-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="8d726-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="8d726-207">Connaître</span><span class="sxs-lookup"><span data-stu-id="8d726-207">Encounter</span></span>

<span data-ttu-id="8d726-208">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :</span><span class="sxs-lookup"><span data-stu-id="8d726-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="8d726-209">État</span><span class="sxs-lookup"><span data-stu-id="8d726-209">Status</span></span>
2. <span data-ttu-id="8d726-210">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="8d726-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="8d726-211">De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="8d726-212">Période. début</span><span class="sxs-lookup"><span data-stu-id="8d726-212">Period.Start</span></span>
2. <span data-ttu-id="8d726-213">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="8d726-213">Location[0].Location.Display</span></span>

<span data-ttu-id="8d726-214">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-215">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="8d726-215">patient=\<patient id></span></span>
2. <span data-ttu-id="8d726-216">_sort : DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="8d726-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="8d726-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="8d726-217">_count=\<max results></span></span>

<span data-ttu-id="8d726-218">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="8d726-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="8d726-219">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8d726-219">Each encounter references a location resource.</span></span> <span data-ttu-id="8d726-220">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="8d726-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="8d726-221">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="8d726-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="8d726-222">Demande : obtenez <fhir-Server>/Encounter ? patient =<patient-ID>&_sort :d Échap = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="8d726-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="8d726-223">Réponse : {"resourceType" : "bundle", "type", "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "rencontre", "identifiant" : "<-ID>", "identificateur" : [{"utiliser" : "officiel", "valeur" <id> Status " :" incomplet "," type " : [{" Coding " : [{" Display " :" rendez-vous "}],})," patient " : {" Réf "<>"}, "période" : {"début" : "09/17/2018 1:00:00 PM"}; "lieu" : [{"lieu" : {"Display" : "Clinic-ent"}})}</span><span class="sxs-lookup"><span data-stu-id="8d726-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="8d726-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="8d726-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="8d726-225">AllergyIntolerance</span></span>

<span data-ttu-id="8d726-226">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :</span><span class="sxs-lookup"><span data-stu-id="8d726-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="8d726-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="8d726-227">Code.Text</span></span>
2. <span data-ttu-id="8d726-228">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="8d726-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="8d726-229">État</span><span class="sxs-lookup"><span data-stu-id="8d726-229">Status</span></span>

<span data-ttu-id="8d726-230">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="8d726-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="8d726-231">RecordedDate</span></span>
2. <span data-ttu-id="8d726-232">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="8d726-232">Note.Text</span></span>
3. <span data-ttu-id="8d726-233">Réaction [...]. Substance. texte</span><span class="sxs-lookup"><span data-stu-id="8d726-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="8d726-234">Réaction [...]. Manifeste [...]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="8d726-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="8d726-235">Text. div</span><span class="sxs-lookup"><span data-stu-id="8d726-235">Text.Div</span></span>

<span data-ttu-id="8d726-236">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-237">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="8d726-237">Patient =  \<patient id></span></span>

<span data-ttu-id="8d726-238">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="8d726-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="8d726-239">Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="8d726-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="8d726-240">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 1, "entry" : "AllergyIntolerance", "ID" : "<-ID>", "recordedDate" : "" 2018-09-17T07:00:00.000 Z "," substance " : {" texte " :" Cashew écrous "}," statut " :" confirmé "," réaction " : [{" substance " : {" texte " :" Cashew d’écrou d’écrou allergique "}," manifeste " : [{" texte " :" anaphylactic réaction "}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="8d726-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="8d726-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="8d726-242">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="8d726-242">Medication Order</span></span>

<span data-ttu-id="8d726-243">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :</span><span class="sxs-lookup"><span data-stu-id="8d726-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="8d726-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="8d726-244">DateWritten</span></span>
2. <span data-ttu-id="8d726-245">Ordonnateur. Display</span><span class="sxs-lookup"><span data-stu-id="8d726-245">Prescriber.Display</span></span>
3. <span data-ttu-id="8d726-246">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="8d726-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="8d726-247">Medication. Text (si concept)</span><span class="sxs-lookup"><span data-stu-id="8d726-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="8d726-248">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="8d726-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="8d726-249">DateEnded</span></span>
2. <span data-ttu-id="8d726-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="8d726-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="8d726-251">Text. div</span><span class="sxs-lookup"><span data-stu-id="8d726-251">Text.Div</span></span>

<span data-ttu-id="8d726-252">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-253">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="8d726-253">patient=\<patient id></span></span>
2. <span data-ttu-id="8d726-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="8d726-254">_count=\<max results></span></span>

<span data-ttu-id="8d726-255">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="8d726-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="8d726-256">Demande : obtenez <fhir-Server>/MedicationOrder ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="8d726-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="8d726-257">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "MedicationOrder", "ID" : "<-ID de ressource>", "dateWritten" : "2018-09-17", "medicationCodeableConcept" : {"Text" : "Lisinopril 20 MG de comprimé"}, "" : "Jane Dupont"}, "dosageInstruction" : [{"Text" : "1 quotidien"}</span><span class="sxs-lookup"><span data-stu-id="8d726-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="8d726-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="8d726-259">Articles</span><span class="sxs-lookup"><span data-stu-id="8d726-259">Coverage</span></span>

<span data-ttu-id="8d726-260">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="8d726-261">Payor</span><span class="sxs-lookup"><span data-stu-id="8d726-261">Payor</span></span>

<span data-ttu-id="8d726-262">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8d726-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="8d726-263">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="8d726-263">patient=\<patient id></span></span>

<span data-ttu-id="8d726-264">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="8d726-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="8d726-265">Demande : obtenez <fhir-Server>/Coverage ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="8d726-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="8d726-266">Réponse : {"resourceType" : "bundle", "tapez" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "couverture", "ID" : "<-id de ressource", "plan" : "pas d'> assurance primaire", "abonné" : {"référence" : "patient/<patient-ID>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="8d726-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="8d726-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="8d726-268">Lieu</span><span class="sxs-lookup"><span data-stu-id="8d726-268">Location</span></span>

<span data-ttu-id="8d726-269">Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="8d726-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="8d726-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="8d726-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
