---
title: Application des patients et DMP interface d’intégration STU3
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Intégration de Patients d’équipes Microsoft app DMI
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643095"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="f790c-103">Spécification d’interface STU3</span><span class="sxs-lookup"><span data-stu-id="f790c-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="f790c-104">Configuration ou la reconfiguration d’un serveur FHIR pour fonctionner avec l’application Microsoft équipes Patients, vous devez comprendre les données de l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="f790c-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="f790c-105">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de groupes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="f790c-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="f790c-106">Patient</span><span class="sxs-lookup"><span data-stu-id="f790c-106">Patient</span></span>](#patient)
- [<span data-ttu-id="f790c-107">Observation</span><span class="sxs-lookup"><span data-stu-id="f790c-107">Observation</span></span>](#observation)
- [<span data-ttu-id="f790c-108">Condition</span><span class="sxs-lookup"><span data-stu-id="f790c-108">Condition</span></span>](#condition)
- [<span data-ttu-id="f790c-109">Rencontrez</span><span class="sxs-lookup"><span data-stu-id="f790c-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="f790c-110">INTOLÉRANCE allergies</span><span class="sxs-lookup"><span data-stu-id="f790c-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="f790c-111">Couverture</span><span class="sxs-lookup"><span data-stu-id="f790c-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="f790c-112">[Instruction MEDICATION](#medication-request) (remplace la MedicationOrder dans la version DSTU2 de le PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="f790c-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="f790c-113">Emplacement (les informations nécessaires à partir de cette ressource peut être incluses dans rencontre)</span><span class="sxs-lookup"><span data-stu-id="f790c-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="f790c-114">La ressource Patient est la ressource obligatoire uniquement (sans laquelle l’application chargera pas du tout) ; Toutefois, il est recommandé que le partenaire de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus par les spécifications indiquées ci-dessous pour la meilleure expérience utilisateur final avec l’application de Patients équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f790c-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="f790c-115">Requêtes à partir de l’application Microsoft équipes Patients pour plusieurs ressources doivent publier un lot (BATCH) des demandes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="f790c-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="f790c-116">Le serveur doit traiter chaque demande et renvoyer un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="f790c-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="f790c-117">Pour plus d’informations et des exemples, voir [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="f790c-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="f790c-118">Instruction de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="f790c-118">Capability Statement</span></span>

<span data-ttu-id="f790c-119">Voici les champs obligatoires minimales :</span><span class="sxs-lookup"><span data-stu-id="f790c-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="f790c-120">REST</span><span class="sxs-lookup"><span data-stu-id="f790c-120">REST</span></span>
   1. <span data-ttu-id="f790c-121">Mode</span><span class="sxs-lookup"><span data-stu-id="f790c-121">Mode</span></span>
   2. <span data-ttu-id="f790c-122">Interaction</span><span class="sxs-lookup"><span data-stu-id="f790c-122">Interaction</span></span>
   3. <span data-ttu-id="f790c-123">Ressource : Type</span><span class="sxs-lookup"><span data-stu-id="f790c-123">Resource: Type</span></span>
   4. <span data-ttu-id="f790c-124">Sécurité : [Extension pour les URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="f790c-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="f790c-125">FhirVersion (notre code requiert cette option pour comprendre de quelle version nous devons de tableau croisé dynamique à).</span><span class="sxs-lookup"><span data-stu-id="f790c-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="f790c-126">Voir [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="f790c-127">Patient</span><span class="sxs-lookup"><span data-stu-id="f790c-127">Patient</span></span>

<span data-ttu-id="f790c-128">Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs profil patients Argonaut :</span><span class="sxs-lookup"><span data-stu-id="f790c-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="f790c-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="f790c-129">Name.Given</span></span>
2. <span data-ttu-id="f790c-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="f790c-130">Name.Family</span></span>
3. <span data-ttu-id="f790c-131">Sexe</span><span class="sxs-lookup"><span data-stu-id="f790c-131">Gender</span></span>
4. <span data-ttu-id="f790c-132">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="f790c-132">BirthDate</span></span>
5. <span data-ttu-id="f790c-133">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="f790c-133">MRN (Identifier)</span></span>

<span data-ttu-id="f790c-134">Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f790c-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="f790c-135">Name.Use</span></span>
2. <span data-ttu-id="f790c-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="f790c-136">Name.Prefix</span></span>
3. <span data-ttu-id="f790c-137">[GeneralPractitioner] - GeneralPractitioner la référence doit être inclus dans la ressource Patient (champ Affichage uniquement)</span><span class="sxs-lookup"><span data-stu-id="f790c-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="f790c-138">Une recherche de ressource utilise la méthode POST /Patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="f790c-139">ID</span><span class="sxs-lookup"><span data-stu-id="f790c-139">id</span></span>
2. <span data-ttu-id="f790c-140">famille = (tous les patients dont le nom de famille contient la valeur de la recherche)</span><span class="sxs-lookup"><span data-stu-id="f790c-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="f790c-141">donnée =\<substring></span><span class="sxs-lookup"><span data-stu-id="f790c-141">given=\<substring></span></span>
4. <span data-ttu-id="f790c-142">date de naissance =(exact match)</span><span class="sxs-lookup"><span data-stu-id="f790c-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="f790c-143">sexe = (valeurs dont le sexe-administration)</span><span class="sxs-lookup"><span data-stu-id="f790c-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="f790c-144">\_Count (nombre maximal de résultats qui doit être retourné)</span><span class="sxs-lookup"><span data-stu-id="f790c-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="f790c-145">La réponse doit contenir le nombre total d’enregistrements renvoyés à la suite de la recherche et \_count utilisera le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="f790c-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="f790c-146">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="f790c-146">identifier=\<mrn></span></span>

<span data-ttu-id="f790c-147">L’objectif doit être en mesure de recherche et filtrage d’un patient par les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="f790c-148">ID : Il s’agit de l’ID de ressource a toutes les ressources de FHIR.</span><span class="sxs-lookup"><span data-stu-id="f790c-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="f790c-149">NRM : Il s’agit de l’identificateur pour le patient personnel savez réel.</span><span class="sxs-lookup"><span data-stu-id="f790c-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="f790c-150">Nous savons que ce NRM est basé sur le type d’identificateur à l’intérieur de la ressource de l’identificateur dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="f790c-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="f790c-151">Nom</span><span class="sxs-lookup"><span data-stu-id="f790c-151">Name</span></span>
- <span data-ttu-id="f790c-152">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="f790c-152">Birthdate</span></span>

<span data-ttu-id="f790c-153">Consultez l’exemple de l’appel suivant :</span><span class="sxs-lookup"><span data-stu-id="f790c-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="f790c-154">Requête : Corps de la demande POST <fhir-server>/Patient/_search : donnée = ruth&family = noir</span><span class="sxs-lookup"><span data-stu-id="f790c-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="f790c-155">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « meta » : {« lastUpdated » : « 2019-01-14T23:44:45.052 + 00:00 »}, « type » : « searchset », « total » : 1, « lien » : [{« relation » : « self », « url » : <fhir-server>/Patient/_search »}], « entry » : [{ « fullUrl » : <fhir-server>/Patient/<patient-id> », « ressource » : {« resourceType » : « Patient », « id » : « <patient-id> », « meta » : {« versionId » : « 1 », « lastUpdated » : « 2017-10-18T18:32:37.000 + 00:00 »}, « texte » : {« status » : « généré », « div ": "</span><span class="sxs-lookup"><span data-stu-id="f790c-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="f790c-156">\n</span><span class="sxs-lookup"><span data-stu-id="f790c-156">\n</span></span>        <p><span data-ttu-id="f790c-157">Roland noir</span><span class="sxs-lookup"><span data-stu-id="f790c-157">Ruth Black</span></span></p><span data-ttu-id="f790c-158">\n</span><span class="sxs-lookup"><span data-stu-id="f790c-158">\n</span></span>      </div><span data-ttu-id="f790c-159">«}, « identificateur » : [{« utiliser » : « normal », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR », « afficher » : « numéro de dossier médical », « userSelected » : false}], « texte » : « numéro de dossier médical »}, « système » : «http://hospital.smarthealthit.org», « valeur » : « 1234567 »}], « actif » : true, » « nom : [{« utiliser » : « officielle », « famille » : « Noir », « attribué » : [« Michael Jordan » « c ».</span><span class="sxs-lookup"><span data-stu-id="f790c-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="f790c-160">]}], « télécommunications » : [{« système » : « téléphoniques », « valeur » : utilisation » « 800-599-2739 », » : « d’accueil »}, {« système » : « téléphoniques », « valeur » : utilisation » « 800-808-7785 », » : « mobile »}, {« système » : « email », « valeur » : « ruth.black@example.com »}], « sexe » : « féminin », « date de naissance » : « 1951-08-23 », » adresse » : [{« utiliser » : « maison », « ligne » : [« 26 Sud RdApt 22 »], « city » : « Sapulpa », « état » : « OK », « code postal » : « 74066 », « pays » : « USA »}]}, « search » : {« en mode » : « correspond à »}}]}</span><span class="sxs-lookup"><span data-stu-id="f790c-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="f790c-161">Demande : GET <fhir-server>/Patient/<patient-id></span><span class="sxs-lookup"><span data-stu-id="f790c-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="f790c-162">Réponse : {« resourceType » : « Patient », « id » : « <patient-id> », « identificateur » : [{« utiliser » : « normal », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR »,}], « texte » : « numéro de dossier médical »}, « valeur » : « 1234567 »}], « nom » : [{« utiliser » : « officiel », » famille » : « Adams », « attribué » : [« Michel », « X ».</span><span class="sxs-lookup"><span data-stu-id="f790c-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="f790c-163">{]}], « sexe » : « masculin », « date de naissance » : « 1925-12-23"}</span><span class="sxs-lookup"><span data-stu-id="f790c-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="f790c-164">Voir [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="f790c-165">Observation</span><span class="sxs-lookup"><span data-stu-id="f790c-165">Observation</span></span>

<span data-ttu-id="f790c-166">Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil Argonaut Vital-signes](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="f790c-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="f790c-167">Effet (date heure ou période)</span><span class="sxs-lookup"><span data-stu-id="f790c-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="f790c-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="f790c-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="f790c-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="f790c-169">ValueQuantity.Value</span></span>

<span data-ttu-id="f790c-170">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f790c-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="f790c-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="f790c-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="f790c-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="f790c-173">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-174">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-174">patient=\<patient id></span></span>
2. <span data-ttu-id="f790c-175">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="f790c-175">_sort=-date</span></span>
3. <span data-ttu-id="f790c-176">catégorie (nous demande « catégorie = vitale signes ») pour récupérer la liste des signes vital.</span><span class="sxs-lookup"><span data-stu-id="f790c-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="f790c-177">Reportez-vous à cet exemple de l’appel :</span><span class="sxs-lookup"><span data-stu-id="f790c-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="f790c-178">Demande : Obtenir <fhir-server>/Observation ? patient = <patient-id>&category = vitale signes</span><span class="sxs-lookup"><span data-stu-id="f790c-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="f790c-179">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 20, « entry » : [{« ressource » : {« resourceType » : « Observation », « id » : « <resource-id> », « catégorie » : [{« codage » : [{« système » : «http://hl7.org/fhir/observation-category», « code » : » vital-signes «}]}], « code » : {« codage » : [{« système » : «http://loinc.org», « code » : « 4 8867 », « affichage » : « heart_rate »}]}, « effectiveDateTime » : » 2009-04-08T00:00:00-06:00 », « valueQuantity » : {« valeur » : 72,0, « unité » : » {temps} / min », « système » : «http://unitsofmeasure.org»,}}},.</span><span class="sxs-lookup"><span data-stu-id="f790c-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="f790c-180">.</span><span class="sxs-lookup"><span data-stu-id="f790c-180"></span></span>
        <span data-ttu-id="f790c-181">.</span><span class="sxs-lookup"><span data-stu-id="f790c-181"></span></span>
      <span data-ttu-id="f790c-182">] }</span><span class="sxs-lookup"><span data-stu-id="f790c-182"></span></span>

* * *

<span data-ttu-id="f790c-183">Voir [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="f790c-184">Condition</span><span class="sxs-lookup"><span data-stu-id="f790c-184">Condition</span></span>

<span data-ttu-id="f790c-185">Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="f790c-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="f790c-186">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="f790c-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="f790c-187">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f790c-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="f790c-188">AssertedDate</span></span>
2. <span data-ttu-id="f790c-189">Niveau de gravité</span><span class="sxs-lookup"><span data-stu-id="f790c-189">Severity</span></span>

<span data-ttu-id="f790c-190">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-191">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-191">patient=\<patient id></span></span>
2. <span data-ttu-id="f790c-192">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="f790c-192">_count=\<max results></span></span>

<span data-ttu-id="f790c-193">Consultez l’exemple de cet appel suivant :</span><span class="sxs-lookup"><span data-stu-id="f790c-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="f790c-194">Demande : Obtenir <fhir-server>/Condition ? patient = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="f790c-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="f790c-195">Response Group : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 2, « entry » : [{« ressource » : {« resourceType » : « Condition », « id » : « <resource-id> », « code » : {« codage » : [{« système » : «http://snomed.info/sct», « code » : « 185903001 », » afficher » : « Immunisation contre de besoins »,}]}, « severity » : {« codage » : [{« système » : «http://snomed.info/sct», « code » : « 24484000 », « afficher » : « Grave »}]}, « assertedDate » : « 2018-04-04 »}},.</span><span class="sxs-lookup"><span data-stu-id="f790c-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="f790c-196">.</span><span class="sxs-lookup"><span data-stu-id="f790c-196"></span></span>
        <span data-ttu-id="f790c-197">.</span><span class="sxs-lookup"><span data-stu-id="f790c-197"></span></span>
      <span data-ttu-id="f790c-198">] }</span><span class="sxs-lookup"><span data-stu-id="f790c-198"></span></span>

* * *
<span data-ttu-id="f790c-199">Voir [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="f790c-200">Rencontrez</span><span class="sxs-lookup"><span data-stu-id="f790c-200">Encounter</span></span>

<span data-ttu-id="f790c-201">Les champs suivants sont minimales requises, qui sont un sous-ensemble des champs [profil US principaux rencontrer](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) « doit avoir »).</span><span class="sxs-lookup"><span data-stu-id="f790c-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="f790c-202">État</span><span class="sxs-lookup"><span data-stu-id="f790c-202">Status</span></span>
2. <span data-ttu-id="f790c-203">Type [0]. Codage [0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="f790c-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="f790c-204">En outre, les champs suivants à partir du profil de nous rencontrer principaux » doivent prendre en charge » champs :</span><span class="sxs-lookup"><span data-stu-id="f790c-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="f790c-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="f790c-205">Period.Start</span></span>
2. <span data-ttu-id="f790c-206">Emplacement [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="f790c-206">Location[0].Location.Display</span></span>

<span data-ttu-id="f790c-207">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-208">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-208">patient=\<patient id></span></span>
2. <span data-ttu-id="f790c-209">_sort:DESC =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="f790c-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="f790c-210">date></span><span class="sxs-lookup"><span data-stu-id="f790c-210">date></span></span>
3. <span data-ttu-id="f790c-211">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="f790c-211">_count=\<max results></span></span>

<span data-ttu-id="f790c-212">L’objectif est de pouvoir récupérer l’emplacement connu dernier du patient.</span><span class="sxs-lookup"><span data-stu-id="f790c-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="f790c-213">Chaque fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="f790c-213">Each encounter references a location resource.</span></span> <span data-ttu-id="f790c-214">La référence comprennent également champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="f790c-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="f790c-215">Voir [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="f790c-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="f790c-216">AllergyIntolerance</span></span>

<span data-ttu-id="f790c-217">Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="f790c-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="f790c-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="f790c-218">Code.Text</span></span>
2. <span data-ttu-id="f790c-219">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="f790c-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="f790c-220">ClinicalStatus/VerificationStatus (lu les deux)</span><span class="sxs-lookup"><span data-stu-id="f790c-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="f790c-221">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="f790c-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="f790c-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="f790c-222">AssertedDate</span></span>
2. <span data-ttu-id="f790c-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="f790c-223">Note.Text</span></span>
3. <span data-ttu-id="f790c-224">Réaction</span><span class="sxs-lookup"><span data-stu-id="f790c-224">Reaction</span></span>
    1. <span data-ttu-id="f790c-225">Substance (un seul élément de codage)</span><span class="sxs-lookup"><span data-stu-id="f790c-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="f790c-226">Manifestation (un seul élément de codage)</span><span class="sxs-lookup"><span data-stu-id="f790c-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="f790c-227">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-228">Patient = \<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-228">Patient =  \<patient id></span></span>

<span data-ttu-id="f790c-229">Consultez l’exemple de l’appel suivant :</span><span class="sxs-lookup"><span data-stu-id="f790c-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="f790c-230">Demande : Obtenir <fhir-server>/AllergyIntolerance ? patient = <patient-id></span><span class="sxs-lookup"><span data-stu-id="f790c-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="f790c-231">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « AllergyIntolerance », « id » : « <resource-id> », « clinicalStatus » : « actif », « ve rificationStatus » : « confirmée », « code » : {« codage » : [{« système » : «http://rxnav.nlm.nih.gov/REST/Ndfrt», « code » : « N0000175503 », « afficher » : « sulfonamide ANTIBACTÉRIEN »,}], « texte » : ant sulfonamide » ibacterial »}, « assertedDate » : « 2018-01-01T00:00:00-07:00 », « réaction » : [{« manifestation » : [{« codage » : [{« système » : «http://snomed.info/sct», « code » :  « 271807003 », « afficher » : « éruption apparence »,}], « texte » : « éruption apparence »}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="f790c-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="f790c-232">Voir [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="f790c-233">Demande de médication</span><span class="sxs-lookup"><span data-stu-id="f790c-233">Medication Request</span></span>

<span data-ttu-id="f790c-234">Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil US principaux médication demande](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="f790c-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="f790c-235">Medication.Display (si référence)</span><span class="sxs-lookup"><span data-stu-id="f790c-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="f790c-236">Medication.Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="f790c-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="f790c-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="f790c-237">AuthoredOn</span></span>
4. <span data-ttu-id="f790c-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="f790c-238">Requester.Agent.Display</span></span>

<span data-ttu-id="f790c-239">Outre les champs Core américain, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f790c-240">DosageInstruction [.]. Texte</span><span class="sxs-lookup"><span data-stu-id="f790c-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="f790c-241">Texte</span><span class="sxs-lookup"><span data-stu-id="f790c-241">Text</span></span>

<span data-ttu-id="f790c-242">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-243">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-243">patient=\<patient id></span></span>
2. <span data-ttu-id="f790c-244">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="f790c-244">_count=\<max results></span></span>

<span data-ttu-id="f790c-245">Voir [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="f790c-246">Couverture</span><span class="sxs-lookup"><span data-stu-id="f790c-246">Coverage</span></span>

<span data-ttu-id="f790c-247">Voici les champs obligatoires minimales, non couverts par les profils Argonaut soit nous principaux :</span><span class="sxs-lookup"><span data-stu-id="f790c-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="f790c-248">Regroupement, au moins un élément avec</span><span class="sxs-lookup"><span data-stu-id="f790c-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="f790c-249">Groupe IPMPAffichage</span><span class="sxs-lookup"><span data-stu-id="f790c-249">GroupDisplay</span></span>
    2. <span data-ttu-id="f790c-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="f790c-250">PlanDisplay</span></span>
2. <span data-ttu-id="f790c-251">Période</span><span class="sxs-lookup"><span data-stu-id="f790c-251">Period</span></span>
3. <span data-ttu-id="f790c-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="f790c-252">SubscriberId</span></span>

<span data-ttu-id="f790c-253">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f790c-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f790c-254">Patient = \<id> patient</span><span class="sxs-lookup"><span data-stu-id="f790c-254">Patient = \<patient id></span></span>

<span data-ttu-id="f790c-255">Voir [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="f790c-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
