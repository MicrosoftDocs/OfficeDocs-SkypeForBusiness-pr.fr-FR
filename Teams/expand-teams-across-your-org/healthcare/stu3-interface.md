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
description: En savoir plus sur l’intégration d’enregistrements de santé électronique dans l’application Microsoft teams patients et la spécification de l’interface STU3.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c5e19ff28c67641ac5b643e1944bf2435fbf164
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361344"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="6d33b-103">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="6d33b-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d33b-104">**À compter du 15 octobre 2020, l’application patients sera déconseillée et les utilisateurs ne pourront plus l’installer à partir de l’App Store d’Teams. Nous vous encourageons à commencer à utiliser l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans teams dès aujourd’hui.**</span><span class="sxs-lookup"><span data-stu-id="6d33b-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="6d33b-105">Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe.</span><span class="sxs-lookup"><span data-stu-id="6d33b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="6d33b-106">Lorsque l’application patients est supprimée, toutes les données qui lui sont associées seront conservées dans ce groupe, mais ne seront plus accessibles par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d33b-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="6d33b-107">Les utilisateurs actuels peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="6d33b-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="6d33b-108">L' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) est préinstallée pour tous les utilisateurs d’teams et est disponible sous la forme d’une tabulation dans chaque équipe ou canal.</span><span class="sxs-lookup"><span data-stu-id="6d33b-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="6d33b-109">Les listes permettent aux équipes de soins de créer des listes de patients à l’aide du modèle de patients intégré, de zéro à partir de zéro ou d’importer des données dans Excel.</span><span class="sxs-lookup"><span data-stu-id="6d33b-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="6d33b-110">Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="6d33b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="6d33b-111">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="6d33b-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="6d33b-112">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d33b-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="6d33b-113">Patient</span><span class="sxs-lookup"><span data-stu-id="6d33b-113">Patient</span></span>](#patient)
- [<span data-ttu-id="6d33b-114">Déterminée</span><span class="sxs-lookup"><span data-stu-id="6d33b-114">Observation</span></span>](#observation)
- [<span data-ttu-id="6d33b-115">Condition</span><span class="sxs-lookup"><span data-stu-id="6d33b-115">Condition</span></span>](#condition)
- [<span data-ttu-id="6d33b-116">Connaître</span><span class="sxs-lookup"><span data-stu-id="6d33b-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="6d33b-117">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="6d33b-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="6d33b-118">Articles</span><span class="sxs-lookup"><span data-stu-id="6d33b-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="6d33b-119">[État de médication](#medication-request) (remplace le MedicationOrder dans la version DSTU2 du PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="6d33b-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="6d33b-120">Emplacement (les informations requises par cette ressource peuvent être intégrées à la rencontre)</span><span class="sxs-lookup"><span data-stu-id="6d33b-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="6d33b-121">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout); Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="6d33b-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="6d33b-122">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources publient une offre (BATCH) de requêtes dans l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="6d33b-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="6d33b-123">Le serveur traitera chaque demande et renverra une offre de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="6d33b-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="6d33b-124">Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="6d33b-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="6d33b-125">Instruction Capability</span><span class="sxs-lookup"><span data-stu-id="6d33b-125">Capability Statement</span></span>

<span data-ttu-id="6d33b-126">Voici les champs obligatoires obligatoires :</span><span class="sxs-lookup"><span data-stu-id="6d33b-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="6d33b-127">LAISSER</span><span class="sxs-lookup"><span data-stu-id="6d33b-127">REST</span></span>
   1. <span data-ttu-id="6d33b-128">Veille</span><span class="sxs-lookup"><span data-stu-id="6d33b-128">Mode</span></span>
   2. <span data-ttu-id="6d33b-129">Interaction</span><span class="sxs-lookup"><span data-stu-id="6d33b-129">Interaction</span></span>
   3. <span data-ttu-id="6d33b-130">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="6d33b-130">Resource: Type</span></span>
   4. <span data-ttu-id="6d33b-131">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="6d33b-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="6d33b-132">FhirVersion (notre code nécessite cela pour comprendre la version à laquelle nous devons faire pivoter.)</span><span class="sxs-lookup"><span data-stu-id="6d33b-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="6d33b-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="6d33b-134">Patient</span><span class="sxs-lookup"><span data-stu-id="6d33b-134">Patient</span></span>

<span data-ttu-id="6d33b-135">Voici les champs requis au minimum, qui sont un sous-ensemble des champs du profil du patient Argonaut :</span><span class="sxs-lookup"><span data-stu-id="6d33b-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="6d33b-136">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="6d33b-136">Name.Given</span></span>
2. <span data-ttu-id="6d33b-137">Name. Family</span><span class="sxs-lookup"><span data-stu-id="6d33b-137">Name.Family</span></span>
3. <span data-ttu-id="6d33b-138">Public</span><span class="sxs-lookup"><span data-stu-id="6d33b-138">Gender</span></span>
4. <span data-ttu-id="6d33b-139">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="6d33b-139">BirthDate</span></span>
5. <span data-ttu-id="6d33b-140">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="6d33b-140">MRN (Identifier)</span></span>

<span data-ttu-id="6d33b-141">Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6d33b-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="6d33b-142">Name.Use</span></span>
2. <span data-ttu-id="6d33b-143">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="6d33b-143">Name.Prefix</span></span>
3. <span data-ttu-id="6d33b-144">[GeneralPractitioner] : la référence GeneralPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)</span><span class="sxs-lookup"><span data-stu-id="6d33b-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="6d33b-145">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-146">ID</span><span class="sxs-lookup"><span data-stu-id="6d33b-146">id</span></span>
2. <span data-ttu-id="6d33b-147">famille = (recherche tous les patients dont le nom de famille contient la valeur)</span><span class="sxs-lookup"><span data-stu-id="6d33b-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="6d33b-148">accordé =\<substring></span><span class="sxs-lookup"><span data-stu-id="6d33b-148">given=\<substring></span></span>
4. <span data-ttu-id="6d33b-149">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="6d33b-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="6d33b-150">sexe = (valeurs faisant partie d’un compte d’administrateur-sexe)</span><span class="sxs-lookup"><span data-stu-id="6d33b-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="6d33b-151">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="6d33b-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="6d33b-152">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche et du \_ comptage qui seront utilisés par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="6d33b-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="6d33b-153">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="6d33b-153">identifier=\<mrn></span></span>

<span data-ttu-id="6d33b-154">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="6d33b-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="6d33b-155">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="6d33b-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="6d33b-156">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="6d33b-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="6d33b-157">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="6d33b-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="6d33b-158">Nom</span><span class="sxs-lookup"><span data-stu-id="6d33b-158">Name</span></span>
- <span data-ttu-id="6d33b-159">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="6d33b-159">Birthdate</span></span>

<span data-ttu-id="6d33b-160">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="6d33b-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="6d33b-161">Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="6d33b-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="6d33b-162">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "meta" : {"lastUpdated" : "2019-01-14T23:44:45.052 + 00:00"}, "tapez" : "searchset", "total" : 1, "Self", "URL" : « auto », « URL » : <fhir-Server>/patient/_search "}]," entrée " : [{" fullUrl " : <fhir-Server>/patient/<patient-ID>", "ressource" : {"resourceType" : "patient", "ID" : "<patient-ID>", "meta" : {"versionId" : "1", "lastUpdated" : "2017-10-18T18:32:37.000 + 00:00"}, "texte" : {"Status" : "generated", "div" : "</span><span class="sxs-lookup"><span data-stu-id="6d33b-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="6d33b-163">\n</span><span class="sxs-lookup"><span data-stu-id="6d33b-163">\n</span></span>        <p><span data-ttu-id="6d33b-164">Noir Ruth</span><span class="sxs-lookup"><span data-stu-id="6d33b-164">Ruth Black</span></span></p><span data-ttu-id="6d33b-165">\n</span><span class="sxs-lookup"><span data-stu-id="6d33b-165">\n</span></span>      </div><span data-ttu-id="6d33b-166">"}," identificateur " : [{" use " :" usuelle "," type " : {" codification " : [{" System " :" https://hl7.org/fhir/v2/0203 "," code " :" Mr "," Display "," "userSelected" : false}], "texte" : "" http://hospital.smarthealthit.org , "", "", "", "", "valeur" : "1234567"}], "actif" : vrai, "nom" : "" ";" ""; ""; ""; "" ";"</span><span class="sxs-lookup"><span data-stu-id="6d33b-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="6d33b-167">]}], "Telecom" : [{"système" : "téléphone", "valeur" : "800-599-2739", "utiliser" : "maison"}, {"système" : "téléphone", "valeur" : "800-808-7785", "utiliser" : "mobile"}, {"système" : "ruth.black@example.com" = "" valeur "femelle", "DateNaissance" : "1951-08-23", "adresse" : [{"utiliser" : "maison", "ligne" : ["26 South RdApt 22"], "ville" : "sapâtea", "État" : "OK", "CodePostal" : "74066", "Country" : "USA"}]), "Search" : {"mode" : "match"}})}</span><span class="sxs-lookup"><span data-stu-id="6d33b-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="6d33b-168">Demande : obtenez <fhir-Server>/patient/<patient-ID></span><span class="sxs-lookup"><span data-stu-id="6d33b-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="6d33b-169">Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>", "identificateur" : [{"use" : "usuelle", "type" : {"codage" : [{"système" : " https://hl7.org/fhir/v2/0203 ", "code" : "Mr",}], "texte" : "le numéro de l’enregistrement médical"}, "valeur" : "1234567"}], "nom" : [{"utiliser" : "officiel", "famille" : "Adams", ""» : "Michel", "X."</span><span class="sxs-lookup"><span data-stu-id="6d33b-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="6d33b-170">]}], "sexe" : "mâle", "DateNaissance" : "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="6d33b-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="6d33b-171">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="6d33b-172">Déterminée</span><span class="sxs-lookup"><span data-stu-id="6d33b-172">Observation</span></span>

<span data-ttu-id="6d33b-173">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de signes vitaux de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="6d33b-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="6d33b-174">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="6d33b-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="6d33b-175">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="6d33b-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="6d33b-176">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="6d33b-176">ValueQuantity.Value</span></span>

<span data-ttu-id="6d33b-177">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6d33b-178">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="6d33b-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="6d33b-179">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="6d33b-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="6d33b-180">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-181">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-181">patient=\<patient id></span></span>
2. <span data-ttu-id="6d33b-182">_sort = date</span><span class="sxs-lookup"><span data-stu-id="6d33b-182">_sort=-date</span></span>
3. <span data-ttu-id="6d33b-183">Category (nous interrogerons « Category = vitaux-Sign-signes ») pour récupérer la liste des signes vitaux.</span><span class="sxs-lookup"><span data-stu-id="6d33b-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="6d33b-184">Reportez-vous à cet exemple de l’appel :</span><span class="sxs-lookup"><span data-stu-id="6d33b-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="6d33b-185">Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&catégorie = vitaux-signes</span><span class="sxs-lookup"><span data-stu-id="6d33b-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="6d33b-186">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-ID>", "category" : [{"code" : [{"System", " https://hl7.org/fhir/observation-category ", "code" : "" code " : {" Coding " : [{" System " :" http://loinc.org "," code " :" 8867-4 "," Display " :" heart_rate "}]}," effectiveDateTime " :" 2009-04-08T00:00:00-06:00 "," valueQuantity " : {" value " : 72,0," Unit " :" {temps} minute "," système " :" http://unitsofmeasure.org ",}}},.</span><span class="sxs-lookup"><span data-stu-id="6d33b-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="6d33b-187">.</span><span class="sxs-lookup"><span data-stu-id="6d33b-187">.</span></span>
        <span data-ttu-id="6d33b-188">.</span><span class="sxs-lookup"><span data-stu-id="6d33b-188">.</span></span>
      <span data-ttu-id="6d33b-189">] }</span><span class="sxs-lookup"><span data-stu-id="6d33b-189">] }</span></span>

* * *

<span data-ttu-id="6d33b-190">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="6d33b-191">Condition</span><span class="sxs-lookup"><span data-stu-id="6d33b-191">Condition</span></span>

<span data-ttu-id="6d33b-192">Voici les champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="6d33b-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="6d33b-193">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="6d33b-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="6d33b-194">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6d33b-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="6d33b-195">AssertedDate</span></span>
2. <span data-ttu-id="6d33b-196">Minimal</span><span class="sxs-lookup"><span data-stu-id="6d33b-196">Severity</span></span>

<span data-ttu-id="6d33b-197">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-198">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-198">patient=\<patient id></span></span>
2. <span data-ttu-id="6d33b-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6d33b-199">_count=\<max results></span></span>

<span data-ttu-id="6d33b-200">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="6d33b-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="6d33b-201">Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="6d33b-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="6d33b-202">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 2, "entry" : [{"Resource" : {"resourceType" = "condition", "ID" : "<-ID>", "code" : {"code" http://snomed.info/sct "," code " :" 185903001 "," Display " :" nécessite une immunisation de la grippe ",}]}," gravité " : {" codage " : [{" System " :" http://snomed.info/sct "," code " :" 24484000 "," Display " :" assertedDate "}}," " :" 2018-04-04 "}};</span><span class="sxs-lookup"><span data-stu-id="6d33b-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="6d33b-203">.</span><span class="sxs-lookup"><span data-stu-id="6d33b-203">.</span></span>
        <span data-ttu-id="6d33b-204">.</span><span class="sxs-lookup"><span data-stu-id="6d33b-204">.</span></span>
      <span data-ttu-id="6d33b-205">] }</span><span class="sxs-lookup"><span data-stu-id="6d33b-205">] }</span></span>

* * *
<span data-ttu-id="6d33b-206">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="6d33b-207">Connaître</span><span class="sxs-lookup"><span data-stu-id="6d33b-207">Encounter</span></span>

<span data-ttu-id="6d33b-208">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du profil de type [rencontrent des États-Unis](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="6d33b-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="6d33b-209">État</span><span class="sxs-lookup"><span data-stu-id="6d33b-209">Status</span></span>
2. <span data-ttu-id="6d33b-210">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="6d33b-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="6d33b-211">De plus, les champs suivants provenant du cœur Microsoft pour les États-Unis du profil « doivent prendre en charge » :</span><span class="sxs-lookup"><span data-stu-id="6d33b-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="6d33b-212">Période. début</span><span class="sxs-lookup"><span data-stu-id="6d33b-212">Period.Start</span></span>
2. <span data-ttu-id="6d33b-213">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="6d33b-213">Location[0].Location.Display</span></span>

<span data-ttu-id="6d33b-214">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-215">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-215">patient=\<patient id></span></span>
2. <span data-ttu-id="6d33b-216">_sort : DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="6d33b-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="6d33b-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6d33b-217">_count=\<max results></span></span>

<span data-ttu-id="6d33b-218">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="6d33b-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="6d33b-219">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6d33b-219">Each encounter references a location resource.</span></span> <span data-ttu-id="6d33b-220">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6d33b-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="6d33b-221">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="6d33b-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="6d33b-222">AllergyIntolerance</span></span>

<span data-ttu-id="6d33b-223">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="6d33b-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="6d33b-224">Code. Text</span><span class="sxs-lookup"><span data-stu-id="6d33b-224">Code.Text</span></span>
2. <span data-ttu-id="6d33b-225">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="6d33b-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="6d33b-226">ClinicalStatus/VerificationStatus (nous avons lu les deux)</span><span class="sxs-lookup"><span data-stu-id="6d33b-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="6d33b-227">Outre les champs Argonaut, pour optimiser l’utilisation de l’application patients, l’application patients peut également lire le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="6d33b-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="6d33b-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="6d33b-228">AssertedDate</span></span>
2. <span data-ttu-id="6d33b-229">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="6d33b-229">Note.Text</span></span>
3. <span data-ttu-id="6d33b-230">Réaction</span><span class="sxs-lookup"><span data-stu-id="6d33b-230">Reaction</span></span>
    1. <span data-ttu-id="6d33b-231">Substance (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="6d33b-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="6d33b-232">Manifeste (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="6d33b-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="6d33b-233">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-234">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-234">Patient =  \<patient id></span></span>

<span data-ttu-id="6d33b-235">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="6d33b-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="6d33b-236">Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID></span><span class="sxs-lookup"><span data-stu-id="6d33b-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="6d33b-237">Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType", "AllergyIntolerance", "ID" : "<-ID>", "clinicalStatus" : "actif", "verificationStatus" : "confirmé", "code" : {"code" : "", "code" : http://rxnav.nlm.nih.gov/REST/Ndfrt "N0000175503", "Display" : "sulfonamide antibactérienne",}], "texte" : "sulfonamide antibactérienne"}, "assertedDate" : "2018-01-01T00:00:00-07:00", "réaction" : [{"se manifester" : [{"codage" : [{"système" : " http://snomed.info/sct ", "code" : "271807003", "Display" : "Skin rash",}), "Text" : "Skin rash"}]</span><span class="sxs-lookup"><span data-stu-id="6d33b-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="6d33b-238">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="6d33b-239">Demande de médication</span><span class="sxs-lookup"><span data-stu-id="6d33b-239">Medication Request</span></span>

<span data-ttu-id="6d33b-240">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de demande de médicament principal pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="6d33b-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="6d33b-241">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="6d33b-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="6d33b-242">Médication. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="6d33b-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="6d33b-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="6d33b-243">AuthoredOn</span></span>
4. <span data-ttu-id="6d33b-244">Demandeur. agent. Display</span><span class="sxs-lookup"><span data-stu-id="6d33b-244">Requester.Agent.Display</span></span>

<span data-ttu-id="6d33b-245">Outre les champs de base américaine, l’application patients peut également lire les champs suivants pour une utilisation optimale :</span><span class="sxs-lookup"><span data-stu-id="6d33b-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6d33b-246">DosageInstruction[..]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="6d33b-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="6d33b-247">Synthèse</span><span class="sxs-lookup"><span data-stu-id="6d33b-247">Text</span></span>

<span data-ttu-id="6d33b-248">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-249">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-249">patient=\<patient id></span></span>
2. <span data-ttu-id="6d33b-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6d33b-250">_count=\<max results></span></span>

<span data-ttu-id="6d33b-251">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="6d33b-252">Articles</span><span class="sxs-lookup"><span data-stu-id="6d33b-252">Coverage</span></span>

<span data-ttu-id="6d33b-253">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="6d33b-254">Regroupement d’au moins un élément avec</span><span class="sxs-lookup"><span data-stu-id="6d33b-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="6d33b-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="6d33b-255">GroupDisplay</span></span>
    2. <span data-ttu-id="6d33b-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="6d33b-256">PlanDisplay</span></span>
2. <span data-ttu-id="6d33b-257">Donnée</span><span class="sxs-lookup"><span data-stu-id="6d33b-257">Period</span></span>
3. <span data-ttu-id="6d33b-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="6d33b-258">SubscriberId</span></span>

<span data-ttu-id="6d33b-259">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d33b-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6d33b-260">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="6d33b-260">Patient = \<patient id></span></span>

<span data-ttu-id="6d33b-261">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="6d33b-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
