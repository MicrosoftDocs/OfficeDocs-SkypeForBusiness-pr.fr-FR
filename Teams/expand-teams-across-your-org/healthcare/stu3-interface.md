---
title: Interface De l’application Patients et de l’intégration EHR
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
description: Découvrez comment intégrer des enregistrements d’état d’santé électroniques à l Microsoft Teams patient et à la spécification de l’interface SPECIFICATION3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803492"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="c0ec1-103">Spécification de l’interface STU3</span><span class="sxs-lookup"><span data-stu-id="c0ec1-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="c0ec1-104">À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="c0ec1-105">Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="c0ec1-106">Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="c0ec1-107">Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="c0ec1-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="c0ec1-108">Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.).</span><span class="sxs-lookup"><span data-stu-id="c0ec1-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="c0ec1-109">Pour commencer, consultez le modèle Patients dans listes.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="c0ec1-110">Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="c0ec1-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="c0ec1-111">La configuration ou la reconfiguration d’un serveur FEMBA pour l’Microsoft Teams Patients nécessite de comprendre les données dont l’application a besoin pour accéder.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c0ec1-112">Le serveur F POSTER doit prendre en charge les demandes POST qui utilisent des offres groupées pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c0ec1-113">Patient</span><span class="sxs-lookup"><span data-stu-id="c0ec1-113">Patient</span></span>](#patient)
- [<span data-ttu-id="c0ec1-114">Observation</span><span class="sxs-lookup"><span data-stu-id="c0ec1-114">Observation</span></span>](#observation)
- [<span data-ttu-id="c0ec1-115">Condition</span><span class="sxs-lookup"><span data-stu-id="c0ec1-115">Condition</span></span>](#condition)
- [<span data-ttu-id="c0ec1-116">Rencontrer</span><span class="sxs-lookup"><span data-stu-id="c0ec1-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c0ec1-117">Erdesses</span><span class="sxs-lookup"><span data-stu-id="c0ec1-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c0ec1-118">Couverture</span><span class="sxs-lookup"><span data-stu-id="c0ec1-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="c0ec1-119">[Relevé de médication](#medication-request) (remplace l’ordre Médication dans la version DSTU2 de l’app Patients)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="c0ec1-120">Emplacement (les informations requises pour cette ressource peuvent être incluses dans La Rencontre)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="c0ec1-121">La ressource patient est la seule ressource obligatoire (sans laquelle l’application ne se charge pas du tout) ; Toutefois, il est recommandé au partenaire d’implémenter la prise en charge de toutes les ressources ci-dessus mentionnées par spécifications fournies ci-dessous pour une expérience utilisateur la plus agréable avec l’application Microsoft Teams Patients.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c0ec1-122">Les requêtes de l’Microsoft Teams Patients pour plusieurs ressources publient une offre groupée (BATCH) de demandes sur l’URL du serveur F URL.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c0ec1-123">Le serveur doit traiter chaque demande et renvoyer une offre groupée de ressources correspondent à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c0ec1-124">Pour plus d’informations et d’exemples, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) voir .</span><span class="sxs-lookup"><span data-stu-id="c0ec1-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="c0ec1-125">Instruction de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c0ec1-125">Capability Statement</span></span>

<span data-ttu-id="c0ec1-126">Voici les champs minimum requis :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="c0ec1-127">REST</span><span class="sxs-lookup"><span data-stu-id="c0ec1-127">REST</span></span>

    - <span data-ttu-id="c0ec1-128">Mode</span><span class="sxs-lookup"><span data-stu-id="c0ec1-128">Mode</span></span>
    - <span data-ttu-id="c0ec1-129">Interaction</span><span class="sxs-lookup"><span data-stu-id="c0ec1-129">Interaction</span></span>
    - <span data-ttu-id="c0ec1-130">Ressource : Type</span><span class="sxs-lookup"><span data-stu-id="c0ec1-130">Resource: Type</span></span>
    - <span data-ttu-id="c0ec1-131">Sécurité : [Extension pour les UR OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="c0ec1-132">FembaVersion (notre code nécessite que l’on comprenne la version vers laquelle nous devons pivoter).</span><span class="sxs-lookup"><span data-stu-id="c0ec1-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="c0ec1-133">Consultez [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c0ec1-134">Patient</span><span class="sxs-lookup"><span data-stu-id="c0ec1-134">Patient</span></span>

<span data-ttu-id="c0ec1-135">Voici les champs minimum requis, qui sont un sous-ensemble des champs de profil du patient Argot :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="c0ec1-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="c0ec1-136">Name.Given</span></span>
 - <span data-ttu-id="c0ec1-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="c0ec1-137">Name.Family</span></span>
 - <span data-ttu-id="c0ec1-138">Sexe</span><span class="sxs-lookup"><span data-stu-id="c0ec1-138">Gender</span></span>
 - <span data-ttu-id="c0ec1-139">Date BirthDate</span><span class="sxs-lookup"><span data-stu-id="c0ec1-139">BirthDate</span></span>
 - <span data-ttu-id="c0ec1-140">MRN (identificateur)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-140">MRN (Identifier)</span></span>

<span data-ttu-id="c0ec1-141">Outre les champs [Argot,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c0ec1-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="c0ec1-142">Name.Use</span></span>
 - <span data-ttu-id="c0ec1-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="c0ec1-143">Name.Prefix</span></span>
 - <span data-ttu-id="c0ec1-144">[GeneralPractitioner] - La référence du generalPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="c0ec1-145">Une recherche de ressources utilise la méthode POST à /Patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-146">id</span><span class="sxs-lookup"><span data-stu-id="c0ec1-146">id</span></span>
 - <span data-ttu-id="c0ec1-147">family=(recherche tous les patients dont le nom de famille contient la valeur)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="c0ec1-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="c0ec1-148">given=\<substring></span></span>
 - <span data-ttu-id="c0ec1-149">birthdate=(correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="c0ec1-150">gender=(valeurs l’une des administratives-sexe)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="c0ec1-151">\_nombre (nombre maximal de résultats à retourner)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c0ec1-152">La réponse doit contenir le nombre total d’enregistrements renvoyés suite à la recherche et le nombre sera utilisé par l’App Patients pour limiter le nombre d’enregistrements \_ renvoyés.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="c0ec1-153">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="c0ec1-153">identifier=\<mrn></span></span>

<span data-ttu-id="c0ec1-154">L’objectif est de pouvoir rechercher et filtrer un patient comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c0ec1-155">N° : il s’agit de l’ID de ressource dont dispose chaque ressource de l’affectation FEMBA.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c0ec1-156">MRN : il s’agit de l’identificateur réel du patient que le personnel clinique connaît.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c0ec1-157">Nous comprenons que cette fonction MRN est basée sur le type d’identificateur à l’intérieur de la ressource d’identificateur dans FEMBA.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="c0ec1-158">Nom</span><span class="sxs-lookup"><span data-stu-id="c0ec1-158">Name</span></span>
- <span data-ttu-id="c0ec1-159">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="c0ec1-159">Birthdate</span></span>

<span data-ttu-id="c0ec1-160">Consultez l’exemple suivant de l’appel :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-160">See the following example of the call:</span></span>

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

<span data-ttu-id="c0ec1-161">Consultez [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c0ec1-162">Observation</span><span class="sxs-lookup"><span data-stu-id="c0ec1-162">Observation</span></span>

<span data-ttu-id="c0ec1-163">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil [Vital-Signs argotaïques.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="c0ec1-164">Effectif (date ou période)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="c0ec1-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="c0ec1-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="c0ec1-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="c0ec1-166">ValueQuantity.Value</span></span>

<span data-ttu-id="c0ec1-167">Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c0ec1-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="c0ec1-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="c0ec1-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="c0ec1-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="c0ec1-170">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-171">patient=\<patient id></span></span>
 - <span data-ttu-id="c0ec1-172">_sort=date</span><span class="sxs-lookup"><span data-stu-id="c0ec1-172">_sort=-date</span></span>
 - <span data-ttu-id="c0ec1-173">catégorie (nous interrogerons « category=signes vital ») pour récupérer la liste des signes vital.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="c0ec1-174">Reportez-vous à cet exemple d’appel :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="c0ec1-175">Consultez [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c0ec1-176">Condition</span><span class="sxs-lookup"><span data-stu-id="c0ec1-176">Condition</span></span>

<span data-ttu-id="c0ec1-177">Voici les champs minimaux requis, qui sont un sous-ensemble du profil [de condition argotaïques.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="c0ec1-178">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="c0ec1-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="c0ec1-179">Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c0ec1-180">AréoedDate</span><span class="sxs-lookup"><span data-stu-id="c0ec1-180">AssertedDate</span></span>
 - <span data-ttu-id="c0ec1-181">Gravité</span><span class="sxs-lookup"><span data-stu-id="c0ec1-181">Severity</span></span>

<span data-ttu-id="c0ec1-182">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-183">patient=\<patient id></span></span>
 - <span data-ttu-id="c0ec1-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="c0ec1-184">_count=\<max results></span></span>

<span data-ttu-id="c0ec1-185">Consultez l’exemple suivant de cet appel :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-185">See the following example of this call:</span></span>

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

<span data-ttu-id="c0ec1-186">Consultez [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c0ec1-187">Rencontrer</span><span class="sxs-lookup"><span data-stu-id="c0ec1-187">Encounter</span></span>

<span data-ttu-id="c0ec1-188">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs « must have » du profil [US Core Encounter).](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="c0ec1-189">État</span><span class="sxs-lookup"><span data-stu-id="c0ec1-189">Status</span></span>
 - <span data-ttu-id="c0ec1-190">Tapez[0]. Codage[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="c0ec1-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c0ec1-191">De plus, les champs suivants des champs « doivent prendre en charge » du profil US Core Encounter :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="c0ec1-192">Point.Début</span><span class="sxs-lookup"><span data-stu-id="c0ec1-192">Period.Start</span></span>
 - <span data-ttu-id="c0ec1-193">Emplacement[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="c0ec1-193">Location[0].Location.Display</span></span>

<span data-ttu-id="c0ec1-194">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-195">patient=\<patient id></span></span>
 - <span data-ttu-id="c0ec1-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="c0ec1-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="c0ec1-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="c0ec1-197">_count=\<max results></span></span>

<span data-ttu-id="c0ec1-198">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="c0ec1-199">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-199">Each encounter references a location resource.</span></span> <span data-ttu-id="c0ec1-200">La référence doit également inclure le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="c0ec1-201">Consultez [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c0ec1-202">MondeYIntolerance</span><span class="sxs-lookup"><span data-stu-id="c0ec1-202">AllergyIntolerance</span></span>

<span data-ttu-id="c0ec1-203">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil [d’argotaïeIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="c0ec1-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="c0ec1-204">Code.Text</span></span>
 - <span data-ttu-id="c0ec1-205">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="c0ec1-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="c0ec1-206">État clinique/État De vérification (nous lisons les deux)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="c0ec1-207">Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="c0ec1-208">AréoedDate</span><span class="sxs-lookup"><span data-stu-id="c0ec1-208">AssertedDate</span></span>
 - <span data-ttu-id="c0ec1-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="c0ec1-209">Note.Text</span></span>
 - <span data-ttu-id="c0ec1-210">Réaction</span><span class="sxs-lookup"><span data-stu-id="c0ec1-210">Reaction</span></span>
    - <span data-ttu-id="c0ec1-211">Substance (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="c0ec1-212">Environ (un élément de codage)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="c0ec1-213">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-214">Patient =  \<patient id></span></span>

<span data-ttu-id="c0ec1-215">Consultez l’exemple suivant de l’appel :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="c0ec1-216">Consultez [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="c0ec1-217">Demande de médication</span><span class="sxs-lookup"><span data-stu-id="c0ec1-217">Medication Request</span></span>

<span data-ttu-id="c0ec1-218">Voici les champs minimum requis, qui sont un sous-ensemble du profil de demande de médication de base [pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="c0ec1-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="c0ec1-219">Medication.Display (si référence)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="c0ec1-220">Medication.Text (siConceptable)</span><span class="sxs-lookup"><span data-stu-id="c0ec1-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="c0ec1-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="c0ec1-221">AuthoredOn</span></span>
 - <span data-ttu-id="c0ec1-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="c0ec1-222">Requester.Agent.Display</span></span>

<span data-ttu-id="c0ec1-223">Outre les champs cœur des États-Unis, pour une expérience utilisateur excellente, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="c0ec1-224">[.]. Texte</span><span class="sxs-lookup"><span data-stu-id="c0ec1-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="c0ec1-225">Texte</span><span class="sxs-lookup"><span data-stu-id="c0ec1-225">Text</span></span>

<span data-ttu-id="c0ec1-226">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-227">patient=\<patient id></span></span>
 - <span data-ttu-id="c0ec1-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="c0ec1-228">_count=\<max results></span></span>

<span data-ttu-id="c0ec1-229">Consultez [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c0ec1-230">Couverture</span><span class="sxs-lookup"><span data-stu-id="c0ec1-230">Coverage</span></span>

<span data-ttu-id="c0ec1-231">Il s’agit des champs requis au minimum, et non couverts par les profils Us Core ou Argot :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="c0ec1-232">Regroupement, au moins un élément avec</span><span class="sxs-lookup"><span data-stu-id="c0ec1-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="c0ec1-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="c0ec1-233">GroupDisplay</span></span>
    - <span data-ttu-id="c0ec1-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="c0ec1-234">PlanDisplay</span></span>
 - <span data-ttu-id="c0ec1-235">Point</span><span class="sxs-lookup"><span data-stu-id="c0ec1-235">Period</span></span>
 - <span data-ttu-id="c0ec1-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="c0ec1-236">SubscriberId</span></span>

<span data-ttu-id="c0ec1-237">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c0ec1-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="c0ec1-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="c0ec1-238">Patient = \<patient id></span></span>

<span data-ttu-id="c0ec1-239">Consultez [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="c0ec1-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
