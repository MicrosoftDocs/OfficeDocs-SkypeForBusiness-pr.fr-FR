---
title: Application patients et interface STU3 d’intégration DMI
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
description: Apprenez-en davantage sur la spécification de l’interface STU3 dans Teams, notamment la configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35d887575ffb894b7a47e50511e6bd6c3a9a75d1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141197"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="3e00d-103">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="3e00d-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="3e00d-104">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="3e00d-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="3e00d-105">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e00d-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="3e00d-106">Patient</span><span class="sxs-lookup"><span data-stu-id="3e00d-106">Patient</span></span>](#patient)
- [<span data-ttu-id="3e00d-107">Déterminée</span><span class="sxs-lookup"><span data-stu-id="3e00d-107">Observation</span></span>](#observation)
- [<span data-ttu-id="3e00d-108">Condition</span><span class="sxs-lookup"><span data-stu-id="3e00d-108">Condition</span></span>](#condition)
- [<span data-ttu-id="3e00d-109">Connaître</span><span class="sxs-lookup"><span data-stu-id="3e00d-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="3e00d-110">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="3e00d-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="3e00d-111">Articles</span><span class="sxs-lookup"><span data-stu-id="3e00d-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="3e00d-112">[État de médication](#medication-request) (remplace le MedicationOrder dans la version DSTU2 du PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="3e00d-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="3e00d-113">Emplacement (les informations requises par cette ressource peuvent être intégrées à la rencontre)</span><span class="sxs-lookup"><span data-stu-id="3e00d-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="3e00d-114">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout); Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="3e00d-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="3e00d-115">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources publient une offre (BATCH) de requêtes dans l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="3e00d-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="3e00d-116">Le serveur traitera chaque demande et renverra une offre de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="3e00d-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="3e00d-117">Pour plus d’informations et d’exemples [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction), voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="3e00d-118">Instruction Capability</span><span class="sxs-lookup"><span data-stu-id="3e00d-118">Capability Statement</span></span>

<span data-ttu-id="3e00d-119">Voici les champs obligatoires obligatoires :</span><span class="sxs-lookup"><span data-stu-id="3e00d-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="3e00d-120">LAISSER</span><span class="sxs-lookup"><span data-stu-id="3e00d-120">REST</span></span>
   1. <span data-ttu-id="3e00d-121">Veille</span><span class="sxs-lookup"><span data-stu-id="3e00d-121">Mode</span></span>
   2. <span data-ttu-id="3e00d-122">Interaction</span><span class="sxs-lookup"><span data-stu-id="3e00d-122">Interaction</span></span>
   3. <span data-ttu-id="3e00d-123">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="3e00d-123">Resource: Type</span></span>
   4. <span data-ttu-id="3e00d-124">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="3e00d-124">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="3e00d-125">FhirVersion (notre code nécessite cela pour comprendre la version à laquelle nous devons faire pivoter.)</span><span class="sxs-lookup"><span data-stu-id="3e00d-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="3e00d-126">Pour [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="3e00d-127">Patient</span><span class="sxs-lookup"><span data-stu-id="3e00d-127">Patient</span></span>

<span data-ttu-id="3e00d-128">Voici les champs requis au minimum, qui sont un sous-ensemble des champs du profil du patient Argonaut :</span><span class="sxs-lookup"><span data-stu-id="3e00d-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="3e00d-129">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="3e00d-129">Name.Given</span></span>
2. <span data-ttu-id="3e00d-130">Name. Family</span><span class="sxs-lookup"><span data-stu-id="3e00d-130">Name.Family</span></span>
3. <span data-ttu-id="3e00d-131">Public</span><span class="sxs-lookup"><span data-stu-id="3e00d-131">Gender</span></span>
4. <span data-ttu-id="3e00d-132">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="3e00d-132">BirthDate</span></span>
5. <span data-ttu-id="3e00d-133">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="3e00d-133">MRN (Identifier)</span></span>

<span data-ttu-id="3e00d-134">Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="3e00d-135">Name. use</span><span class="sxs-lookup"><span data-stu-id="3e00d-135">Name.Use</span></span>
2. <span data-ttu-id="3e00d-136">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="3e00d-136">Name.Prefix</span></span>
3. <span data-ttu-id="3e00d-137">[GeneralPractitioner] : la référence GeneralPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)</span><span class="sxs-lookup"><span data-stu-id="3e00d-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="3e00d-138">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-139">ID</span><span class="sxs-lookup"><span data-stu-id="3e00d-139">id</span></span>
2. <span data-ttu-id="3e00d-140">famille = (recherche tous les patients dont le nom de famille contient la valeur)</span><span class="sxs-lookup"><span data-stu-id="3e00d-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="3e00d-141">fourni =\<sous-chaîne></span><span class="sxs-lookup"><span data-stu-id="3e00d-141">given=\<substring></span></span>
4. <span data-ttu-id="3e00d-142">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="3e00d-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="3e00d-143">sexe = (valeurs faisant partie d’un compte d’administrateur-sexe)</span><span class="sxs-lookup"><span data-stu-id="3e00d-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="3e00d-144">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="3e00d-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="3e00d-145">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche et \_du comptage qui seront utilisés par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="3e00d-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="3e00d-146">identifiant =\<NRM></span><span class="sxs-lookup"><span data-stu-id="3e00d-146">identifier=\<mrn></span></span>

<span data-ttu-id="3e00d-147">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e00d-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="3e00d-148">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="3e00d-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="3e00d-149">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="3e00d-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="3e00d-150">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="3e00d-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="3e00d-151">Nom</span><span class="sxs-lookup"><span data-stu-id="3e00d-151">Name</span></span>
- <span data-ttu-id="3e00d-152">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="3e00d-152">Birthdate</span></span>

<span data-ttu-id="3e00d-153">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3e00d-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="3e00d-154">Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="3e00d-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="3e00d-155">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "meta" : {"lastUpdated" : "2019-01-14T23:44:45.052 + 00:00"}, "tapez" : "searchset", "total" : 1, "Self", "URL" : « auto », « URL » : <fhir-Server>/patient/_search "}]," entrée " : [{" fullUrl " : <fhir-Server>/patient/<patient-ID>", "ressource" : {"resourceType" : "patient", "ID" : "<patient-ID>", "meta" : {"versionId" : "1", "lastUpdated" : "2017-10-18T18:32:37.000 + 00:00"}, "texte" : {"Status" : "generated", "div" : "</span><span class="sxs-lookup"><span data-stu-id="3e00d-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="3e00d-156">\n</span><span class="sxs-lookup"><span data-stu-id="3e00d-156">\n</span></span>        <p><span data-ttu-id="3e00d-157">Noir Ruth</span><span class="sxs-lookup"><span data-stu-id="3e00d-157">Ruth Black</span></span></p><span data-ttu-id="3e00d-158">\n</span><span class="sxs-lookup"><span data-stu-id="3e00d-158">\n</span></span>      </div><span data-ttu-id="3e00d-159">"}," identificateur " : [{" use " :" usuelle "," type " : {" codification " : [{" System " :"https://hl7.org/fhir/v2/0203"," code " :" Mr "," Display "," "userSelected" : false}], "texte" : "http://hospital.smarthealthit.org", "", "", "", "", "valeur" : "1234567"}], "actif" : vrai, "nom" : "" ";" ""; ""; ""; "" ";"</span><span class="sxs-lookup"><span data-stu-id="3e00d-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="3e00d-160">]}], "Telecom" : [{"système" : "téléphone", "valeur" : "800-599-2739", "utiliser" : "maison"}, {"système" : "téléphone", "valeur" : "800-808-7785", "utiliser" : "mobile"}, {"système" : "ruth.black@example.com" = "" valeur "femelle", "DateNaissance" : "1951-08-23", "adresse" : [{"utiliser" : "maison", "ligne" : ["26 South RdApt 22"], "ville" : "sapâtea", "État" : "OK", "CodePostal" : "74066", "Country" : "USA"}]), "Search" : {"mode" : "match"}})}</span><span class="sxs-lookup"><span data-stu-id="3e00d-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="3e00d-161">Demande : obtenez <fhir-Server>/patient/<patient-ID></span><span class="sxs-lookup"><span data-stu-id="3e00d-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="3e00d-162">Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>", "identificateur" : [{"use" : "usuelle", "type" : {"codage" : [{"système" : "https://hl7.org/fhir/v2/0203", "code" : "Mr",}], "texte" : "le numéro de l’enregistrement médical"}, "valeur" : "1234567"}], "nom" : [{"utiliser" : "officiel", "famille" : "Adams", ""» : "Michel", "X."</span><span class="sxs-lookup"><span data-stu-id="3e00d-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="3e00d-163">]}], "sexe" : "mâle", "DateNaissance" : "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="3e00d-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="3e00d-164">Pour [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-164">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="3e00d-165">Déterminée</span><span class="sxs-lookup"><span data-stu-id="3e00d-165">Observation</span></span>

<span data-ttu-id="3e00d-166">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de signes vitaux de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="3e00d-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="3e00d-167">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="3e00d-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="3e00d-168">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="3e00d-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="3e00d-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="3e00d-169">ValueQuantity.Value</span></span>

<span data-ttu-id="3e00d-170">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="3e00d-171">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="3e00d-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="3e00d-172">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="3e00d-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="3e00d-173">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-174">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-174">patient=\<patient id></span></span>
2. <span data-ttu-id="3e00d-175">_sort = date</span><span class="sxs-lookup"><span data-stu-id="3e00d-175">_sort=-date</span></span>
3. <span data-ttu-id="3e00d-176">Category (nous interrogerons « Category = vitaux-Sign-signes ») pour récupérer la liste des signes vitaux.</span><span class="sxs-lookup"><span data-stu-id="3e00d-176">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="3e00d-177">Reportez-vous à cet exemple de l’appel :</span><span class="sxs-lookup"><span data-stu-id="3e00d-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="3e00d-178">Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&catégorie = vitaux-signes</span><span class="sxs-lookup"><span data-stu-id="3e00d-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="3e00d-179">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-ID>", "category" : [{"code" : [{"System", "https://hl7.org/fhir/observation-category", "code" : "" code " : {" Coding " : [{" System " :"http://loinc.org"," code " :" 8867-4 "," display " :" heart_rate "}]}," effectiveDateTime " :" 2009-04-08T00:00:00-06:00 "," valueQuantity " : {" value " : 72,0," Unit " :" {temps} minute "," système " :"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="3e00d-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="3e00d-180">.</span><span class="sxs-lookup"><span data-stu-id="3e00d-180">.</span></span>
        <span data-ttu-id="3e00d-181">.</span><span class="sxs-lookup"><span data-stu-id="3e00d-181">.</span></span>
      <span data-ttu-id="3e00d-182">] }</span><span class="sxs-lookup"><span data-stu-id="3e00d-182">] }</span></span>

* * *

<span data-ttu-id="3e00d-183">Pour [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="3e00d-184">Condition</span><span class="sxs-lookup"><span data-stu-id="3e00d-184">Condition</span></span>

<span data-ttu-id="3e00d-185">Voici les champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="3e00d-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="3e00d-186">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="3e00d-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="3e00d-187">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="3e00d-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="3e00d-188">AssertedDate</span></span>
2. <span data-ttu-id="3e00d-189">Minimal</span><span class="sxs-lookup"><span data-stu-id="3e00d-189">Severity</span></span>

<span data-ttu-id="3e00d-190">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-191">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-191">patient=\<patient id></span></span>
2. <span data-ttu-id="3e00d-192">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="3e00d-192">_count=\<max results></span></span>

<span data-ttu-id="3e00d-193">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3e00d-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="3e00d-194">Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="3e00d-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="3e00d-195">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 2, "entry" : [{"Resource" : {"resourceType" = "condition", "ID" : "<-ID>", "code" : {"code"http://snomed.info/sct"," code " :" 185903001 "," Display " :" nécessite une immunisation de la grippe ",}]}," gravité " : {" codage " : [{" System " :"http://snomed.info/sct"," code " :" 24484000 "," Display " :" assertedDate "}}," " :" 2018-04-04 "}};</span><span class="sxs-lookup"><span data-stu-id="3e00d-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="3e00d-196">.</span><span class="sxs-lookup"><span data-stu-id="3e00d-196">.</span></span>
        <span data-ttu-id="3e00d-197">.</span><span class="sxs-lookup"><span data-stu-id="3e00d-197">.</span></span>
      <span data-ttu-id="3e00d-198">] }</span><span class="sxs-lookup"><span data-stu-id="3e00d-198">] }</span></span>

