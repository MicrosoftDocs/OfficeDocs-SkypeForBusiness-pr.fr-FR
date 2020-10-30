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
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803482"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="fdb6e-103">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="fdb6e-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="fdb6e-104">À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="fdb6e-105">Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="fdb6e-106">Toutes les données associées à l’application patients sont conservées dans ce groupe, mais vous ne pouvez plus y accéder par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="fdb6e-107">Les utilisateurs peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="fdb6e-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="fdb6e-108">Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="fdb6e-109">Consultez le modèle patients dans les listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="fdb6e-110">Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="fdb6e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="fdb6e-111">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fdb6e-112">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fdb6e-113">Patient</span><span class="sxs-lookup"><span data-stu-id="fdb6e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="fdb6e-114">Déterminée</span><span class="sxs-lookup"><span data-stu-id="fdb6e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="fdb6e-115">Condition</span><span class="sxs-lookup"><span data-stu-id="fdb6e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="fdb6e-116">Connaître</span><span class="sxs-lookup"><span data-stu-id="fdb6e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fdb6e-117">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="fdb6e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fdb6e-118">Articles</span><span class="sxs-lookup"><span data-stu-id="fdb6e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="fdb6e-119">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="fdb6e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="fdb6e-120">Emplacement</span><span class="sxs-lookup"><span data-stu-id="fdb6e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="fdb6e-121">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="fdb6e-122">Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fdb6e-123">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources ont une offre groupée (lot) de requêtes à l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fdb6e-124">Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fdb6e-125">Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="fdb6e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="fdb6e-126">Toutes les ressources FHIR suivantes doivent être accessibles par référence directe aux ressources.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="fdb6e-127">Jeu de champs requis de conformité</span><span class="sxs-lookup"><span data-stu-id="fdb6e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="fdb6e-128">Le serveur FHIR doit mettre en œuvre la déclaration de conformité afin d’avoir une synthèse factuelle de ses capacités.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="fdb6e-129">Nous attendons les paramètres ci-dessous dans un DSTU2 FHIR Server :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="fdb6e-130">LAISSER</span><span class="sxs-lookup"><span data-stu-id="fdb6e-130">REST</span></span>

    - <span data-ttu-id="fdb6e-131">Veille</span><span class="sxs-lookup"><span data-stu-id="fdb6e-131">Mode</span></span>
    - <span data-ttu-id="fdb6e-132">Interaction</span><span class="sxs-lookup"><span data-stu-id="fdb6e-132">Interaction</span></span>
    - <span data-ttu-id="fdb6e-133">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="fdb6e-133">Resource: Type</span></span>
    - <span data-ttu-id="fdb6e-134">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="fdb6e-135">FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="fdb6e-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fdb6e-137">Patient</span><span class="sxs-lookup"><span data-stu-id="fdb6e-137">Patient</span></span>

<span data-ttu-id="fdb6e-138">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="fdb6e-139">Name. Family</span><span class="sxs-lookup"><span data-stu-id="fdb6e-139">Name.Family</span></span>
 - <span data-ttu-id="fdb6e-140">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="fdb6e-140">Name.Given</span></span>
 - <span data-ttu-id="fdb6e-141">Public</span><span class="sxs-lookup"><span data-stu-id="fdb6e-141">Gender</span></span>
 - <span data-ttu-id="fdb6e-142">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="fdb6e-142">BirthDate</span></span>
 - <span data-ttu-id="fdb6e-143">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-143">MRN (Identifier)</span></span>

<span data-ttu-id="fdb6e-144">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fdb6e-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="fdb6e-145">Name.Use</span></span>
 - <span data-ttu-id="fdb6e-146">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="fdb6e-146">Name.Prefix</span></span>
 - <span data-ttu-id="fdb6e-147">CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="fdb6e-148">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-149">ID</span><span class="sxs-lookup"><span data-stu-id="fdb6e-149">id</span></span>
 - <span data-ttu-id="fdb6e-150">famille : contient = (recherche les patients dont le nom de famille contient la valeur.)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="fdb6e-151">accordé =\<substring></span><span class="sxs-lookup"><span data-stu-id="fdb6e-151">given=\<substring></span></span>
 - <span data-ttu-id="fdb6e-152">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="fdb6e-152">name=\<substring></span></span>
 - <span data-ttu-id="fdb6e-153">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="fdb6e-154">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fdb6e-155">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_ le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="fdb6e-156">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="fdb6e-156">identifier=\<mrn></span></span>

<span data-ttu-id="fdb6e-157">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fdb6e-158">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fdb6e-159">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fdb6e-160">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR</span><span class="sxs-lookup"><span data-stu-id="fdb6e-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="fdb6e-161">Nom</span><span class="sxs-lookup"><span data-stu-id="fdb6e-161">Name</span></span>
- <span data-ttu-id="fdb6e-162">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="fdb6e-162">Birthdate</span></span>

<span data-ttu-id="fdb6e-163">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="fdb6e-164">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fdb6e-165">Déterminée</span><span class="sxs-lookup"><span data-stu-id="fdb6e-165">Observation</span></span>

<span data-ttu-id="fdb6e-166">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="fdb6e-167">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="fdb6e-168">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="fdb6e-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="fdb6e-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="fdb6e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="fdb6e-170">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fdb6e-171">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="fdb6e-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="fdb6e-172">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="fdb6e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="fdb6e-173">S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="fdb6e-174">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-175">patient =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="fdb6e-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="fdb6e-176">Trier : DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="fdb6e-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="fdb6e-177">L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="fdb6e-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="fdb6e-178">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fdb6e-179">Condition</span><span class="sxs-lookup"><span data-stu-id="fdb6e-179">Condition</span></span>

