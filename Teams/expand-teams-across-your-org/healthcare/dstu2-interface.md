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
description: Intégration du DMI de l’application Microsoft teams
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153816"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="e4a0b-103">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="e4a0b-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="e4a0b-104">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="e4a0b-105">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="e4a0b-106">Patient</span><span class="sxs-lookup"><span data-stu-id="e4a0b-106">Patient</span></span>](#patient)
- [<span data-ttu-id="e4a0b-107">Déterminée</span><span class="sxs-lookup"><span data-stu-id="e4a0b-107">Observation</span></span>](#observation)
- [<span data-ttu-id="e4a0b-108">Condition</span><span class="sxs-lookup"><span data-stu-id="e4a0b-108">Condition</span></span>](#condition)
- [<span data-ttu-id="e4a0b-109">Connaître</span><span class="sxs-lookup"><span data-stu-id="e4a0b-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="e4a0b-110">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="e4a0b-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="e4a0b-111">Articles</span><span class="sxs-lookup"><span data-stu-id="e4a0b-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="e4a0b-112">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="e4a0b-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="e4a0b-113">Emplacement</span><span class="sxs-lookup"><span data-stu-id="e4a0b-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="e4a0b-114">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="e4a0b-115">Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="e4a0b-116">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources ont une offre groupée (lot) de requêtes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="e4a0b-117">Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="e4a0b-118">Pour plus d’informations et d’exemples [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction), voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="e4a0b-119">Toutes les ressources FHIR suivantes doivent être accessibles par référence directe aux ressources.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="e4a0b-120">Jeu de champs requis de conformité</span><span class="sxs-lookup"><span data-stu-id="e4a0b-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="e4a0b-121">Le serveur FHIR doit mettre en œuvre la déclaration de conformité afin d’avoir une synthèse factuelle de ses capacités.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="e4a0b-122">Nous attendons les paramètres ci-dessous dans un DSTU2 FHIR Server :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="e4a0b-123">LAISSER</span><span class="sxs-lookup"><span data-stu-id="e4a0b-123">REST</span></span>
   1. <span data-ttu-id="e4a0b-124">Veille</span><span class="sxs-lookup"><span data-stu-id="e4a0b-124">Mode</span></span>
   2. <span data-ttu-id="e4a0b-125">Interaction</span><span class="sxs-lookup"><span data-stu-id="e4a0b-125">Interaction</span></span>
   3. <span data-ttu-id="e4a0b-126">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="e4a0b-126">Resource: Type</span></span>
   4. <span data-ttu-id="e4a0b-127">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="e4a0b-128">FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="e4a0b-129">Pour [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="e4a0b-130">Patient</span><span class="sxs-lookup"><span data-stu-id="e4a0b-130">Patient</span></span>

<span data-ttu-id="e4a0b-131">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="e4a0b-132">Name. Family</span><span class="sxs-lookup"><span data-stu-id="e4a0b-132">Name.Family</span></span>
2. <span data-ttu-id="e4a0b-133">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="e4a0b-133">Name.Given</span></span>
3. <span data-ttu-id="e4a0b-134">Public</span><span class="sxs-lookup"><span data-stu-id="e4a0b-134">Gender</span></span>
4. <span data-ttu-id="e4a0b-135">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="e4a0b-135">BirthDate</span></span>
5. <span data-ttu-id="e4a0b-136">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-136">MRN (Identifier)</span></span>

<span data-ttu-id="e4a0b-137">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="e4a0b-138">Name. use</span><span class="sxs-lookup"><span data-stu-id="e4a0b-138">Name.Use</span></span>
2. <span data-ttu-id="e4a0b-139">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="e4a0b-139">Name.Prefix</span></span>
3. <span data-ttu-id="e4a0b-140">CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="e4a0b-141">Demande : obtenez <fhir-Server>/patient/<patient-ID></span><span class="sxs-lookup"><span data-stu-id="e4a0b-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="e4a0b-142">Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>",.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="e4a0b-143">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-143">.</span></span>
      <span data-ttu-id="e4a0b-144">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-144">.</span></span>
      <span data-ttu-id="e4a0b-145">"nom" : [{"utilisation" : "officiel", "préfixe" : ["Mr"], "famille" : ["Chau"], "en"; ";" ";" ";" ";" officiel "," tapez " : {" codage " : [{" système " :"https://hl7.org/fhir/v2/0203"," code " :" 1234567 "}])," valeur " :" "}]," sexe "," careProvider "," DateNaissance " :" 1957-06-05 "," " : [{" Display " :" Jane Dupont "}],}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="e4a0b-146">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-147">ID</span><span class="sxs-lookup"><span data-stu-id="e4a0b-147">id</span></span>
2. <span data-ttu-id="e4a0b-148">famille : contient = (recherche les patients dont le nom de famille contient la valeur.)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="e4a0b-149">fourni =\<sous-chaîne></span><span class="sxs-lookup"><span data-stu-id="e4a0b-149">given=\<substring></span></span>
4. <span data-ttu-id="e4a0b-150">name =\<sous-chaîne></span><span class="sxs-lookup"><span data-stu-id="e4a0b-150">name=\<substring></span></span>
5. <span data-ttu-id="e4a0b-151">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="e4a0b-152">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="e4a0b-153">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="e4a0b-154">identifiant =\<NRM></span><span class="sxs-lookup"><span data-stu-id="e4a0b-154">identifier=\<mrn></span></span>

<span data-ttu-id="e4a0b-155">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="e4a0b-156">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="e4a0b-157">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="e4a0b-158">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR</span><span class="sxs-lookup"><span data-stu-id="e4a0b-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="e4a0b-159">Nom</span><span class="sxs-lookup"><span data-stu-id="e4a0b-159">Name</span></span>
- <span data-ttu-id="e4a0b-160">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="e4a0b-160">Birthdate</span></span>

<span data-ttu-id="e4a0b-161">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="e4a0b-162">Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="e4a0b-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="e4a0b-163">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>",.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="e4a0b-164">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-164">.</span></span>
      <span data-ttu-id="e4a0b-165">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-165">.</span></span>
      <span data-ttu-id="e4a0b-166">"entrée" : [{"ressource" : {"resourceType" : "patient", "ID" : "ID patient-ID>", "nom" : [{"texte" : "Hugh Chau", "<famille" : [Chau "]," nom " : [" Hugh "]}]," sexe " :" mâle "," DateNaissance " :" 1957-06-05 "}," recherche " : {" mode " :" match "}})}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="e4a0b-167">Pour [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="e4a0b-168">Déterminée</span><span class="sxs-lookup"><span data-stu-id="e4a0b-168">Observation</span></span>

<span data-ttu-id="e4a0b-169">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="e4a0b-170">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="e4a0b-171">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="e4a0b-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="e4a0b-172">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="e4a0b-172">ValueQuantity.Value</span></span>

<span data-ttu-id="e4a0b-173">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="e4a0b-174">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="e4a0b-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="e4a0b-175">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="e4a0b-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="e4a0b-176">S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="e4a0b-177">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-178">patient =\<Réf patient\></span><span class="sxs-lookup"><span data-stu-id="e4a0b-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="e4a0b-179">Trier : DESC =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="e4a0b-180">période\></span><span class="sxs-lookup"><span data-stu-id="e4a0b-180">date\></span></span>

<span data-ttu-id="e4a0b-181">L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="e4a0b-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="e4a0b-182">Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&_sort :d Échap = date&catégorie = vitaux-signes</span><span class="sxs-lookup"><span data-stu-id="e4a0b-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="e4a0b-183">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "tapez" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-id de ressource", "category" : {"code" : {{code " :" "Pseudo"> = "" code " : {" codage " : [{" système " :"http://loinc.org"," code " :" 39156-5 "," Display " :" BMI "}),}," effectiveDateTime " :" 2009-12-01 "," valueQuantity " : {" value " : 34,4," Unit " :" kg/m2 "," système " :"http://unitsofmeasure.org"," code " :" kg/m2 "}},},.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="e4a0b-184">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-184">.</span></span>
        <span data-ttu-id="e4a0b-185">.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-185">.</span></span>
      <span data-ttu-id="e4a0b-186">] }</span><span class="sxs-lookup"><span data-stu-id="e4a0b-186">] }</span></span>

* * *

<span data-ttu-id="e4a0b-187">Pour [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="e4a0b-188">Condition</span><span class="sxs-lookup"><span data-stu-id="e4a0b-188">Condition</span></span>

<span data-ttu-id="e4a0b-189">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="e4a0b-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="e4a0b-190">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="e4a0b-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="e4a0b-191">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="e4a0b-192">Date d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="e4a0b-192">Date Recorded</span></span>
2. <span data-ttu-id="e4a0b-193">Minimal</span><span class="sxs-lookup"><span data-stu-id="e4a0b-193">Severity</span></span>

<span data-ttu-id="e4a0b-194">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-195">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="e4a0b-195">patient=\<patient id></span></span>
2. <span data-ttu-id="e4a0b-196">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="e4a0b-196">_count=\<max results></span></span>

<span data-ttu-id="e4a0b-197">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4a0b-198">Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="e4a0b-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="e4a0b-199">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "condition", "ID" : "<-ID de ressource-ID>", "code" : {"Coding" : [{"System"http://snomed.info/sct: "", "code" : "386033004", "Display" : "« syst" », "Display" : "2018-09-17", "dateRecorded", "" : "", "gravité" em " :"http://snomed.info/sct"," code " :" 24484000 "," Display " :" sévère "}]}}})}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="e4a0b-200">Pour [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="e4a0b-201">Connaître</span><span class="sxs-lookup"><span data-stu-id="e4a0b-201">Encounter</span></span>

<span data-ttu-id="e4a0b-202">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="e4a0b-203">État</span><span class="sxs-lookup"><span data-stu-id="e4a0b-203">Status</span></span>
2. <span data-ttu-id="e4a0b-204">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="e4a0b-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="e4a0b-205">De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="e4a0b-206">Période. début</span><span class="sxs-lookup"><span data-stu-id="e4a0b-206">Period.Start</span></span>
2. <span data-ttu-id="e4a0b-207">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="e4a0b-207">Location[0].Location.Display</span></span>

<span data-ttu-id="e4a0b-208">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-209">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="e4a0b-209">patient=\<patient id></span></span>
2. <span data-ttu-id="e4a0b-210">_sort : DESC =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="e4a0b-211">Date></span><span class="sxs-lookup"><span data-stu-id="e4a0b-211">date></span></span>
3. <span data-ttu-id="e4a0b-212">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="e4a0b-212">_count=\<max results></span></span>

<span data-ttu-id="e4a0b-213">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="e4a0b-214">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-214">Each encounter references a location resource.</span></span> <span data-ttu-id="e4a0b-215">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="e4a0b-216">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="e4a0b-217">Demande : obtenez <fhir-Server>/Encounter ? patient =<patient-ID>&_sort :d Échap = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="e4a0b-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="e4a0b-218">Réponse : {"ResourceType" : "bundle", "type" : "searchset", "total" : 1, "entrée" : [{"Resource" : "" ResourceType "=", "'ID" : "<-ID>", "identificateur" : [{"use" : "Official", "value" : ""<id>}], "Status" : "incomplet", "type" : [{"code" : [{"Display" : "rendez-vous"}],}], "patient" : "09/17/2018 1:00:00" = "patient/<patient-ID>              "location" : {"Display" : "Clinic-ENT"}})}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4a0b-219">Pour [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="e4a0b-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="e4a0b-220">AllergyIntolerance</span></span>

<span data-ttu-id="e4a0b-221">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="e4a0b-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="e4a0b-222">Code.Text</span></span>
2. <span data-ttu-id="e4a0b-223">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="e4a0b-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="e4a0b-224">État</span><span class="sxs-lookup"><span data-stu-id="e4a0b-224">Status</span></span>

<span data-ttu-id="e4a0b-225">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="e4a0b-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="e4a0b-226">RecordedDate</span></span>
2. <span data-ttu-id="e4a0b-227">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="e4a0b-227">Note.Text</span></span>
3. <span data-ttu-id="e4a0b-228">Réaction [...]. Substance. texte</span><span class="sxs-lookup"><span data-stu-id="e4a0b-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="e4a0b-229">Réaction [...]. Manifeste [...]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="e4a0b-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="e4a0b-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="e4a0b-230">Text.Div</span></span>

<span data-ttu-id="e4a0b-231">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-232">Patient = \<ID du patient></span><span class="sxs-lookup"><span data-stu-id="e4a0b-232">Patient =  \<patient id></span></span>

<span data-ttu-id="e4a0b-233">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4a0b-234">Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="e4a0b-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="e4a0b-235">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"Resource" : "" resourceType " :" AllergyIntolerance "," ID " :" <> d’ID de ressource "," recordedDate " :" 2018-09-17T07:00:00.000 Z "," substance " : {" texte " :" Cashew écrous "}," État " :" confirmé "," réaction " : [{" substance " : {" texte " :" Cashew d’extraction allergique sur " : [{" texte " :" réaction anaphylactic "}]}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4a0b-236">Pour [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="e4a0b-237">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="e4a0b-237">Medication Order</span></span>

<span data-ttu-id="e4a0b-238">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="e4a0b-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="e4a0b-239">DateWritten</span></span>
2. <span data-ttu-id="e4a0b-240">Ordonnateur. Display</span><span class="sxs-lookup"><span data-stu-id="e4a0b-240">Prescriber.Display</span></span>
3. <span data-ttu-id="e4a0b-241">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="e4a0b-242">Medication. Text (si concept)</span><span class="sxs-lookup"><span data-stu-id="e4a0b-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="e4a0b-243">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="e4a0b-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="e4a0b-244">DateEnded</span></span>
2. <span data-ttu-id="e4a0b-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="e4a0b-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="e4a0b-246">Text. div</span><span class="sxs-lookup"><span data-stu-id="e4a0b-246">Text.Div</span></span>

<span data-ttu-id="e4a0b-247">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-248">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="e4a0b-248">patient=\<patient id></span></span>
2. <span data-ttu-id="e4a0b-249">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="e4a0b-249">_count=\<max results></span></span>

<span data-ttu-id="e4a0b-250">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4a0b-251">Demande : obtenez <fhir-Server>/MedicationOrder ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="e4a0b-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="e4a0b-252">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "MedicationOrder", "ID" : "<-ID de ressource>", "dateWritten" : "2018-09-17", "medicationCodeableConcept" : {"Text" : "Lisinopril 20 MG de comprimé"}, "" : "Jane Dupont"}, "dosageInstruction" : [{"Text" : "1 quotidien"}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="e4a0b-253">Pour [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="e4a0b-254">Articles</span><span class="sxs-lookup"><span data-stu-id="e4a0b-254">Coverage</span></span>

<span data-ttu-id="e4a0b-255">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="e4a0b-256">Payor</span><span class="sxs-lookup"><span data-stu-id="e4a0b-256">Payor</span></span>

<span data-ttu-id="e4a0b-257">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="e4a0b-258">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="e4a0b-258">patient=\<patient id></span></span>

<span data-ttu-id="e4a0b-259">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e4a0b-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="e4a0b-260">Demande : obtenez <fhir-Server>/Coverage ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="e4a0b-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="e4a0b-261">Réponse : {"resourceType" : "bundle", "tapez" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "couverture", "ID" : "<-id de ressource", "plan" : "pas d'> assurance primaire", "abonné" : {"référence" : "patient/<patient-ID>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="e4a0b-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="e4a0b-262">Pour [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="e4a0b-263">Lieu</span><span class="sxs-lookup"><span data-stu-id="e4a0b-263">Location</span></span>

<span data-ttu-id="e4a0b-264">Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="e4a0b-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="e4a0b-265">Pour [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="e4a0b-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