* * *
<span data-ttu-id="3e00d-199">Pour [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-199">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="3e00d-200">Connaître</span><span class="sxs-lookup"><span data-stu-id="3e00d-200">Encounter</span></span>

<span data-ttu-id="3e00d-201">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du profil de type [rencontrent des États-Unis](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="3e00d-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="3e00d-202">État</span><span class="sxs-lookup"><span data-stu-id="3e00d-202">Status</span></span>
2. <span data-ttu-id="3e00d-203">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="3e00d-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="3e00d-204">De plus, les champs suivants provenant du cœur Microsoft pour les États-Unis du profil « doivent prendre en charge » :</span><span class="sxs-lookup"><span data-stu-id="3e00d-204">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="3e00d-205">Période. début</span><span class="sxs-lookup"><span data-stu-id="3e00d-205">Period.Start</span></span>
2. <span data-ttu-id="3e00d-206">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="3e00d-206">Location[0].Location.Display</span></span>

<span data-ttu-id="3e00d-207">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-208">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-208">patient=\<patient id></span></span>
2. <span data-ttu-id="3e00d-209">_sort : DESC =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="3e00d-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="3e00d-210">Date></span><span class="sxs-lookup"><span data-stu-id="3e00d-210">date></span></span>
3. <span data-ttu-id="3e00d-211">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="3e00d-211">_count=\<max results></span></span>

<span data-ttu-id="3e00d-212">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="3e00d-212">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="3e00d-213">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e00d-213">Each encounter references a location resource.</span></span> <span data-ttu-id="3e00d-214">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e00d-214">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="3e00d-215">Pour [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-215">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="3e00d-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="3e00d-216">AllergyIntolerance</span></span>

<span data-ttu-id="3e00d-217">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="3e00d-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="3e00d-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="3e00d-218">Code.Text</span></span>
2. <span data-ttu-id="3e00d-219">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="3e00d-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="3e00d-220">ClinicalStatus/VerificationStatus (nous avons lu les deux)</span><span class="sxs-lookup"><span data-stu-id="3e00d-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="3e00d-221">Outre les champs Argonaut, pour optimiser l’utilisation de l’application patients, l’application patients peut également lire le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="3e00d-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="3e00d-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="3e00d-222">AssertedDate</span></span>
2. <span data-ttu-id="3e00d-223">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="3e00d-223">Note.Text</span></span>
3. <span data-ttu-id="3e00d-224">Réaction</span><span class="sxs-lookup"><span data-stu-id="3e00d-224">Reaction</span></span>
    1. <span data-ttu-id="3e00d-225">Substance (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="3e00d-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="3e00d-226">Manifeste (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="3e00d-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="3e00d-227">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-228">Patient = \<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-228">Patient =  \<patient id></span></span>

<span data-ttu-id="3e00d-229">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3e00d-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="3e00d-230">Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="3e00d-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="3e00d-231">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType", "AllergyIntolerance", "ID" : "<-ID>", "clinicalStatus" : "actif", "verificationStatus" : "confirmé", "code" : {"http://rxnav.nlm.nih.gov/REST/Ndfrtcode" : "", "code" : "N0000175503", "Display" : "sulfonamide antibactérienne",}], "texte" : "sulfonamide antibactérienne"}, "assertedDate" : "2018-01-01T00:00:00-07:00", "réaction" : [{"se manifester" : [{"codage" : [{"système" : "http://snomed.info/sct", "code" : "271807003", "Display" : "Skin rash",}), "Text" : "Skin rash"}]</span><span class="sxs-lookup"><span data-stu-id="3e00d-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="3e00d-232">Pour [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-232">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="3e00d-233">Demande de médication</span><span class="sxs-lookup"><span data-stu-id="3e00d-233">Medication Request</span></span>

<span data-ttu-id="3e00d-234">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de demande de médicament principal pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="3e00d-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="3e00d-235">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="3e00d-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="3e00d-236">Médication. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="3e00d-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="3e00d-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="3e00d-237">AuthoredOn</span></span>
4. <span data-ttu-id="3e00d-238">Demandeur. agent. Display</span><span class="sxs-lookup"><span data-stu-id="3e00d-238">Requester.Agent.Display</span></span>

<span data-ttu-id="3e00d-239">Outre les champs de base américaine, l’application patients peut également lire les champs suivants pour une utilisation optimale :</span><span class="sxs-lookup"><span data-stu-id="3e00d-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="3e00d-240">DosageInstruction[..]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="3e00d-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="3e00d-241">Synthèse</span><span class="sxs-lookup"><span data-stu-id="3e00d-241">Text</span></span>

<span data-ttu-id="3e00d-242">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-243">patient =\<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-243">patient=\<patient id></span></span>
2. <span data-ttu-id="3e00d-244">_count =\<résultats maximum></span><span class="sxs-lookup"><span data-stu-id="3e00d-244">_count=\<max results></span></span>

<span data-ttu-id="3e00d-245">Pour [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="3e00d-246">Articles</span><span class="sxs-lookup"><span data-stu-id="3e00d-246">Coverage</span></span>

<span data-ttu-id="3e00d-247">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="3e00d-248">Regroupement d’au moins un élément avec</span><span class="sxs-lookup"><span data-stu-id="3e00d-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="3e00d-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="3e00d-249">GroupDisplay</span></span>
    2. <span data-ttu-id="3e00d-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="3e00d-250">PlanDisplay</span></span>
2. <span data-ttu-id="3e00d-251">Donnée</span><span class="sxs-lookup"><span data-stu-id="3e00d-251">Period</span></span>
3. <span data-ttu-id="3e00d-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="3e00d-252">SubscriberId</span></span>

<span data-ttu-id="3e00d-253">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3e00d-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="3e00d-254">Patient = \<ID du patient></span><span class="sxs-lookup"><span data-stu-id="3e00d-254">Patient = \<patient id></span></span>

<span data-ttu-id="3e00d-255">Pour [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="3e00d-255">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