<span data-ttu-id="fdb6e-180">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="fdb6e-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="fdb6e-181">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fdb6e-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="fdb6e-182">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fdb6e-183">Date d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="fdb6e-183">Date Recorded</span></span>
 - <span data-ttu-id="fdb6e-184">Minimal</span><span class="sxs-lookup"><span data-stu-id="fdb6e-184">Severity</span></span>

<span data-ttu-id="fdb6e-185">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-186">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fdb6e-186">patient=\<patient id></span></span>
 - <span data-ttu-id="fdb6e-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fdb6e-187">_count=\<max results></span></span>

<span data-ttu-id="fdb6e-188">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-188">See the following example of this call:</span></span>

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

<span data-ttu-id="fdb6e-189">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fdb6e-190">Connaître</span><span class="sxs-lookup"><span data-stu-id="fdb6e-190">Encounter</span></span>

<span data-ttu-id="fdb6e-191">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="fdb6e-192">État</span><span class="sxs-lookup"><span data-stu-id="fdb6e-192">Status</span></span>
 - <span data-ttu-id="fdb6e-193">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fdb6e-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fdb6e-194">De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="fdb6e-195">Période. début</span><span class="sxs-lookup"><span data-stu-id="fdb6e-195">Period.Start</span></span>
 - <span data-ttu-id="fdb6e-196">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="fdb6e-196">Location[0].Location.Display</span></span>

<span data-ttu-id="fdb6e-197">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-198">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fdb6e-198">patient=\<patient id></span></span>
 - <span data-ttu-id="fdb6e-199">_sort : DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="fdb6e-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="fdb6e-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fdb6e-200">_count=\<max results></span></span>

<span data-ttu-id="fdb6e-201">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="fdb6e-202">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-202">Each encounter references a location resource.</span></span> <span data-ttu-id="fdb6e-203">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="fdb6e-204">Pour plus d’informations, reportez-vous à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-204">See the following example of this call.</span></span>

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

<span data-ttu-id="fdb6e-205">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fdb6e-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fdb6e-206">AllergyIntolerance</span></span>

<span data-ttu-id="fdb6e-207">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="fdb6e-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="fdb6e-208">Code.Text</span></span>
 - <span data-ttu-id="fdb6e-209">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="fdb6e-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="fdb6e-210">État</span><span class="sxs-lookup"><span data-stu-id="fdb6e-210">Status</span></span>

<span data-ttu-id="fdb6e-211">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fdb6e-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="fdb6e-212">RecordedDate</span></span>
 - <span data-ttu-id="fdb6e-213">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="fdb6e-213">Note.Text</span></span>
 - <span data-ttu-id="fdb6e-214">Réaction [...]. Substance. texte</span><span class="sxs-lookup"><span data-stu-id="fdb6e-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="fdb6e-215">Réaction [...]. Manifeste [...]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="fdb6e-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="fdb6e-216">Text. div</span><span class="sxs-lookup"><span data-stu-id="fdb6e-216">Text.Div</span></span>

<span data-ttu-id="fdb6e-217">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="fdb6e-218">Patient =  \<patient id></span></span>

<span data-ttu-id="fdb6e-219">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-219">See the following example of this call:</span></span>

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

<span data-ttu-id="fdb6e-220">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="fdb6e-221">Ordre de médication</span><span class="sxs-lookup"><span data-stu-id="fdb6e-221">Medication Order</span></span>

<span data-ttu-id="fdb6e-222">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="fdb6e-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="fdb6e-223">DateWritten</span></span>
 - <span data-ttu-id="fdb6e-224">Ordonnateur. Display</span><span class="sxs-lookup"><span data-stu-id="fdb6e-224">Prescriber.Display</span></span>
 - <span data-ttu-id="fdb6e-225">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="fdb6e-226">Medication. Text (si concept)</span><span class="sxs-lookup"><span data-stu-id="fdb6e-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="fdb6e-227">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fdb6e-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="fdb6e-228">DateEnded</span></span>
 - <span data-ttu-id="fdb6e-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="fdb6e-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="fdb6e-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="fdb6e-230">Text.Div</span></span>

<span data-ttu-id="fdb6e-231">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-232">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fdb6e-232">patient=\<patient id></span></span>
 - <span data-ttu-id="fdb6e-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fdb6e-233">_count=\<max results></span></span>

<span data-ttu-id="fdb6e-234">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-234">See the following example of this call:</span></span>

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

<span data-ttu-id="fdb6e-235">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fdb6e-236">Articles</span><span class="sxs-lookup"><span data-stu-id="fdb6e-236">Coverage</span></span>

<span data-ttu-id="fdb6e-237">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="fdb6e-238">Payor</span><span class="sxs-lookup"><span data-stu-id="fdb6e-238">Payor</span></span>

<span data-ttu-id="fdb6e-239">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fdb6e-240">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fdb6e-240">patient=\<patient id></span></span>

<span data-ttu-id="fdb6e-241">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fdb6e-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="fdb6e-242">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="fdb6e-243">Lieu</span><span class="sxs-lookup"><span data-stu-id="fdb6e-243">Location</span></span>

<span data-ttu-id="fdb6e-244">Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="fdb6e-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="fdb6e-245">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="fdb6e-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
