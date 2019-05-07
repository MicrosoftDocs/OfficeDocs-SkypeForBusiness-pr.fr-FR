---
title: " Application des patients et DMP interface d’intégration DSTU2"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643093"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="68337-103">Spécification d’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="68337-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="68337-104">Configuration ou la reconfiguration d’un serveur FHIR pour fonctionner avec l’application Microsoft équipes Patients, vous devez comprendre les données de l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="68337-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="68337-105">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de groupes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="68337-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="68337-106">Patient</span><span class="sxs-lookup"><span data-stu-id="68337-106">Patient</span></span>](#patient)
- [<span data-ttu-id="68337-107">Observation</span><span class="sxs-lookup"><span data-stu-id="68337-107">Observation</span></span>](#observation)
- [<span data-ttu-id="68337-108">Condition</span><span class="sxs-lookup"><span data-stu-id="68337-108">Condition</span></span>](#condition)
- [<span data-ttu-id="68337-109">Rencontrez</span><span class="sxs-lookup"><span data-stu-id="68337-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="68337-110">INTOLÉRANCE allergies</span><span class="sxs-lookup"><span data-stu-id="68337-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="68337-111">Couverture</span><span class="sxs-lookup"><span data-stu-id="68337-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="68337-112">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="68337-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="68337-113">Emplacement</span><span class="sxs-lookup"><span data-stu-id="68337-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="68337-114">La ressource Patient est la ressource obligatoire uniquement (sans laquelle l’application chargera pas du tout.</span><span class="sxs-lookup"><span data-stu-id="68337-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="68337-115">Toutefois, il est recommandé que le partenaire de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus par les spécifications indiquées ci-dessous pour la meilleure expérience utilisateur final avec l’application de Patients équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68337-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="68337-116">Requêtes à partir de l’application Microsoft équipes Patients pour plusieurs ressources publier un lot (BATCH) des demandes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="68337-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="68337-117">Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="68337-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="68337-118">Pour plus d’informations et des exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="68337-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="68337-119">Toutes les ressources FHIR suivantes doivent être accessibles par référence de ressource direct.</span><span class="sxs-lookup"><span data-stu-id="68337-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="68337-120">La valeur de champ obligatoire minimale de mise en conformité</span><span class="sxs-lookup"><span data-stu-id="68337-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="68337-121">Le serveur FHIR doit implémenter la déclaration de conformité pour avoir un résumé concrètes de ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="68337-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="68337-122">Nous pensons que les paramètres d’un serveur de FHIR DSTU2 ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="68337-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="68337-123">REST</span><span class="sxs-lookup"><span data-stu-id="68337-123">REST</span></span>
   1. <span data-ttu-id="68337-124">Mode</span><span class="sxs-lookup"><span data-stu-id="68337-124">Mode</span></span>
   2. <span data-ttu-id="68337-125">Interaction</span><span class="sxs-lookup"><span data-stu-id="68337-125">Interaction</span></span>
   3. <span data-ttu-id="68337-126">Ressource : Type</span><span class="sxs-lookup"><span data-stu-id="68337-126">Resource: Type</span></span>
   4. <span data-ttu-id="68337-127">Sécurité : [Extension pour les URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="68337-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="68337-128">FhirVersion (notre code requiert cette option pour comprendre de quelle version nous devons de tableau croisé dynamique pour qu’il prend en charge plusieurs versions).</span><span class="sxs-lookup"><span data-stu-id="68337-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="68337-129">Voir [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="68337-130">Patient</span><span class="sxs-lookup"><span data-stu-id="68337-130">Patient</span></span>

<span data-ttu-id="68337-131">Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs [profil patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="68337-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="68337-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="68337-132">Name.Family</span></span>
2. <span data-ttu-id="68337-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="68337-133">Name.Given</span></span>
3. <span data-ttu-id="68337-134">Sexe</span><span class="sxs-lookup"><span data-stu-id="68337-134">Gender</span></span>
4. <span data-ttu-id="68337-135">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="68337-135">BirthDate</span></span>
5. <span data-ttu-id="68337-136">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="68337-136">MRN (Identifier)</span></span>

<span data-ttu-id="68337-137">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="68337-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="68337-138">Name.Use</span></span>
2. <span data-ttu-id="68337-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="68337-139">Name.Prefix</span></span>
3. <span data-ttu-id="68337-140">CareProvider (ce guide de référence sur la ressource Patient doit inclure les champs d’affichage dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="68337-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="68337-141">Demande : GET <fhir-server>/Patient/<patient-id></span><span class="sxs-lookup"><span data-stu-id="68337-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="68337-142">Réponse : {« resourceType » : « Patient », « id » : « <patient-id>, ».</span><span class="sxs-lookup"><span data-stu-id="68337-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="68337-143">.</span><span class="sxs-lookup"><span data-stu-id="68337-143"></span></span>
      <span data-ttu-id="68337-144">.</span><span class="sxs-lookup"><span data-stu-id="68337-144"></span></span>
      <span data-ttu-id="68337-145">« name » : [{« utiliser » : « officiel », « préfixe » : [« Mr »], « famille » : [« Chau »], « attribué » : [« Hugh »]}], « identificateur » : [{« utiliser » : « officiel », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR »}]}, « valeur » : « 1234567 »}], « sexe » : « masculin », « date de naissance » : « 1957-06-05 «, « careProvider » : [{« affichage » : « Jane Doe »}],}</span><span class="sxs-lookup"><span data-stu-id="68337-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="68337-146">Une recherche de ressource utilise la méthode POST /Patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="68337-147">ID</span><span class="sxs-lookup"><span data-stu-id="68337-147">id</span></span>
2. <span data-ttu-id="68337-148">famille : contient = (recherche tous les patients dont le nom de famille contient la valeur).</span><span class="sxs-lookup"><span data-stu-id="68337-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="68337-149">donnée =\<substring></span><span class="sxs-lookup"><span data-stu-id="68337-149">given=\<substring></span></span>
4. <span data-ttu-id="68337-150">nom =\<substring></span><span class="sxs-lookup"><span data-stu-id="68337-150">name=\<substring></span></span>
5. <span data-ttu-id="68337-151">date de naissance =(exact match)</span><span class="sxs-lookup"><span data-stu-id="68337-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="68337-152">\_Count (nombre maximal de résultats qui doit être retourné)</span><span class="sxs-lookup"><span data-stu-id="68337-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="68337-153">La réponse doit contenir le nombre total d’enregistrements renvoyés à la suite de la recherche, et \_count utilisera le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="68337-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="68337-154">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="68337-154">identifier=\<mrn></span></span>

<span data-ttu-id="68337-155">L’objectif doit être en mesure de recherche et filtrage d’un patient par les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="68337-156">ID : Il s’agit de l’ID de ressource a toutes les ressources de FHIR.</span><span class="sxs-lookup"><span data-stu-id="68337-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="68337-157">NRM : Il s’agit de l’identificateur pour le patient personnel savez réel.</span><span class="sxs-lookup"><span data-stu-id="68337-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="68337-158">Nous savons que ce NRM est basé sur le type d’identificateur à l’intérieur de la ressource de l’identificateur dans FHIR</span><span class="sxs-lookup"><span data-stu-id="68337-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="68337-159">Nom</span><span class="sxs-lookup"><span data-stu-id="68337-159">Name</span></span>
- <span data-ttu-id="68337-160">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="68337-160">Birthdate</span></span>

<span data-ttu-id="68337-161">Voir l’exemple suivant de cet appel.</span><span class="sxs-lookup"><span data-stu-id="68337-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="68337-162">Requête : Corps de la demande POST <fhir-server>/Patient/_search : donnée = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="68337-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="68337-163">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id>, ».</span><span class="sxs-lookup"><span data-stu-id="68337-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="68337-164">.</span><span class="sxs-lookup"><span data-stu-id="68337-164"></span></span>
      <span data-ttu-id="68337-165">.</span><span class="sxs-lookup"><span data-stu-id="68337-165"></span></span>
      <span data-ttu-id="68337-166">« entry » : [{« ressource » : {« resourceType » : « Patient », « id » : « <patient-id> », « nom » : [{« texte » : « Hugh Chau », « famille » : [« Chau »], « attribué » : [« Hugh »]}], « sexe » : « masculin », « date de naissance » : « 1957-06-05 »}, « search » : {« mode » : « correspond à »}}]}</span><span class="sxs-lookup"><span data-stu-id="68337-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="68337-167">Voir [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="68337-168">Observation</span><span class="sxs-lookup"><span data-stu-id="68337-168">Observation</span></span>

<span data-ttu-id="68337-169">Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut signes essentielles :</span><span class="sxs-lookup"><span data-stu-id="68337-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="68337-170">Effet (date heure ou période)</span><span class="sxs-lookup"><span data-stu-id="68337-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="68337-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="68337-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="68337-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="68337-172">ValueQuantity.Value</span></span>

<span data-ttu-id="68337-173">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="68337-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="68337-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="68337-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="68337-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="68337-176">Si vous utilisez des observations composant, la même logique s’applique pour observation de chaque composant.</span><span class="sxs-lookup"><span data-stu-id="68337-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="68337-177">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-178">patient =\<id patient\></span><span class="sxs-lookup"><span data-stu-id="68337-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="68337-179">tri : desc =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="68337-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="68337-180">date\></span><span class="sxs-lookup"><span data-stu-id="68337-180">date\></span></span>

<span data-ttu-id="68337-181">L’objectif doit être en mesure de récupérer les signes vital le plus récent pour un patient, [VitalSigns.DSTU.saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="68337-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="68337-182">Demande : Obtenir <fhir-server>/Observation ? patient = <patient-id>&_sort:desc = date&category = vitale signes</span><span class="sxs-lookup"><span data-stu-id="68337-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="68337-183">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 20, « entry » : [{« ressource » : {« resourceType » : « Observation », « id » : « <resource-id> », « catégorie » : {« codage » : [{code » : « vitale signes »}],}, « code » : { » codage » : [{« système » : «http://loinc.org», « code » : « 39156-5 », « affichage » : « IMC »}],}, « effectiveDateTime » : « 2009-12-01 », « valueQuantity » : {« valeur » : 34.4, « unité » : « kg/m2 », « système » : «http://unitsofmeasure.org», « code » : « kg/m2 »}},},.</span><span class="sxs-lookup"><span data-stu-id="68337-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="68337-184">.</span><span class="sxs-lookup"><span data-stu-id="68337-184"></span></span>
        <span data-ttu-id="68337-185">.</span><span class="sxs-lookup"><span data-stu-id="68337-185"></span></span>
      <span data-ttu-id="68337-186">] }</span><span class="sxs-lookup"><span data-stu-id="68337-186"></span></span>

* * *

<span data-ttu-id="68337-187">Voir [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="68337-188">Condition</span><span class="sxs-lookup"><span data-stu-id="68337-188">Condition</span></span>

<span data-ttu-id="68337-189">Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="68337-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="68337-190">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="68337-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="68337-191">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="68337-192">Date d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="68337-192">Date Recorded</span></span>
2. <span data-ttu-id="68337-193">Niveau de gravité</span><span class="sxs-lookup"><span data-stu-id="68337-193">Severity</span></span>

<span data-ttu-id="68337-194">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-195">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="68337-195">patient=\<patient id></span></span>
2. <span data-ttu-id="68337-196">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="68337-196">_count=\<max results></span></span>

<span data-ttu-id="68337-197">Consultez l’exemple de cet appel suivant :</span><span class="sxs-lookup"><span data-stu-id="68337-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="68337-198">Demande : Obtenir <fhir-server>/Condition ? patient = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="68337-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="68337-199">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Condition », « id » : « <resource-id> », « code » : {« codage » : [{               « système » : «http://snomed.info/sct», « code » : « 386033004 », « afficher » : « NEUROPATHIE (nerf) »}]}, « dateRecorded » : « 2018-09-17 », « severity » : {« codage » : [{ » le système cadratin » : «http://snomed.info/sct», « code » : « 24484000 », « afficher » : « Grave »}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="68337-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="68337-200">Voir [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="68337-201">Rencontrez</span><span class="sxs-lookup"><span data-stu-id="68337-201">Encounter</span></span>

<span data-ttu-id="68337-202">Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs « doit avoir » profil nous rencontrer principaux :</span><span class="sxs-lookup"><span data-stu-id="68337-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="68337-203">État</span><span class="sxs-lookup"><span data-stu-id="68337-203">Status</span></span>
2. <span data-ttu-id="68337-204">Type [0]. Codage [0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="68337-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="68337-205">En outre, les champs suivants à partir du profil de nous rencontrer principaux » doivent prendre en charge » de champs</span><span class="sxs-lookup"><span data-stu-id="68337-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="68337-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="68337-206">Period.Start</span></span>
2. <span data-ttu-id="68337-207">Emplacement [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="68337-207">Location[0].Location.Display</span></span>

<span data-ttu-id="68337-208">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-209">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="68337-209">patient=\<patient id></span></span>
2. <span data-ttu-id="68337-210">_sort:DESC =\<champ ex.</span><span class="sxs-lookup"><span data-stu-id="68337-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="68337-211">date></span><span class="sxs-lookup"><span data-stu-id="68337-211">date></span></span>
3. <span data-ttu-id="68337-212">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="68337-212">_count=\<max results></span></span>

<span data-ttu-id="68337-213">L’objectif est de pouvoir récupérer l’emplacement connu dernier du patient.</span><span class="sxs-lookup"><span data-stu-id="68337-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="68337-214">Chaque fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="68337-214">Each encounter references a location resource.</span></span> <span data-ttu-id="68337-215">La référence comprennent également champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="68337-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="68337-216">Voir l’exemple suivant de cet appel.</span><span class="sxs-lookup"><span data-stu-id="68337-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="68337-217">Demande : Obtenir <fhir-server>/rencontre ? patient = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="68337-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="68337-218">Réponse : {« resourceType » : « Groupement », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Rencontrer », « id » : « <resource-id> », « identificateur » : [{« utiliser » : « officiel », « valeur » : «<id>»}], « status » : « a », « type » : [{« codage » : [{« affichage » : « Rendez-vous »}],}], « patients » : {« référence » : « Patient/<patient-id> »}, « période » : {« Démarrer » : « 17/09/2018 1:00:00 PM »}, « emplacement » : [{              « emplacement » : {« affichage » : « Cours pratique – ENT »},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="68337-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="68337-219">Voir [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="68337-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="68337-220">AllergyIntolerance</span></span>

<span data-ttu-id="68337-221">Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :</span><span class="sxs-lookup"><span data-stu-id="68337-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="68337-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="68337-222">Code.Text</span></span>
2. <span data-ttu-id="68337-223">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="68337-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="68337-224">État</span><span class="sxs-lookup"><span data-stu-id="68337-224">Status</span></span>

<span data-ttu-id="68337-225">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="68337-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="68337-226">RecordedDate</span></span>
2. <span data-ttu-id="68337-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="68337-227">Note.Text</span></span>
3. <span data-ttu-id="68337-228">Réaction [.]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="68337-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="68337-229">Réaction [.]. Manifestation [.]. Texte</span><span class="sxs-lookup"><span data-stu-id="68337-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="68337-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="68337-230">Text.Div</span></span>

<span data-ttu-id="68337-231">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-232">Patient = \<id> patient</span><span class="sxs-lookup"><span data-stu-id="68337-232">Patient =  \<patient id></span></span>

<span data-ttu-id="68337-233">Consultez l’exemple de cet appel suivant :</span><span class="sxs-lookup"><span data-stu-id="68337-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="68337-234">Demande : Obtenir <fhir-server>/AllergyIntolerance ? patient = <patient-id></span><span class="sxs-lookup"><span data-stu-id="68337-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="68337-235">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « AllergyIntolerance », « id » : « <resource-id> », « recordedDate » : « 2018-09-17T07:00:00.00 0Z », « substance » : {« texte » : « Cajou »}, « status » : « confirmée », « réaction » : [{« substance » : {« texte » : « écrou cajou allergisants extraire produit Injectable »}, manifestati » sur » : [{« texte » : « Réaction Anaphylactic »}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="68337-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="68337-236">Voir [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="68337-237">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="68337-237">Medication Order</span></span>

<span data-ttu-id="68337-238">Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut MedicationOrder :</span><span class="sxs-lookup"><span data-stu-id="68337-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="68337-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="68337-239">DateWritten</span></span>
2. <span data-ttu-id="68337-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="68337-240">Prescriber.Display</span></span>
3. <span data-ttu-id="68337-241">Medication.Display (si référence)</span><span class="sxs-lookup"><span data-stu-id="68337-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="68337-242">Medication.Text (si concept)</span><span class="sxs-lookup"><span data-stu-id="68337-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="68337-243">Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="68337-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="68337-244">DateEnded</span></span>
2. <span data-ttu-id="68337-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="68337-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="68337-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="68337-246">Text.Div</span></span>

<span data-ttu-id="68337-247">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-248">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="68337-248">patient=\<patient id></span></span>
2. <span data-ttu-id="68337-249">_count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="68337-249">_count=\<max results></span></span>

<span data-ttu-id="68337-250">Consultez l’exemple de cet appel suivant :</span><span class="sxs-lookup"><span data-stu-id="68337-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="68337-251">Demande : Obtenir <fhir-server>/MedicationOrder ? patient = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="68337-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="68337-252">Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « MedicationOrder », « id » : « <resource-id> », « dateWritten » : « 2018-09-17 », « medi cationCodeableConcept » : {« texte » : « Lisinopril 20 MG orale Tablet »}, « prescriber » : {« affichage » : « Jane Doe »}, « dosageInstruction » : [{« texte » : « 1 jour »}]}}]}</span><span class="sxs-lookup"><span data-stu-id="68337-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="68337-253">Voir [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="68337-254">Couverture</span><span class="sxs-lookup"><span data-stu-id="68337-254">Coverage</span></span>

<span data-ttu-id="68337-255">Voici les champs obligatoires minimales, non couverts par les profils Argonaut soit nous principaux :</span><span class="sxs-lookup"><span data-stu-id="68337-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="68337-256">Organismes payeurs</span><span class="sxs-lookup"><span data-stu-id="68337-256">Payor</span></span>

<span data-ttu-id="68337-257">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="68337-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="68337-258">patient =\<id> patient</span><span class="sxs-lookup"><span data-stu-id="68337-258">patient=\<patient id></span></span>

<span data-ttu-id="68337-259">Consultez l’exemple de cet appel suivant :</span><span class="sxs-lookup"><span data-stu-id="68337-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="68337-260">Demande : Obtenir une <fhir-server>/couverture ? patient = <patient-id></span><span class="sxs-lookup"><span data-stu-id="68337-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="68337-261">Réponse : {« resourceType » : « Groupement », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Couverture », « id » : « <resource-id> », « plan » : « No principal d’assurance », « abonné » : {« référence » : « Patient / <patient-id> »}}}]}</span><span class="sxs-lookup"><span data-stu-id="68337-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="68337-262">Voir [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="68337-263">Lieu</span><span class="sxs-lookup"><span data-stu-id="68337-263">Location</span></span>

<span data-ttu-id="68337-264">Cette ressource est uniquement utilisée comme une référence à la ressource de [rencontrer](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="68337-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="68337-265">Voir [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) pour plus de détails sur ce champ défini.</span><span class="sxs-lookup"><span data-stu-id="68337-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
