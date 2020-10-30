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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803492"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="726a4-103">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="726a4-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="726a4-104">À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="726a4-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="726a4-105">Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe.</span><span class="sxs-lookup"><span data-stu-id="726a4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="726a4-106">Toutes les données associées à l’application patients sont conservées dans ce groupe, mais vous ne pouvez plus y accéder par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="726a4-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="726a4-107">Les utilisateurs peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="726a4-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="726a4-108">Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale.</span><span class="sxs-lookup"><span data-stu-id="726a4-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="726a4-109">Consultez le modèle patients dans les listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="726a4-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="726a4-110">Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="726a4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="726a4-111">La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder.</span><span class="sxs-lookup"><span data-stu-id="726a4-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="726a4-112">Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="726a4-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="726a4-113">Patient</span><span class="sxs-lookup"><span data-stu-id="726a4-113">Patient</span></span>](#patient)
- [<span data-ttu-id="726a4-114">Déterminée</span><span class="sxs-lookup"><span data-stu-id="726a4-114">Observation</span></span>](#observation)
- [<span data-ttu-id="726a4-115">Condition</span><span class="sxs-lookup"><span data-stu-id="726a4-115">Condition</span></span>](#condition)
- [<span data-ttu-id="726a4-116">Connaître</span><span class="sxs-lookup"><span data-stu-id="726a4-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="726a4-117">Intolérance des allergies</span><span class="sxs-lookup"><span data-stu-id="726a4-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="726a4-118">Articles</span><span class="sxs-lookup"><span data-stu-id="726a4-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="726a4-119">[État de médication](#medication-request) (remplace le MedicationOrder dans la version DSTU2 du PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="726a4-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="726a4-120">Emplacement (les informations requises par cette ressource peuvent être intégrées à la rencontre)</span><span class="sxs-lookup"><span data-stu-id="726a4-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="726a4-121">La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout); Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="726a4-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="726a4-122">Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources publient une offre (BATCH) de requêtes dans l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="726a4-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="726a4-123">Le serveur traitera chaque demande et renverra une offre de ressources correspondant à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="726a4-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="726a4-124">Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="726a4-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="726a4-125">Instruction Capability</span><span class="sxs-lookup"><span data-stu-id="726a4-125">Capability Statement</span></span>

<span data-ttu-id="726a4-126">Voici les champs obligatoires obligatoires :</span><span class="sxs-lookup"><span data-stu-id="726a4-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="726a4-127">LAISSER</span><span class="sxs-lookup"><span data-stu-id="726a4-127">REST</span></span>

    - <span data-ttu-id="726a4-128">Veille</span><span class="sxs-lookup"><span data-stu-id="726a4-128">Mode</span></span>
    - <span data-ttu-id="726a4-129">Interaction</span><span class="sxs-lookup"><span data-stu-id="726a4-129">Interaction</span></span>
    - <span data-ttu-id="726a4-130">Ressource : type</span><span class="sxs-lookup"><span data-stu-id="726a4-130">Resource: Type</span></span>
    - <span data-ttu-id="726a4-131">Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="726a4-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="726a4-132">FhirVersion (notre code nécessite cela pour comprendre la version à laquelle nous devons faire pivoter.)</span><span class="sxs-lookup"><span data-stu-id="726a4-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="726a4-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="726a4-134">Patient</span><span class="sxs-lookup"><span data-stu-id="726a4-134">Patient</span></span>

<span data-ttu-id="726a4-135">Voici les champs requis au minimum, qui sont un sous-ensemble des champs du profil du patient Argonaut :</span><span class="sxs-lookup"><span data-stu-id="726a4-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="726a4-136">Nom. fourni</span><span class="sxs-lookup"><span data-stu-id="726a4-136">Name.Given</span></span>
 - <span data-ttu-id="726a4-137">Name. Family</span><span class="sxs-lookup"><span data-stu-id="726a4-137">Name.Family</span></span>
 - <span data-ttu-id="726a4-138">Public</span><span class="sxs-lookup"><span data-stu-id="726a4-138">Gender</span></span>
 - <span data-ttu-id="726a4-139">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="726a4-139">BirthDate</span></span>
 - <span data-ttu-id="726a4-140">NRM (identificateur)</span><span class="sxs-lookup"><span data-stu-id="726a4-140">MRN (Identifier)</span></span>

<span data-ttu-id="726a4-141">Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="726a4-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="726a4-142">Name.Use</span></span>
 - <span data-ttu-id="726a4-143">Nom. préfixe</span><span class="sxs-lookup"><span data-stu-id="726a4-143">Name.Prefix</span></span>
 - <span data-ttu-id="726a4-144">[GeneralPractitioner] : la référence GeneralPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)</span><span class="sxs-lookup"><span data-stu-id="726a4-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="726a4-145">Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="726a4-146">ID</span><span class="sxs-lookup"><span data-stu-id="726a4-146">id</span></span>
 - <span data-ttu-id="726a4-147">famille = (recherche tous les patients dont le nom de famille contient la valeur)</span><span class="sxs-lookup"><span data-stu-id="726a4-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="726a4-148">accordé =\<substring></span><span class="sxs-lookup"><span data-stu-id="726a4-148">given=\<substring></span></span>
 - <span data-ttu-id="726a4-149">DateNaissance = (correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="726a4-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="726a4-150">sexe = (valeurs faisant partie d’un compte d’administrateur-sexe)</span><span class="sxs-lookup"><span data-stu-id="726a4-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="726a4-151">\_nombre (nombre maximal de résultats à renvoyer)</span><span class="sxs-lookup"><span data-stu-id="726a4-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="726a4-152">La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche et du \_ comptage qui seront utilisés par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.</span><span class="sxs-lookup"><span data-stu-id="726a4-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="726a4-153">identificateur =\<mrn></span><span class="sxs-lookup"><span data-stu-id="726a4-153">identifier=\<mrn></span></span>

<span data-ttu-id="726a4-154">L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="726a4-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="726a4-155">ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="726a4-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="726a4-156">NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait.</span><span class="sxs-lookup"><span data-stu-id="726a4-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="726a4-157">Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR.</span><span class="sxs-lookup"><span data-stu-id="726a4-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="726a4-158">Nom</span><span class="sxs-lookup"><span data-stu-id="726a4-158">Name</span></span>
- <span data-ttu-id="726a4-159">Anniversaire</span><span class="sxs-lookup"><span data-stu-id="726a4-159">Birthdate</span></span>

<span data-ttu-id="726a4-160">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="726a4-160">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="726a4-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="726a4-162">Déterminée</span><span class="sxs-lookup"><span data-stu-id="726a4-162">Observation</span></span>

<span data-ttu-id="726a4-163">Il s’agit des champs requis au minimum, qui sont un sous-ensemble de [Argonaut Vital-Signs profil](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="726a4-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="726a4-164">Effective (heure de date ou période)</span><span class="sxs-lookup"><span data-stu-id="726a4-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="726a4-165">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="726a4-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="726a4-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="726a4-166">ValueQuantity.Value</span></span>

<span data-ttu-id="726a4-167">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="726a4-168">Code. Coding. Display</span><span class="sxs-lookup"><span data-stu-id="726a4-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="726a4-169">ValueQuantity. Unit</span><span class="sxs-lookup"><span data-stu-id="726a4-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="726a4-170">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-171">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-171">patient=\<patient id></span></span>
 - <span data-ttu-id="726a4-172">_sort = date</span><span class="sxs-lookup"><span data-stu-id="726a4-172">_sort=-date</span></span>
 - <span data-ttu-id="726a4-173">Category (nous interrogerons « Category = vitaux-Sign-signes ») pour récupérer la liste des signes vitaux.</span><span class="sxs-lookup"><span data-stu-id="726a4-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="726a4-174">Reportez-vous à cet exemple de l’appel :</span><span class="sxs-lookup"><span data-stu-id="726a4-174">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="726a4-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="726a4-176">Condition</span><span class="sxs-lookup"><span data-stu-id="726a4-176">Condition</span></span>

<span data-ttu-id="726a4-177">Voici les champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="726a4-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="726a4-178">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="726a4-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="726a4-179">Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="726a4-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="726a4-180">AssertedDate</span></span>
 - <span data-ttu-id="726a4-181">Minimal</span><span class="sxs-lookup"><span data-stu-id="726a4-181">Severity</span></span>

<span data-ttu-id="726a4-182">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-183">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-183">patient=\<patient id></span></span>
 - <span data-ttu-id="726a4-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="726a4-184">_count=\<max results></span></span>

<span data-ttu-id="726a4-185">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="726a4-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="726a4-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="726a4-187">Connaître</span><span class="sxs-lookup"><span data-stu-id="726a4-187">Encounter</span></span>

<span data-ttu-id="726a4-188">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du profil de type [rencontrent des États-Unis](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="726a4-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="726a4-189">État</span><span class="sxs-lookup"><span data-stu-id="726a4-189">Status</span></span>
 - <span data-ttu-id="726a4-190">Tapez [0]. Code [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="726a4-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="726a4-191">De plus, les champs suivants provenant du cœur Microsoft pour les États-Unis du profil « doivent prendre en charge » :</span><span class="sxs-lookup"><span data-stu-id="726a4-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="726a4-192">Période. début</span><span class="sxs-lookup"><span data-stu-id="726a4-192">Period.Start</span></span>
 - <span data-ttu-id="726a4-193">Emplacement [0]. Emplacement. Display</span><span class="sxs-lookup"><span data-stu-id="726a4-193">Location[0].Location.Display</span></span>

<span data-ttu-id="726a4-194">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-195">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-195">patient=\<patient id></span></span>
 - <span data-ttu-id="726a4-196">_sort : DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="726a4-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="726a4-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="726a4-197">_count=\<max results></span></span>

<span data-ttu-id="726a4-198">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="726a4-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="726a4-199">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="726a4-199">Each encounter references a location resource.</span></span> <span data-ttu-id="726a4-200">La référence inclut également le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="726a4-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="726a4-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="726a4-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="726a4-202">AllergyIntolerance</span></span>

<span data-ttu-id="726a4-203">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="726a4-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="726a4-204">Code. Text</span><span class="sxs-lookup"><span data-stu-id="726a4-204">Code.Text</span></span>
 - <span data-ttu-id="726a4-205">Code. Coding [0]. 3D</span><span class="sxs-lookup"><span data-stu-id="726a4-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="726a4-206">ClinicalStatus/VerificationStatus (nous avons lu les deux)</span><span class="sxs-lookup"><span data-stu-id="726a4-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="726a4-207">Outre les champs Argonaut, pour optimiser l’utilisation de l’application patients, l’application patients peut également lire le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="726a4-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="726a4-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="726a4-208">AssertedDate</span></span>
 - <span data-ttu-id="726a4-209">Remarque. Text</span><span class="sxs-lookup"><span data-stu-id="726a4-209">Note.Text</span></span>
 - <span data-ttu-id="726a4-210">Réaction</span><span class="sxs-lookup"><span data-stu-id="726a4-210">Reaction</span></span>
    - <span data-ttu-id="726a4-211">Substance (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="726a4-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="726a4-212">Manifeste (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="726a4-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="726a4-213">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-214">Patient =  \<patient id></span></span>

<span data-ttu-id="726a4-215">Pour plus d’informations, reportez-vous à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="726a4-215">See the following example of the call:</span></span> 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="726a4-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="726a4-217">Demande de médication</span><span class="sxs-lookup"><span data-stu-id="726a4-217">Medication Request</span></span>

<span data-ttu-id="726a4-218">Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de demande de médicament principal pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="726a4-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="726a4-219">Médication. Display (Si référence)</span><span class="sxs-lookup"><span data-stu-id="726a4-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="726a4-220">Médication. Text (si CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="726a4-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="726a4-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="726a4-221">AuthoredOn</span></span>
 - <span data-ttu-id="726a4-222">Demandeur. agent. Display</span><span class="sxs-lookup"><span data-stu-id="726a4-222">Requester.Agent.Display</span></span>

<span data-ttu-id="726a4-223">Outre les champs de base américaine, l’application patients peut également lire les champs suivants pour une utilisation optimale :</span><span class="sxs-lookup"><span data-stu-id="726a4-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="726a4-224">DosageInstruction[..]. Synthèse</span><span class="sxs-lookup"><span data-stu-id="726a4-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="726a4-225">Synthèse</span><span class="sxs-lookup"><span data-stu-id="726a4-225">Text</span></span>

<span data-ttu-id="726a4-226">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-227">patient =\<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-227">patient=\<patient id></span></span>
 - <span data-ttu-id="726a4-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="726a4-228">_count=\<max results></span></span>

<span data-ttu-id="726a4-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="726a4-230">Articles</span><span class="sxs-lookup"><span data-stu-id="726a4-230">Coverage</span></span>

<span data-ttu-id="726a4-231">Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="726a4-232">Regroupement d’au moins un élément avec</span><span class="sxs-lookup"><span data-stu-id="726a4-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="726a4-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="726a4-233">GroupDisplay</span></span>
    - <span data-ttu-id="726a4-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="726a4-234">PlanDisplay</span></span>
 - <span data-ttu-id="726a4-235">Donnée</span><span class="sxs-lookup"><span data-stu-id="726a4-235">Period</span></span>
 - <span data-ttu-id="726a4-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="726a4-236">SubscriberId</span></span>

<span data-ttu-id="726a4-237">Une recherche de ressource utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="726a4-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="726a4-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="726a4-238">Patient = \<patient id></span></span>

<span data-ttu-id="726a4-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.</span><span class="sxs-lookup"><span data-stu-id="726a4-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
