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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772205"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="fc4bd-103">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="fc4bd-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="fc4bd-104">À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="fc4bd-105">Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="fc4bd-106">Consultez le modèle patients dans les listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="fc4bd-107">Pour en savoir plus sur la gestion de l’application listes dans votre organisation, voir [gérer l’application listes](../../manage-lists-app.md) .</span><span class="sxs-lookup"><span data-stu-id="fc4bd-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="fc4bd-108">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fc4bd-109">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fc4bd-110">Patient</span><span class="sxs-lookup"><span data-stu-id="fc4bd-110">Patient</span></span>](#patient)
- [<span data-ttu-id="fc4bd-111">Déterminée</span><span class="sxs-lookup"><span data-stu-id="fc4bd-111">Observation</span></span>](#observation)
- [<span data-ttu-id="fc4bd-112">Condition</span><span class="sxs-lookup"><span data-stu-id="fc4bd-112">Condition</span></span>](#condition)
- [<span data-ttu-id="fc4bd-113">Connaître</span><span class="sxs-lookup"><span data-stu-id="fc4bd-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fc4bd-114">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="fc4bd-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fc4bd-115">Articles</span><span class="sxs-lookup"><span data-stu-id="fc4bd-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="fc4bd-116">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="fc4bd-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="fc4bd-117">Emplacement</span><span class="sxs-lookup"><span data-stu-id="fc4bd-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="fc4bd-118">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="fc4bd-119">Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fc4bd-120">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources ont une offre groupée (lot) de requêtes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fc4bd-121">Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fc4bd-122">Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="fc4bd-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="fc4bd-123">Toutes les ressources FHIR suivantes doivent être accessibles par référence directe aux ressources.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="fc4bd-124">Jeu de champs requis de conformité</span><span class="sxs-lookup"><span data-stu-id="fc4bd-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="fc4bd-125">Le serveur FHIR doit mettre en œuvre la déclaration de conformité afin d’avoir une synthèse factuelle de ses capacités.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="fc4bd-126">Nous attendons les paramètres ci-dessous dans un DSTU2 FHIR Server :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="fc4bd-127">LAISSER</span><span class="sxs-lookup"><span data-stu-id="fc4bd-127">REST</span></span>

    - <span data-ttu-id="fc4bd-128">Veille</span><span class="sxs-lookup"><span data-stu-id="fc4bd-128">Mode</span></span>
    - <span data-ttu-id="fc4bd-129">Interaction</span><span class="sxs-lookup"><span data-stu-id="fc4bd-129">Interaction</span></span>
    - <span data-ttu-id="fc4bd-130">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="fc4bd-130">Resource: Type</span></span>
    - <span data-ttu-id="fc4bd-131">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="fc4bd-132">FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="fc4bd-133">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fc4bd-134">Patient</span><span class="sxs-lookup"><span data-stu-id="fc4bd-134">Patient</span></span>

<span data-ttu-id="fc4bd-135">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="fc4bd-136">Name. Family</span><span class="sxs-lookup"><span data-stu-id="fc4bd-136">Name.Family</span></span>
 - <span data-ttu-id="fc4bd-137">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="fc4bd-137">Name.Given</span></span>
 - <span data-ttu-id="fc4bd-138">Public</span><span class="sxs-lookup"><span data-stu-id="fc4bd-138">Gender</span></span>
 - <span data-ttu-id="fc4bd-139">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="fc4bd-139">BirthDate</span></span>
 - <span data-ttu-id="fc4bd-140">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-140">MRN (Identifier)</span></span>

<span data-ttu-id="fc4bd-141">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fc4bd-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="fc4bd-142">Name.Use</span></span>
 - <span data-ttu-id="fc4bd-143">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="fc4bd-143">Name.Prefix</span></span>
 - <span data-ttu-id="fc4bd-144">CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="fc4bd-145">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-146">ID</span><span class="sxs-lookup"><span data-stu-id="fc4bd-146">id</span></span>
 - <span data-ttu-id="fc4bd-147">famille : contient = (recherche les patients dont le nom de famille contient la valeur.)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="fc4bd-148">accordé =\<substring></span><span class="sxs-lookup"><span data-stu-id="fc4bd-148">given=\<substring></span></span>
 - <span data-ttu-id="fc4bd-149">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="fc4bd-149">name=\<substring></span></span>
 - <span data-ttu-id="fc4bd-150">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="fc4bd-151">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fc4bd-152">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_ le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="fc4bd-153">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="fc4bd-153">identifier=\<mrn></span></span>

<span data-ttu-id="fc4bd-154">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fc4bd-155">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fc4bd-156">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fc4bd-157">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR</span><span class="sxs-lookup"><span data-stu-id="fc4bd-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="fc4bd-158">Nom</span><span class="sxs-lookup"><span data-stu-id="fc4bd-158">Name</span></span>
- <span data-ttu-id="fc4bd-159">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="fc4bd-159">Birthdate</span></span>

<span data-ttu-id="fc4bd-160">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-160">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="fc4bd-161">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fc4bd-162">Déterminée</span><span class="sxs-lookup"><span data-stu-id="fc4bd-162">Observation</span></span>

<span data-ttu-id="fc4bd-163">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="fc4bd-164">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="fc4bd-165">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="fc4bd-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="fc4bd-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="fc4bd-166">ValueQuantity.Value</span></span>

<span data-ttu-id="fc4bd-167">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fc4bd-168">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="fc4bd-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="fc4bd-169">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="fc4bd-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="fc4bd-170">S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="fc4bd-171">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-172">patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="fc4bd-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="fc4bd-173">Trier : DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="fc4bd-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="fc4bd-174">L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="fc4bd-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="fc4bd-175">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fc4bd-176">Condition</span><span class="sxs-lookup"><span data-stu-id="fc4bd-176">Condition</span></span>

<span data-ttu-id="fc4bd-177">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="fc4bd-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="fc4bd-178">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fc4bd-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="fc4bd-179">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fc4bd-180">Date d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="fc4bd-180">Date Recorded</span></span>
 - <span data-ttu-id="fc4bd-181">Minimal</span><span class="sxs-lookup"><span data-stu-id="fc4bd-181">Severity</span></span>

<span data-ttu-id="fc4bd-182">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-183">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fc4bd-183">patient=\<patient id></span></span>
 - <span data-ttu-id="fc4bd-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fc4bd-184">_count=\<max results></span></span>

<span data-ttu-id="fc4bd-185">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="fc4bd-186">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fc4bd-187">Connaître</span><span class="sxs-lookup"><span data-stu-id="fc4bd-187">Encounter</span></span>

<span data-ttu-id="fc4bd-188">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="fc4bd-189">État</span><span class="sxs-lookup"><span data-stu-id="fc4bd-189">Status</span></span>
 - <span data-ttu-id="fc4bd-190">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fc4bd-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fc4bd-191">De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="fc4bd-192">Période. début</span><span class="sxs-lookup"><span data-stu-id="fc4bd-192">Period.Start</span></span>
 - <span data-ttu-id="fc4bd-193">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="fc4bd-193">Location[0].Location.Display</span></span>

<span data-ttu-id="fc4bd-194">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-195">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fc4bd-195">patient=\<patient id></span></span>
 - <span data-ttu-id="fc4bd-196">_sort : DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="fc4bd-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="fc4bd-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fc4bd-197">_count=\<max results></span></span>

<span data-ttu-id="fc4bd-198">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="fc4bd-199">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-199">Each encounter references a location resource.</span></span> <span data-ttu-id="fc4bd-200">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="fc4bd-201">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-201">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="fc4bd-202">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fc4bd-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fc4bd-203">AllergyIntolerance</span></span>

<span data-ttu-id="fc4bd-204">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="fc4bd-205">Code. Text</span><span class="sxs-lookup"><span data-stu-id="fc4bd-205">Code.Text</span></span>
 - <span data-ttu-id="fc4bd-206">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fc4bd-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="fc4bd-207">État</span><span class="sxs-lookup"><span data-stu-id="fc4bd-207">Status</span></span>

<span data-ttu-id="fc4bd-208">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fc4bd-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="fc4bd-209">RecordedDate</span></span>
 - <span data-ttu-id="fc4bd-210">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="fc4bd-210">Note.Text</span></span>
 - <span data-ttu-id="fc4bd-211">Réaction [...]. Substance. texte</span><span class="sxs-lookup"><span data-stu-id="fc4bd-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="fc4bd-212">Réaction [...]. Manifeste [...]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="fc4bd-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="fc4bd-213">Text. div</span><span class="sxs-lookup"><span data-stu-id="fc4bd-213">Text.Div</span></span>

<span data-ttu-id="fc4bd-214">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-215">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="fc4bd-215">Patient =  \<patient id></span></span>

<span data-ttu-id="fc4bd-216">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-216">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="fc4bd-217">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="fc4bd-218">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="fc4bd-218">Medication Order</span></span>

<span data-ttu-id="fc4bd-219">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="fc4bd-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="fc4bd-220">DateWritten</span></span>
 - <span data-ttu-id="fc4bd-221">Ordonnateur. Display</span><span class="sxs-lookup"><span data-stu-id="fc4bd-221">Prescriber.Display</span></span>
 - <span data-ttu-id="fc4bd-222">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="fc4bd-223">Medication. Text (si concept)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="fc4bd-224">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fc4bd-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="fc4bd-225">DateEnded</span></span>
 - <span data-ttu-id="fc4bd-226">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="fc4bd-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="fc4bd-227">Text. div</span><span class="sxs-lookup"><span data-stu-id="fc4bd-227">Text.Div</span></span>

<span data-ttu-id="fc4bd-228">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-229">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fc4bd-229">patient=\<patient id></span></span>
 - <span data-ttu-id="fc4bd-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fc4bd-230">_count=\<max results></span></span>

<span data-ttu-id="fc4bd-231">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-231">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="fc4bd-232">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fc4bd-233">Articles</span><span class="sxs-lookup"><span data-stu-id="fc4bd-233">Coverage</span></span>

<span data-ttu-id="fc4bd-234">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="fc4bd-235">Payor</span><span class="sxs-lookup"><span data-stu-id="fc4bd-235">Payor</span></span>

<span data-ttu-id="fc4bd-236">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fc4bd-237">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fc4bd-237">patient=\<patient id></span></span>

<span data-ttu-id="fc4bd-238">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fc4bd-238">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="fc4bd-239">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="fc4bd-240">Lieu</span><span class="sxs-lookup"><span data-stu-id="fc4bd-240">Location</span></span>

<span data-ttu-id="fc4bd-241">Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="fc4bd-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="fc4bd-242">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
